# Vagrantfile for macOS (Japanese Edition)

Vagrantfiles for Japanese macOS HighSierra and Mojave in [vanilla](https://en.wikipedia.org/wiki/Vanilla_software) state. Security updated and for VirutalBOX provider only.

---

このリポジトリは、macOS の検証猿に悩まされるかた向けの Vagrantfile[^vagrantfile] を提供しています。

## Base box

基本となる　Vagrant[^vagrant] Box[^box] イメージは Vagrant Cloud[^vagrantcloud] で提供されています。いずれもプロバイダ[^provider]は VirtualBox です。

- macOS High Sierra (OSX 10.13.6)
  - https://app.vagrantup.com/KEINOS/boxes/macOS.10.13.6_Japanese

## Vagrantfiles

このリポジトリでは以下の Vagrantfile を提供しています。

```text
.
├── LICENSE         MIT ライセンスです。
├── README.md       このファイルです。
└── v10.13.6/       ゲスト OS が HighSierra のディレクトリです。
    ├── vanilla     アップデート意外の余計なインストールがされていない環境を構築します。詳しくは内部の README 参照。
    └── wineskin    Wineskin Winery がインストールされた環境を構築します。（予定）
```

## コラボ

特定の開発環境を構築する Vagrantfile が出来たら遠慮なく PR[^pr] ください。

該当する OS のディレクトリ名の下に、わかりやすいディレクトリを掘り、Vagrantfile と README.md を設置してください。

以下は、HighSierra に `git` と [Homebrew](https://ja.wikipedia.org/wiki/Homebrew_(%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E7%AE%A1%E7%90%86%E3%82%B7%E3%82%B9%E3%83%86%E3%83%A0)) をインストールした環境を提供する場合の設置例です。

```text
.
├── LICENSE
├── README.md           ← 修正（Vagrantfilesにあるツリーに項目を追記）
└── v10.13.6/
    ├── vanilla/
    :
    └── git-brew/       ← 新規
        ├── Vagrantfile ← 新規
        └── README.md   ← 新規
```

なお、一度マージされた PR は、本人の意思に関係なく他者からも自由に改善・変更・修正・削除できるものとします。

## Issue（不具合報告や改善要望）

[Vagrant Cloud 上の Box イメージ](https://app.vagrantup.com/KEINOS/)や、このリポジトリにある Vagrantfile に関する不具合および改善要望は[リポジトリの Issues](https://github.com/KEINOS/Vagrantfile_for_macOS/issues)にお願いします。


[^vagrant]: 【Vagrant とは】Vagrant は、VirutualBox / VMware / Docker などの仮想環境系のアプリケーションをコマンドラインで管理するツールです。
[^vagrantfile]: 【Vagrantfile とは】Vagrant を使って仮想マシン（ゲスト OS 付き）の立ち上げに必要な設定を記載したファイルです。
[^box]: 【Box とは】Vagrant における Box とは、仮想マシン・ゲスト OS および仮想化に必要な設定をパッケージにしたアーカイブファイルのことを指します。
[^vagrantcloud]: 【Vagrant Cloud とは】Vagrant の Box イメージを提供するリポジトリのことです。
[^provider]: 【プロバイダとは】Vagrant におけるプロバイダとは、VirtualBox / VMware / Docker などの仮想環境を提供するアプリケーションのことを指します。
[^pr]: 【PR とは】Pull Request の略。プルリクとも呼ばれる。手元に `clone` したリポジトリの追加・削除・修正を、このリポジトリに反映させるためのリクエストのこと。[「`GitHub` `はじめて` `pull` `request`」の Qiita 記事を検索](https://www.google.com/search?q=site%3Aqiita.com+GitHub+%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6+pull+request) @ Google