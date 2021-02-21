---
marp: true
---

# Shell Script

## ゴール

- 1時間の研修を通じて、Shell Scriptの書き方を体感する
- Shell Scriptが実行できる

---

## なぜShell Scriptか

- CLIでの作業を保存、実行 → 自動化
- OSごとの実行環境を作らずとも、実行できる

---

## Shell Scriptを実行するためには？

- 実行ファイルを用意する
  - シバンで宣言する
  - シェルコマンドを書く
  - ファイルに実行権限を与える
- 実行する

---

### 実行ファイルを用意する

- 1行目にシバン `#!` で起動するインタプリタを宣言する
  - sh（標準シェル）→ `#!/bin/sh`
  - zsh → `#!/bin/zsh`
  - bash → `#!/bin/bash`
- シェルコマンドを書く
- ファイルに実行権限を与える
  - chmodコマンドを使う
    - chmod -- change file modes or Access Control Lists
    - 実行権限を与えたい → `$ chmod +x <ファイル名>`

### 実行する

- `$ ./<ファイル名>`

---

## おまけ

pythonファイルにもシバンが書かれていていたような、、
```
#!/usr/bin/env python3
import sys
print(sys.version)
```

→ pythonはインタプリタ型言語なので、シバンが書かれていることによって、ファイル実行できる

- python（デフォルトバージョン） → `#!/usr/bin/env python`
- python（バージョン指定）→ `#!/usr/bin/env python3`

---

`/usr/bin/env` って？

- env コマンド - set environment and **execute** command, or print environment
- → `PATH=` に記載されていることでパスが通っている
  - e.g. `/usr/bin` がある - `$ env | rg /usr/bin`
- → パスが通っている = プログラム名だけで実行できる
  - e.g. `/usr/bin` の中には `python` がある - `$ ls /usr/bin | rg python`

---

## 確認

### Shell Scriptが使えるようになると、以下のようなメリットが得られます

- CLIでの作業を保存、実行 → 自動化
- OSごとの実行環境を作らずとも、実行できる

### Shell Scriptの実行のためには、以下が必要です

- シバンの宣言
- 実行権限の付与
