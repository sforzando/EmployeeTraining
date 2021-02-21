---
marp: true
---

# Why Learn GitHub Flow

## ゴール

- GitHub Flowにそった開発手順を体感する
- `git` コマンドを使う際に、状態がイメージできる

---

## 内容

- どんなにときに、なぜ？
- GitHubとGitHub Flow
- 実践
  - Git操作で気をつけること
  - GitHub Flow体験
  - より開発しやすくする環境づくり

---

## sforzando LLC. and Inc.での具体的な案件・場面

- sforzando LLC. and Inc.ではGiHubでプロジェクト管理 → https://github.com/sforzando

## なぜGitHubを使って開発をすすめるのか

- プロジェクトメンバーでタスク/コード/進捗の管理および共有が可能なため
- 外部協力者とも共同開発が行ないやすいため
- GitHubのレポジトリをそのまま納品（ドキュメント/コード）することもできるため

---

## Git（GitHub）って？

- Gitはバージョン管理システム
- GitHubは、Gitをクラウド上で管理/共有できるサービス

## sforzando LLC. and Inc.ではどのように使用しているか

- 案件（プロジェクト）毎にリポジトリを用意
- **GitHub Flow**を基本にして、開発を進める

---

## GitHub Flow

### なぜGitHub Flowを使うのか

- 着実に開発を進めていくため
- 開発を進める上で起こりがちな衝突を回避できるため

### どんな衝突が起こるのか

- 共同開発者同士で同じIssueに着手する
- 共同開発者が互いにどんな変更を加えたか分からなくなる
- 開発途中で動かない状態になる

---

### GitHub Flowとは

- 開発を着実に進めていくために
  - 課題設定（Issue） →
  - → 開発ブランチ作成 → コーディング（Coding + Test）→
  - → 変更点まとめ（PR）→ 変更点のレビュー（Review）→
  - → 変更点をmasterへ統合（Merge）→ デプロイ（Deploy）

---

- 主な流れとなるのは2種類
  - `master` （または `main` ）ブランチ（本流）と開発用ブランチ（支流: 複数）

- `master` （または `main` ）ブランチ（本流）
  - バグなどがなく、正常に稼働できる状態のもの
  - 開発用ブランチが取り込まれることによって、成長していく
- 開発用ブランチ（支流）
  - 本流を起点にして、変更を加えるためのもの

---

### 重要! sforzando LLC. and Inc.における3つのGitHub Flowのルール

- `master` （または `main` ）は常にデプロイ可能にする
- 原則としてすべてのcommitはエラーがない状態
- Issueファースト（必ず最初にIssueを作る）

---

## Git（GitHub）実践

### Gitの初期設定

- [Gitでのユーザ名を設定する - GitHub Docs](https://docs.github.com/ja/github/using-git/setting-your-username-in-git#)
  - `$ git config --global user.name "Mona Lisa"`
  - `$ git config --global user.email "email@example.com"`

---

### sforzando LLC. and Inc.のリポジトリをクローンする

- [sforzando/WorkingRules: The Working Rules](https://github.com/sforzando/WorkingRules)
- [sforzando/EmployeeTraining: Employee training documents for sforzando LLC. and Inc.](https://github.com/sforzando/EmployeeTraining)
- `ghq get ~` を使うと良い
- pecoとの組み合わせでリポジトリを移動すると良い
  - `cd $(ghq root)/$(ghq list | peco)` → alias 登録 → `repo`

---

### Gitの操作で迷子にならないために

- Gitの登場人物を意識する
  - リモートリポジトリ、ローカルリポジトリ、ステージングエリア、ワークツリー
- 状態を意識する
  - 今、どのブランチでどういう状態で、何をしたいのか
  - `git` コマンドを実行した後に、どうなるのかイメージできているか
  - エディタのGitをサポートする機能を活用
    - cf. Visual Studio Code
      - Source Control機能（標準機能）
      - [eamodio/vscode-gitlens](https://github.com/eamodio/vscode-gitlens)（拡張機能）
      - [DonJayamanne/gitHistoryVSCode](https://github.com/DonJayamanne/gitHistoryVSCode)（拡張機能）

---

### Gitの操作で気をつけること

- `git <command> -f` は絶対に使わない
  - `-f`, `--force` オプションは強制的にコマンドを実行
  - アラートが出るのは、それは使うと衝突が起きるから
- `commit`, `push` の前に、よくよく状態を確認する
  - `git status`
  - `git log`, `git show`
  - `git diff`

---

### よく使う git コマンド

- `git log`, `git show`, `git status`
- `git branch`, `git checkout`, `git switch`
- `git add`, `git commit`
- `git reset`
- `git push`
- `git pull`, `git fetch`, `git merge`
- `git stash`

Zsh + prezto でのaliasを確認しておこう
  - `$ alias | rg git`

---

## GitHub Flowやってみよう

1. Issue作成
2. 開発
3. PR&レビュー&修正
4. 開発進行と同期をとりつつ、新しい開発へ

cf. [sforzando LLC. and Inc. 流 GitHub Flow の流れ - sforzando LLC. and Inc.](https://sforzando LLC. and Inc..qiita.com/shin-sforzando/items/7d67c7ff06291c8b5bd0)

---

### ステップ1: Issue作成

- GitHubでリモートリポジトリを作成
- GitHubでIssueを作成

---

### ステップ2: 開発

- リモートリポジトリをローカルリポジトリへ `clone` する
- ローカルリポジトリでIssueに対応するbranchを作成
  - ブランチ名は、`<Issue番号>_<タイトル>` としている（Issue番号は0埋め3桁）
- 作成したbranchへ `switch` する
- コーディングし、変更を `commit` する
  - `status` で変更点の確認
  - 変更点をステージに乗せる（= `add` する）
  - ステージに乗った変更点を `commit` する
- リモートリポジトリへ `push` する

---

### ステップ3: PR&レビュー&修正

- Issueに対応できたら、GitHubでPR（Pull Request）を作成する
- レビューおよび修正
- レビュアーにapproveしてもらえたら、本流へマージする

---

### ステップ4: 開発進行と同期をとりつつ、新しい開発へ

- ローカルリポジトリも最新の状態にする
  - `master` （または `main` ）ブランチへ `switch`
  - リモートリポジトリから `fetch` し `merge` する（= `pull` する）
  - 新しいIssueに取りかかる

---

## リポジトリの環境を整えよう

- GitHubの設定で、`master` （または `main` ）ブランチへのマージ条件を制限する
- IssueやPRなどのテンプレートを用意する
- `.gitignore` を用意する
  - GitHubで共有する必要のない、共有してはいけないファイルを定義する
  - `add` によって対象のファイルやディレクトリがcommitに含まれるのを防ぐができる
  - → `.gitignore` 生成サービスを利用すると良い
    - [gitignore.io - Create Useful .gitignore Files For Your Project](https://www.toptal.com/developers/gitignore)
- Slackと連携
- CI/CDと連携
  - [The Leading Code Coverage Solution | Codecov](https://codecov.io/)
    - コードのカバレッジを可視化、通知などしてくれるサービス

---

## まとめ

- GitHub Flowで着実に開発を進めていきます
- Git操作では状態を意識しましょう
