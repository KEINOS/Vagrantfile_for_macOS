# 日本語版 macOS（バニラ状態）の Vagrant Box

アップデート済みで [Vanilla 状態](https://ja.wikipedia.org/wiki/%E3%83%90%E3%83%8B%E3%83%A9_(%E3%82%BD%E3%83%95%E3%83%88%E3%82%A6%E3%82%A7%E3%82%A2))の macOS 仮想環境が必要な場合にご利用ください。

- VirtualBox >= v6.0.4 r128413
- Vagrant >= v2.2.3
- Base box = Latest version. [See latest](https://app.vagrantup.com/KEINOS/boxes/macOS.10.13.6_Japanese/) @ Vagrant Cloud
- [動作確認済み一覧](https://github.com/KEINOS/Vagrantfile_for_macOS/issues/1)
- 注意：
  - Box イメーイは 20 GB 近くあります。空き容量と時間にご注意ください。
  - 無事に起動したら、**初期状態のスナップショットを撮ることをおすすめします＊＊。詳しくは下記「スナップショット」参照。

## ヘッドレス・モード（GUI なし。SSH 接続での利用）

### ダウンロード

```bash
curl -O https://KEINOS.github.io/Vagrantfile_for_macOS/v10.13.6/vanilla/Vagrantfile
```

### ダウンロードと起動

```shellsession
$ curl -O https://KEINOS.github.io/Vagrantfile_for_macOS/v10.13.6/vanilla/Vagrantfile
$ vagrant up
...
```

## GUI モード

### ダウンロード

```bash
curl -o Vagrantfile https://KEINOS.github.io/Vagrantfile_for_macOS/v10.13.6/vanilla/Vagrantfile
```

### ダウンロードと起動

```shelsession
$ curl -o Vagrantfile https://KEINOS.github.io/Vagrantfile_for_macOS/v10.13.6/vanilla/Vagrantfile-GUI
$ vagrant up
...
```

## 基本的な使い方

以下のユーザーでログインします。

- ユーザー： `vagrant`（管理者権限）
- パスワード： `vagrant`（`root` のパスワードも同じです）

### SSH 接続

起動後は `$ vagrant ssh` もしくは `$ ssh -p 2222 vagrant@127.0.0.1` で SSH アクセスできます。

RSA 公開鍵・秘密鍵認証で SSH 接続したい場合は、`.ssh/authorized_keys` に [Vagrant 公式の公開鍵](https://github.com/hashicorp/vagrant/blob/master/keys/vagrant.pub)が設定されています。ペアとなる[公式の秘密鍵](https://github.com/hashicorp/vagrant/blob/master/keys/vagrant)を使ってログインください。

### スナップショット

スナップショットの撮影（現在の状態のバックアップ）と復元は `vagrant snapshot` コマンドを使います。

- 撮影（バックアップ）： `vagrant snapshot push`
- 復元（リカバリー）　： `vagrant snapshot pop`
- その他　　　　　　　： `vagrant snapshot --help`

```shellsession
$ # 現在の状態のスナップショットを撮る
$ vagrant snapshot push
==> default: Snapshotting the machine as 'push_xxxxxxxxxx_yyyy'...
==> default: Snapshot saved! You can restore the snapshot at any time by
==> default: using `vagrant snapshot restore`. You can delete it using
==> default: `vagrant snapshot delete`.

$ # スナップショットのリカバリー（復元）
$ vagrant snapshot pop
==> default: Forcing shutdown of VM...
==> default: Restoring the snapshot 'push_xxxxxxxxxx_yyyy'...
==> default: Deleting the snapshot 'push_xxxxxxxxxx_yyyy'...
==> default: Snapshot deleted!
==> default: Checking if box 'KEINOS/macOS.10.13.6_Japanese' version '0.0.1' is up to date...
==> default: Resuming suspended VM...
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:2222
    default: SSH username: vagrant
    default: SSH auth method: private key
==> default: Machine booted and ready!
==> default: Machine already provisioned. Run `vagrant provision` or use the `--provision`
==> default: flag to force provisioning. Provisioners marked to run always will still run.
```

なお、スナップショットに名前を付けて管理したい場合や複数スナップショットを使い分ける必要がある場合は、[Vagrant 公式のコマンドの詳細](https://www.vagrantup.com/docs/cli/snapshot.html)をご覧ください。
