# atoma

個人的な備忘録です。

Atomaのテストネットがあり、ノードを建ててみました。
なお、MacOSです。

# 1.ツールのダウンロード
```
brew install curl git cmake gcc openssl pkg-config llvm libpq
```
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

# 2.SUI CLI
```
cargo install --locked --git https://github.com/MystenLabs/sui.git --branch testnet sui --features tracing
```


# 3.SUI  setup
```
sui client
```
 y ⇨ Enter ⇨０

 上記の手順を完了すると、次のファイルがローカルに作成されます (必要に応じて、~ をホーム フォルダー ディレクトリに置き換えてください)。

~/.sui/sui_config/client.yaml- Suiクライアント構成ファイル

~/.sui/sui_config/sui.keystore- Sui キーストア ファイル (秘密鍵が含まれています)


## ４.Faucet
```
sui client faucet
```
```
sui client call --package "0xa1b2ce1a52abc52c5d21be9da0f752dbd587018bc666c5298f778f42de26df1d" --module "toma" --function "faucet" --args "0xfdddd6fb95509ea36f44f06d0d0a2f5868dac2bda1423d204bdc9f458115ff75" 100000000000
```
```
sui client balance
```
上記でSUIとTomaの残高が表示されていればOK

## ５.Atoma CLIをダウンロード
```
git clone https://github.com/atoma-network/atoma-contracts
cd atoma-contracts/sui/
```



# 5.参考文献
<https://docs.unichain.org/docs/building-on-unichain/deploy-a-smart-contract>
