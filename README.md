# Vagrantfile for macOS (Japanese Edition) as a Guest OS

Vagrantfiles for Japanese macOS HighSierra and Mojave as a Guest OS.

---

# VirtualBox のゲスト OS に macOS を Vagrant で

このリポジトリは macOS の検証猿の被害に悩まされるかた向けの Vagrantfile<sup>[1](#vagrantfile)</sup> を共有しています。

## Base box

基本となる Vagrant<sup>[2](#vagrant)</sup> Box<sup>[3](#box)</sup> イメージは Vagrant Cloud<sup>[4](#vagrantcloud)</sup> で提供されています。いずれもプロバイダ<sup>[5](#provider)</sup>は VirtualBox です。

- GuestOS: macOS High Sierra (OSX 10.13.6)
  - https://app.vagrantup.com/KEINOS/boxes/macOS.10.13.6_Japanese @ Vagrant Cloud
  - [動作確認済み Host OS 一覧](https://github.com/KEINOS/Vagrantfile_for_macOS/issues/1)

## Vagrantfiles

このリポジトリでは以下の Vagrantfile を提供しています。

```text
.
├── LICENSE                     MIT ライセンスです。
├── README.md                   このファイルです。
├── v10.13.6/                   ゲスト OS が HighSierra のディレクトリです。
│   ├── vanilla/                アップデート以外の余計なインストールがされていない環境です。
│   │   ├── README.md
│   │   ├── Vagrantfile
│   │   └── Vagrantfile-GUI
│   └── wineskin                Wineskin Winery がインストールされた環境を構築します。（予定）
│       └── README.md
└── v10.14.1/                   ゲスト OS が Mojave のディレクトリです。
    └── vanilla/                アップデートと git 以外の余計なインストールがされていない環境です。
        ├── README.md
        ├── Vagrantfile
        └── Vagrantfile-GUI
```

## コラボ

特定の開発環境を構築する Vagrantfile が出来たら遠慮なく PR<sup>[6](#pr)</sup> ください。

該当するゲスト OS のディレクトリの下に、わかりやすいディレクトリ名で、Vagrantfile と README.md を設置してください。

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


---

注釈：

1. <a name="vagrantfile"></a><small>【Vagrantfile とは】Vagrant を使って仮想マシン（ゲスト OS 付き）の立ち上げに必要な設定を記載したファイルです。</small>
1. <a name="vagrant"></a><small>【Vagrant とは】Vagrant は、VirutualBox / VMware / Docker などの仮想環境系のアプリケーションをコマンドラインで管理するツールです。</small>
3. <a name="box"></a><small>【Box とは】Vagrant における Box とは、仮想マシン・ゲスト OS および仮想化に必要な設定をパッケージにしたアーカイブファイルのことを指します。</small>
4. <a name="vagrantcloud"></a><small>【Vagrant Cloud とは】Vagrant の Box イメージを提供するリポジトリのことです。</small>
5. <a name="provider"></a><small>【プロバイダとは】Vagrant におけるプロバイダとは、VirtualBox / VMware / Docker などの仮想環境を提供するアプリケーションのことを指します。</small>
6. <a name="pr"></a><small>【PR とは】Pull Request の略。プルリクとも呼ばれる。手元に `clone` したリポジトリの追加・削除・修正を、このリポジトリに反映させるためのリクエストのこと。[「`GitHub` `はじめて` `pull` `request`」の Qiita 記事を検索](https://www.google.com/search?q=site%3Aqiita.com+GitHub+%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6+pull+request) @ Google</small>
