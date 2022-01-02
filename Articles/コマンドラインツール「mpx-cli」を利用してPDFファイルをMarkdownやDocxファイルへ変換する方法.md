---
title: コマンドラインツール「mpx-cli」を利用してPDFファイルをMarkdownやDocxファイルへ変換する方法
tags: LaTeX mathpix homebrew npm
author: kei11235813
slide: false
---
# コマンドラインツール「mpx-cli」を利用してPDFファイルをMarkdownやDocxファイルへ変換する方法

### 概要
Mathpix Snipの機能をターミナルから実行できるコマンドラインツール「mpx-cli」を利用することで、編集に手間のかかるPDFファイルを簡単に編集可能なMarkdownやDocxファイルへ変換する方法を書いていきます。

### 目次
- 実行環境
- `HomeBrew`のインストール
- `npm`のインストール
- `mpx-cli`のインストール
- Mathpix Snipのアカウント登録とログイン
- 使い方
- 終わりに

### 実行環境
- MacBook Air (M1, 2020)
- シェル: zsh

### HomeBrewのインストール
:::note info
Homebrewを既にインストールしている方は飛ばしてください。
:::

[HomeBrew公式サイト](https://brew.sh/)の`Install Hombrew`下のコマンドをターミナル上で実行。

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

途中Enterを押してインストールが進むと追加のコマンドが求められます。
ターミナルに表示されているコマンドを打ち、パスを通しましょう。

```
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/ユーザ名/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

最後にHomebrewが正常にインストール及びパスの追加ができているか確認します。

```
brew help
```


:::note warn
コマンドは必ず公式サイトからコピーしましょう。
:::


### npmのインストール

:::note info
npmを既にインストールしている方は飛ばしてください。
:::

Homebrewでnodebrewをインストールするため、以下のコマンドを実行します。

```
brew install nodebrew
```


nodebrewでnpmをNode.js(LTS版)と一緒にインストールするため、以下のコマンドを実行します。

```
nodebrew install stable
```

最新版をインストールしたい場合は`nodebrew install latest`と実行しましょう。

続いて使いたいNode.jsのバージョンを指定する必要があります。
[Node.js公式サイト](https://nodejs.org/en/)からLTS版のバージョンを指定しましょう。

```
nodebrew use v14.18.1
```

下記コマンドを実行すると、currentに使いたいNode.jsのバージョンが表示されているかと思います。

```
nodebrew ls
```

最後にパスを通します。

```
export PATH=$HOME/.nodebrew/current/bin:$PATH
source ~/.zsh_profile
```

下記コマンドを実行し、バージョンが表示されればインストールは完了です。

```
node -v
npm -v
```


### mpx-cliのインストール
npmを使ってmpx-cliをインストールするため、下記コマンドを実行します。

```
npm install -g @mathpix/mpx-cli
```

### Mathpix Snipのアカウント登録とログイン
[Mathpixの登録ページ](https://accounts.mathpix.com/signup)からアカウントを登録しましょう。
メールボックスにMathpixからのメールが届いているのでメールを認証し、ログインしましょう。

:::note info
学生の方はac.jpドメインで登録しましょう。月間無料利用回数が2倍になります。
:::

最後に下記コマンドを実行します。

```
mpx login
```

アカウント登録に利用したメールアドレスとパスワードを要求されるので入力します。パスワード入力中は画面に変更はありませんがそのまま入力しましょう。


### 使い方

詳細な使い方は[README.md](https://github.com/Mathpix/mpx-cli/blob/master/README.md)を参考にしてください。

<iframe width="560" height="400" src="https://www.youtube.com/embed/OTaPlA2-XPo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

PDFファイルを編集可能なファイルへ変換したい場合は下記コマンドを実行すると変換後のファイルがダウンロードされます。

```
mpx convert input-file.pdf output-file.docx
```

ホームディレクトリ以外で実行する場合、上記動画のようにファイルのパスも書きましょう。


### 終わりに

Qiitaへの初めての投稿なので色々と至らぬ点があったと思いますが、最後まで本記事を見てくださりありがとうございました。

