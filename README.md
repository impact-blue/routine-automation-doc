# 業務効率化コード集
業務効率化のためのコードテンプレートを集めたものです。

## Github
### 前提
[Github CLI](https://cli.github.com/)のインストールが必要です。

### コード
ターミナルで使用するショートカットです。
~/.zshrc にコマンドを追加してください。

```
# 現在のブランチを取得
alias get_current_branch="git branch | grep '*' | sed -e 's/^\* //'"

# 新しいブランチをプッシュ & PR 作成
# コマンド例：ppr 'バグを修正' 'http://asana.example.com'
function ppr {
  current_branch=`get_current_branch`;
  git push -u origin $current_branch;
  gh pr create -d -a @me -t $1 -b $2;
}

# 現在のブランチの指定ワークフローを実行する
# コマンド例：wkfw check-codestyle
function wkfw {
  gh workflow run $1.yml --ref `get_current_branch`;
}

```