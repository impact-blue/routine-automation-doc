# このテンプレートの使い方

1. 「Use this template」をクリック
    - リポジトリの設定は [.github](https://github.com/impact-blue/.github/blob/main/.github/settings.yml) リポジトリと一緒になります
    - リポジトリはデフォルトで非公開になります
    - `create-asana-attachment`ワークフローは既に入っているのでプルリクエストの概要に Asana のタスク URL を追加すれば Asana のタスクとプルリクエストを連携できます
2. `CODEOWNERS`を適切な内容に修正
    - リポジトリに関わるユーザが変わる可能性があるのでユーザより出来るだけチームを設定するようにしてください
      - `CODEOWNERS`にチームを追加する場合はリポジトリにもチームを追加しなければなりません（Settings → Collaborators and teams）
3. `settings.yml`を適切な内容に修正
    - 修正は基本的に不要です
    - リポジトリを公開したい場合は`private: true`を削除してください
    - マージする前に通らなければならないチェック（Chromatic、`eslint`、`prettier`、`tsc`など）がある場合はチェックを`required_status_checks`に追加してください
4. 環境構築のチェック
    - マージする前に構築が成功しなければならない環境（Vercel のプレビュー環境など）がある場合は`main`ブランチ設定の「Require deployments to succeed before merging」に環境を追加してください
      - `settings.yml`で設定ができないので UI 上で設定しなければなりません
