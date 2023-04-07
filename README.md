# 業務効率化コード集
業務効率化のためのコードテンプレートを集めたものです。

## Github

**前提**
* [Github CLI](https://cli.github.com/)のインストールが必要です。
* Github CLI のコマンドの仕様は[リファレンス](https://cli.github.com/manual/)を参照してください。
* ターミナルで使用するショートカットです。~/.zshrc にコマンドを追加してください。

### 現在のブランチを取得（以下のコードはこちらのエイリアスが登録されていることが前提となります）
```
alias get_current_branch="git branch | grep '*' | sed -e 's/^\* //'"
```
### 新しいブランチをプッシュ & Draft の PR 作成
```
function ppr {
  current_branch=`get_current_branch`;
  git push -u origin $current_branch;
  gh pr create -d -a @me -t $1 -b $2;
}
```
コマンド例: `ppr 'バグの修正' 'https://asana.example.com'`


### 現在のブランチの指定ワークフローを実行する
```
function wkfw {
  gh workflow run $1.yml --ref `get_current_branch`;
}
```
コマンド例：`wkfw check-codestyle`