# 4. fork リポジトリを clone する

## 初めてリポジトリを clone する場合 {#first}

```
// 作業用ディレクトリを作成する
$ cd ~/path/to
$ mkdir mdn_repos
$ cd ~/path/to/mdn_repos

// fork リポジトリを 2 つとも clone する
$ git clone git@github.com:YOUR_NAME/content.git
$ git clone git@github.com:YOUR_NAME/translated-content.git

$ ls
content    translated-content

// content ディレクトリ内に .env を作成する
$ cd content
$ echo 'CONTENT_TRANSLATED_ROOT=../translated-content/files' > .env
$ cat .env
CONTENT_TRANSLATED_ROOT=../translated-content/files

// ローカルプレビューができるように yarn install しておく
$ yarn install
```

## 既にリポジトリを clone している場合 {#already}

```
// 作業用ディレクトリに移動する
$ cd ~/path/to/mdn_repos

// 最新の fork リポジトリを pull する
$ cd content
$ git checkout main
$ git pull

// content リポジトリでは yarn install し直しておく
$ yarn install

// translated-content リポジトリも pull しておく
$ cd ../translated-content
$ git checkout main
$ git pull
```
