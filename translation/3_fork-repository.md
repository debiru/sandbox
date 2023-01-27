# 3. fork リポジトリを用意する

## 初めてリポジトリを fork する場合 {#first}

- https://github.com/mdn/content リポジトリを fork します。
- https://github.com/mdn/translated-content リポジトリを fork します。

## 既にリポジトリを fork している場合 {#already}

- fork したリポジトリ https://github.com/YOUR_NAME/content のページへアクセスします。
- 画面上部にある「Sync fork」を押して「Update branch」を実行します。
- "This branch is up to date with mdn/content:main." と表示されたことを確認します。
    - ここが異なる表示結果になった場合、リポジトリに不整合が生じている可能性があります。その場合は以下の Git コマンドを参考に問題を解決するか Slack で相談してください。
- https://github.com/YOUR_NAME/translated-content のページでも同様のことを行います。

### Git コマンドで Sync fork する方法 {#command}

```
// 前提：clone したリポジトリのディレクトリに移動している
$ cd ~/path/to/
$ git clone git@github.com:YOUR_NAME/translated-content.git
$ cd ~/path/to/translated-content

// main ブランチにいることを確認する
$ git branch

// main ブランチにいなければ、main ブランチに移動する
$ git checkout main

// origin のみであることを確認する
$ git remote -v
origin	git@github.com:YOUR_NAME/translated-content.git (fetch)
origin	git@github.com:YOUR_NAME/translated-content.git (push)

// remote を追加する
$ git remote add upstream git@github.com:mdn/translated-content.git

// upstream が増えていることを確認する
$ git remote -v
origin	git@github.com:YOUR_NAME/translated-content.git (fetch)
origin	git@github.com:YOUR_NAME/translated-content.git (push)
upstream	git@github.com:mdn/translated-content.git (fetch)
upstream	git@github.com:mdn/translated-content.git (push)

// upstream からローカルブランチに変更を取り込む
$ git pull upstream main

// ローカルブランチの状態を GitHub に反映させる
$ git push origin main
```
