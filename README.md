# Vagrantfile for macOS Guest (Japanese Edition)

Vagrantfiles for Japanese macOS HighSierra and Mojave as a Guest OS. (Provider: VirtualBox)

- For Non VirtualBox users:
  - [Search result of "OSX"](https://app.vagrantup.com/boxes/search?utf8=%E2%9C%93&q=OSX) @ VagrantCloud

**Note:** The base boxes using in Vagrantfiles at this repsitory are **only for purposes of: (a) software development; (b) testing during software development; and (c) personal, non-commercial use**.


# VirtualBox のゲスト OS に日本語 macOS を Vagrant で

**このリポジトリは macOS の検証猿の被害に悩まされるかた向け**の Vagrantfile<sup>[1](#vagrantfile)</sup> および、日本語版 macOS の Base Box に適用している Vagrantfile を共有しています。（プロバイダー：VirtualBox）

- VirtualBox 以外のユーザ:
  - ["OSX" の検索結果](https://app.vagrantup.com/boxes/search?utf8=%E2%9C%93&q=OSX) @ VagrantCloud


## Sample Usage

### Bring up macOS in CLI mode (use via SSH).

```shellsession
$ # HighSierra
$ vagrant init -m KEINOS/macOS.10.13.6_Japanese
...
$ vagrant up
...
$ vagrant ssh
...
```
```shellsession
$ # Mojave
$ vagrant init -m KEINOS/macOS.10.14.1_Japanese
...
$ vagrant up
...
$ vagrant ssh
...
```

### Bring up macOS in GUI mode.

```shellsession
$ # HighSierra
$ curl -o Vagrantfile https://KEINOS.github.io/Vagrantfile_for_macOS/Vagrantfiles/Vanilla_GUI_v10.13.6
...
$ vagrant up
...
```
```shellsession
$ # Mojave
$ curl -o Vagrantfile https://KEINOS.github.io/Vagrantfile_for_macOS/Vagrantfiles/Vanilla_GUI_v10.14.1
...
$ vagrant up
...
```

---

## リポジトリのディレクトリ構成

```text
.
├── LICENSE                     MIT ライセンスです。
├── README.md                   このファイルです。
├── Vagrantfiles                各種カスタム用 Vagrantfile のサンプル
│   ├── Vanilla_CUI_v10.13.6
│   ├── Vanilla_CUI_v10.14.1
│   ├── Vanilla_GUI_v10.13.6
│   ├── Vanilla_GUI_v10.13.6
│   ├── Homebrew_CLI_v10.14.1
│   ├── VNC_to_Headless_v10.13.6
│   └── ...
└── base-boxes                  Base Box リリース用ディレクトリ
    ├── README.md
    ├── build_base_box          ローカルの VirutalBox から Base Box を作成するスクリプト
    ├── macOS.10.13.6_Japanese  HighSierra の Base Box 用 Vagrantfile
    │   ├── info.json           Box に含める情報
    │   ├── Vagrantfile_v0.0.1  デフォルトの Vagrantfile（バージョン別）
    │   ├── Vagrantfile_v0.0.2
    │   └── ...
    └── macOS.10.14.1_Japanese  Mojave の Base Box 用 Vagrantfile
        ├── info.json           Box に含める情報
        ├── Vagrantfile_v0.0.1  デフォルトの Vagrantfile（バージョン別）
        ├── Vagrantfile_v0.0.2
        └── ...
```

### Base Boxes for macOS Guest OS

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

### Vagrantfiles for macOS Guest OS

上記 Base Box を元に、さまざまな開発環境を構築する Vagrantfile も共有しています。

特定の開発環境を構築する Vagrantfile が出来たら遠慮なく PR<sup>[6](#pr)</sup> ください。

## PR とコラボ

例えば、最新の XCode を HighSierra にセットアップする Vagrantfile を共有する場合は以下の通りになります。

### コラボ例

- Vagrantfile のファイル名：`XCode_Latest_v10.13.6`
- 設置先ディレクトリ： `./Vagrantfiles`
- ダウンロード URL： `https://KEINOS.github.io/Vagrantfile_for_macOS/Vagrantfiles/XCode_Latest_v10.13.6`

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

- ファイル名から主な内容がわかるようにしてください。
- その他の情報は、各 Vagrantfile 内のコメントに記載してください。
- 詳細な使い方が必要な場合は、[Qiita](https://qiita.com) やブログなどで記事にし、コメントにその URL を記載してください。
- 一度マージされた PR は、本人の意思に関係なく他者からも自由に改善・変更・修正・削除できるものとします。

## Issue（不具合報告や改善要望）

Vagrant Cloud 上の Box イメージや、このリポジトリにある Vagrantfile に関する不具合および改善要望は[リポジトリの Issues](https://github.com/KEINOS/Vagrantfile_for_macOS/issues) にお願いします。

## 免責事項

**自己責任でご利用ください**。

## ライセンスと禁止事項

本リポジトリで公開されている Vagrantfile は [MIT](https://github.com/KEINOS/Vagrantfile_for_macOS/blob/master/LICENSE) ライセンスになります。（Vagrant Cloud 上の Base Box イメージは除く）

<font color=red>**【重要】** このリポジトリで利用している [Base Box](https://app.vagrantup.com/boxes/search?utf8=%E2%9C%93&sort=downloads&provider=&q=KEINOS+macOS) は Mac ユーザー向けで、macOS/iOS などの**開発におけるビルドや動作テスト環境および検証専用**</fonrt>です。これら以外の用途には使用しないでください</font>。

そのため、使用時はデベロッパー（開発者）として下記 Apple の使用許諾および同意したものとします。

- [SOFTWARE LICENSE AGREEMENT FOR macOS High Sierra](http://images.apple.com/legal/sla/docs/macOS1013.pdf) @ Apple 公式 PDF
- [SOFTWARE LICENSE AGREEMENT FOR macOS Mojave](http://images.apple.com/legal/sla/docs/macOS1014.pdf) @ Apple 公式 PDF

### 他の Vagrant イメージを使う

- [Search result of "OSX"](https://app.vagrantup.com/boxes/search?utf8=%E2%9C%93&q=OSX) @ VagrantCloud

---

注釈：

1. <a name="vagrantfile"></a><small>【Vagrantfile とは】Vagrant を使って仮想マシン（ゲスト OS 付き）の立ち上げに必要な設定を記載したファイルです。</small>
1. <a name="vagrant"></a><small>【Vagrant とは】Vagrant は、VirutualBox / VMware / Docker などの仮想環境系のアプリケーションをコマンドラインで管理するツールです。</small>
3. <a name="box"></a><small>【Box とは】Vagrant における Box とは、仮想マシン・ゲスト OS および仮想化に必要な設定をパッケージにしたアーカイブファイルのことを指します。</small>
4. <a name="vagrantcloud"></a><small>【Vagrant Cloud とは】Vagrant の Box イメージを提供するリポジトリのことです。</small>
5. <a name="provider"></a><small>【プロバイダとは】Vagrant におけるプロバイダとは、VirtualBox / VMware / Docker などの仮想環境を提供するアプリケーションのことを指します。</small>
6. <a name="pr"></a><small>【PR とは】Pull Request の略。プルリクとも呼ばれる。手元に `clone` したリポジトリの追加・削除・修正を、このリポジトリに反映させるためのリクエストのこと。[「`GitHub` `はじめて` `pull` `request`」の Qiita 記事を検索](https://www.google.com/search?q=site%3Aqiita.com+GitHub+%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6+pull+request) @ Google</small>
