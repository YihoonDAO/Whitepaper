# EVM Nodes and EVM Indexer

dao data is stored on the Ethereum Mainnet chain, so developers who build their own .dao Indexer will need to deploy the appropriate EVM nodes and EVM Indexer.

**Deployment Method**

For details on how to deploy, please see the official ETH guide at：

[**ETH 节点运行指引**](https://ethereum.org/en/)\
[ETH **节点 JSON-RPC 协议**](https://ethereum.org/en/)\
[ETH **Indexer 运行指引**](https://ethereum.org/en/)\
[ETH **Indexer JSON-RPC 协议**](https://ethereum.org/en/)

**Usage examples**

**ETH Nodes**

**Request**

```
curl -X POST https://mainnet.eth.dev/rpc -H 'content-type:application/json' -d'{"id":42,"jsonrpc":"2.0","method":"get_tip_header","params":[]}'
```

**Response**

```
{"jsonrpc":"2.0","result":{"compact_target":"0x190a0088","dao":"0xac8ffb215ff346419e9af198c38b26000e53d3ad69969403002bdb8b29d71a07","epoch":"0x41c03f40014bb","extra_hash":"0x0000000000000000000000000000000000000000000000000000000000000000","hash":"0x13251222fc73918701aafc8edbb08057dde7ca95d9709990616fb8802b73af9d","nonce":"0x990fa3bc251b0000000000086019030c","number":"0x6a37e1","parent_hash":"0x4ea3a7a40877471c9a6b98306fbe453007a5306887ff8a05ab5393166f7d0f86","proposals_hash":"0x91cea8c15a4b9b0324561f629ff13aff4522f8a925671dfb8650256f7e68692d","timestamp":"0x180509c0e87","transactions_root":"0xf908c0afd0650812557edf3c346ad0f5ae9a44c24cc6cd58db4e6171631f7bbb","version":"0x0"},"id":42}
```

**ETH Indexer**

**Request**

```
curl -X POST https://mainnet.eth.dev/indexer 7 -H 'content-type:application/json' -d'{"id":42,"jsonrpc":"2.0","method":"get_tip"}'
```

**Response**

```
{"jsonrpc":"2.0","result":{"block_hash":"0xc1d86e3986679d32090240f3e6abb641fe9d898976f8adb204b77d34ce11f3ec","block_number":"0x6a37db"},"id":42}
```

**Community Nodes**

If you do not want to deploy your own ETH nodes or are in the testing phase, you can use the public nodes provided by the community (not recommended for long-term use):.

> ****[**Free ETH Nodes**](../.dao-open-source-library/back-end.md)****

**Next step**

* If you need front-end access to .dao, please read [Front-end access](../.dao-open-source-library/back-end.md)
* If you need to see design guidelines, please see Design, [Interaction Guidelines](../.dao-open-source-library/back-end.md)
