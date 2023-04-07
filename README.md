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


```