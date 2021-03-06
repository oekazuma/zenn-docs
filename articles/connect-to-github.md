---
title: "GitHubリポジトリでZennのコンテンツを管理する"
emoji: "😸"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["zenn"]
published: true
---



:::message alert
この機能はベータ版で、仕様が変更される可能性があります
:::

Zennには[オンラインエディター](https://zenn.dev/zenn/articles/editor-guide)が用意されていますが、GitHubリポジトリと連携すればローカルのテキストエディターで執筆することもできます。

# GitHub連携時のイメージ

GitHubリポジトリと連携した場合、投稿コンテンツの作成や更新はすべてリポジトリ内で行います。**登録したブランチに変更があると、zenn.devへ自動で同期（デプロイ）が行われます**。

:::details 同期するブランチの指定
GitHub連携が完了している場合、下記のページからブランチを変更できます。
[デプロイ設定 →](/dashboard/deploys)
:::

### コンテンツの作成
ローカルのテキストエディターなどでマークダウンファイルを作成し、編集します。ファイルの作成やプレビューには[Zenn CLI](https://zenn.dev/zenn/articles/install-zenn-cli)を使用できます。

編集が完了したらリモートリポジトリ（GitHub）へプッシュします。登録したブランチへのプッシュやプルリクエストのマージによりデプロイが開始されます。


:::message
zenn.devにまだ存在しない名前のファイルが見つかると新しいコンテンツとして作成されます。
:::


![](https://storage.googleapis.com/zenn-user-upload/37ee1mlki719c8i5uc6fjf2w86zs)

デプロイ履歴は[ダッシュボード](/dashboard/deploys)から確認できます。デプロイ時に発生したエラーもここでチェックします。


### 内容の更新
内容を変更するときは`.md`ファイルを編集し、再度プッシュします。変更が加えられた`.md`ファイルのみがzenn.devに同期されます。

### コンテンツの削除
安全のため、コンテンツの削除は[ダッシュボード](/dashboard)からのみ行うことができます。

![](https://storage.googleapis.com/zenn-user-upload/xjr1cmm572jkte6ygy0dl8ie33jn)


# GitHubとの連携手順
## 1. リポジトリを作成する
まずGitHubで好きな名前のリポジトリを作成します。公開設定はPublicでもPrivateでもOKです。この時点ではリポジトリの中身は空にしておきます。README.mdを作成する必要もありません。

![](https://storage.googleapis.com/zenn-user-upload/t1og2ri6shz2qy501p2mmhre2a0x)


## 2. ダッシュボードから連携する

Zennにログインしたうえで、ダッシュボードの[デプロイ管理](/dashboard/deploys)を開きます。

![](https://storage.googleapis.com/zenn-user-upload/f2n02idgb8y6kucxcz2wgc4u3ihs)

［リポジトリを連携］を選ぶと、リポジトリの選択する画面が表示されます。

![](https://storage.googleapis.com/zenn-user-upload/pwyqlevhxxcekw6919fnho2myukw)


このとき必ず「Only select repositories」にチェックを入れて、**さきほど作成したリポジトリだけを選ぶ**ようにしてください。

:::message
複数のリポジトリが選択されていると連携は失敗します。これは安全のための意図的な仕様です。
:::

これで連携は完了です。

## 3. 同期するブランチ名を確認
[デプロイページ](/dashboard/deploys)で同期したいブランチ名を確認・変更します。

![](https://storage.googleapis.com/zenn-user-upload/vbnsoeqqie0ppavp1bsb5eklsi5r)

ここで登録されている名前のブランチに変更があったときに自動でデプロイが行われます。


# ファイルの作成やプレビューはCLIで
ローカルでのファイルの作成や、マークダウンのプレビューにはZenn CLIを使います。具体的な使い方は下記のページをご覧ください。

📘 **[Zenn CLIの導入手順 →](https://zenn.dev/zenn/articles/install-zenn-cli)**

