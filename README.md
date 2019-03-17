# Vagrantfile for macOS (Japanese Edition) as a Guest OS
# VirtualBox のゲスト OS に macOS を Vagrant で

Vagrantfiles for Japanese macOS HighSierra and Mojave as a Guest OS.
**このリポジトリは macOS の検証猿の被害に悩まされるかた向け**の Vagrantfile<sup>[1](#vagrantfile)</sup> および、日本語版 macOS の Base Box に適用している Vagrantfile を共有しています。

---

## Base boxes for macOS Guest OS

当リポジトリでは、Vagrant Cloud<sup>[4](#vagrantcloud)</sup> で共有している、以下の Vagrant<sup>[2](#vagrant)</sup> 用 Base Box<sup>[3](#box)</sup> の設定情報を共有しています。

- GuestOS:
  - macOS High Sierra (OSX 10.13.6)
    - Vagrant Cloud: [KEINOS/macOS.10.13.6_Japanese](https://app.vagrantup.com/KEINOS/boxes/macOS.10.13.6_Japanese)
    - [動作確認済み Host OS 一覧](https://github.com/KEINOS/Vagrantfile_for_macOS/issues/1)
    - Provider<sup>[5](#provider)</sup>: VirtualBox
  - macOS Mojave (OSX 10.14.1)
    - Vagrant Cloud: [KEINOS/macOS.10.14.1_Japanese](https://app.vagrantup.com/KEINOS/boxes/macOS.10.14.1_Japanese)
    - [動作確認済み Host OS 一覧](https://github.com/KEINOS/Vagrantfile_for_macOS/issues/2)
    - Provider: VirtualBox

## リポジトリのディレクトリ構成

```text
.
├── LICENSE                     MIT ライセンスです。
├── README.md                   このファイルです。
├── Vagrantfiles                KEINOS/macOS.10.xx.xx_Japanese の Box をカスタムする Vagrantfiles
│   ├── Vanilla_CUI_v10.13.6
│   ├── Vanilla_CUI_v10.14.1
│   ├── Vanilla_GUI_v10.13.6
│   └── Vanilla_GUI_v10.14.1
└── base-boxes                  KEINOS/macOS.10.xx.xx_Japanese の Box に適用している Vagrantfiles
    ├── README.md
    ├── build_base_box          ローカルにある VirutalBox から Base Box を作成するスクリプト
    ├── macOS.10.13.6_Japanese  HighSierra の Base Box 用 Vagrantfile
    │   ├── Vagrantfile_v0.0.1
    │   ├── Vagrantfile_v0.0.2
    │   ├── Vagrantfile_v0.0.3
    │   ├── info.json
    │   └── macOS.10.13.6_Japanese.box
    └── macOS.10.14.1_Japanese  Mojave の Base Box 用 Vagrantfile
        ├── Vagrantfile_v0.0.1
        ├── Vagrantfile_v0.0.2
        └── info.json
```

## コラボ

特定の開発環境を構築する Vagrantfile が出来たら遠慮なく PR<sup>[6](#pr)</sup> ください。

例えば、最新の XCode を HighSierra にセットアップする Vagrantfile（XCode_Latest_v10.13.6）の場合は以下の通りになります。

```text
.
├── Vagrantfiles 
│   ├── XCode_Latest_v10.13.6   ←　ファイル名からわかりやすいものにしてください。
│   ├── Vanilla_CUI_v10.13.6
│   ├── Vanilla_CUI_v10.14.1
│   ├── Vanilla_GUI_v10.13.6
│   └── Vanilla_GUI_v10.14.1
:
```

- ファイル名から主な内容がわかるようにしてください。また詳細な情報は、各 Vagrantfile 内のコメントに記載してください。
- 一度マージされた PR は、本人の意思に関係なく他者からも自由に改善・変更・修正・削除できるものとします。


## Issue（不具合報告や改善要望）

[Vagrant Cloud 上の Box イメージ](https://app.vagrantup.com/KEINOS/)や、このリポジトリにある Vagrantfile に関する不具合および改善要望は[リポジトリの Issues](https://github.com/KEINOS/Vagrantfile_for_macOS/issues) にお願いします。


---

注釈：

1. <a name="vagrantfile"></a><small>【Vagrantfile とは】Vagrant を使って仮想マシン（ゲスト OS 付き）の立ち上げに必要な設定を記載したファイルです。</small>
1. <a name="vagrant"></a><small>【Vagrant とは】Vagrant は、VirutualBox / VMware / Docker などの仮想環境系のアプリケーションをコマンドラインで管理するツールです。</small>
3. <a name="box"></a><small>【Box とは】Vagrant における Box とは、仮想マシン・ゲスト OS および仮想化に必要な設定をパッケージにしたアーカイブファイルのことを指します。</small>
4. <a name="vagrantcloud"></a><small>【Vagrant Cloud とは】Vagrant の Box イメージを提供するリポジトリのことです。</small>
5. <a name="provider"></a><small>【プロバイダとは】Vagrant におけるプロバイダとは、VirtualBox / VMware / Docker などの仮想環境を提供するアプリケーションのことを指します。</small>
6. <a name="pr"></a><small>【PR とは】Pull Request の略。プルリクとも呼ばれる。手元に `clone` したリポジトリの追加・削除・修正を、このリポジトリに反映させるためのリクエストのこと。[「`GitHub` `はじめて` `pull` `request`」の Qiita 記事を検索](https://www.google.com/search?q=site%3Aqiita.com+GitHub+%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6+pull+request) @ Google</small>
