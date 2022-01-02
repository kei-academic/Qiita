---
title: ターミナルでの出力結果をコピーしたい(Mac)
tags: Mac pbcopy
author: kei11235813
slide: false
---
# ターミナルでの出力結果をコピーしたい(Mac)

### 概要
ターミナルの出力結果をpbcopyコマンドに入力することでコピーすることができる．

### ex1.) treeコマンドの出力結果をコピー

```zsh
❯ tree | pbcopy
❯ pbpaste
.
├── Articles
│  └── ターミナルの出力結果をコピーしたい(Mac).md
├── LICENSE
└── README.md
```

README.mdに書くことがない時に，treeの出力結果を`pre`タグで囲むといい感じになる．
ターミナル上で出力結果を表示するために`pbcopy`の対となる`pbpaste`コマンドを使用しているが，`Command+v`でペースト可能である．

### ex2.) ファイルの内容をコピー

```zsh
❯ cat ~/.ssh/github.pub | pbcopy
```

GitHubの公開鍵をコピーするのに役立つ．くれぐれも秘密鍵をコピーしないように．

### ex3.) 作業ディレクトリのパスをコピー

```zsh
❯ pwd | pbcopy
```

pwd は print working directory の略である．
`git mv`など，ファイルのパスを正しく入力したいときによく用いる．

### aliasの設定
毎度コピーするごとに`pbcopy`と入力するのが億劫なので，aliasを設定する．

```sh
alias pb='pbcopy'
```

pb は`pasteboard`の略である．
alias名は何でもいいが，自分がわかりやすいものがいい．

:::note warn
aliasの = 間に半角空白を入れてはいけない．詳しくはシェルスクリプトを参照．
:::

### 終わりに
本記事は個人的な備忘録を修正したものです．至らぬ点があるかと思いますがご了承ください．
