# Key transition statement

Date: 2025/07/07

- 前の鍵の作成から1年半が経過した
- Keyoxide に表示される notation を見直した

などの理由から、新しい OpenPGP 鍵をセットアップした。

古い鍵は 2025/07/14 まで有効にしておく予定だが、

- ProtonMail で使用されるメール暗号化・署名
- Git commit の署名

などは 2025/07/14 までに順次移行される。

古い鍵は以下の通り。

```text
pub   ed25519/2C773681151FDE8F 2024-01-06
      Key fingerprint = 9C22B2503BDD9E049728C5432C773681151FDE8F
```

新しい鍵は以下の通り。

```text
pub   ed25519/2A0B2ABA53BCBC12 2025-07-07
      Key fingerprint = 9A20FF47C3D9CCE2B0C980FF2A0B2ABA53BCBC12
```

公開鍵サーバー `keys.openpgp.org` から新しい鍵を取得するには、以下のコマンドを実行する。

```shell
gpg --keyserver keys.openpgp.org --recv-key '9A20FF47C3D9CCE2B0C980FF2A0B2ABA53BCBC12'
```

すでに古い鍵を保有している場合は、新しい鍵が古い鍵によって署名されていることを確認できる。

```shell
gpg --check-sigs '9A20FF47C3D9CCE2B0C980FF2A0B2ABA53BCBC12'
```

更に鍵を検証したい場合は、上記の指紋と照合できる。

```shell
gpg --fingerprint '9A20FF47C3D9CCE2B0C980FF2A0B2ABA53BCBC12'
```

Ray Shirohara (城原 零)
