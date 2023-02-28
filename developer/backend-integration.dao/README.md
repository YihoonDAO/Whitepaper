# Backend integration.dao

### Official Indexer Service

Considering the stability of the service and the personalized needs of the business, we suggest to build your own indexer service and follow up the iterative update of the .dao official. (Yes! Decentralization!).But at the same time, the .dao team provides a public Indexer with limited functionality for developers to develop and debug at an early stage.\


**Full Feature Indexer**

```Plaintext
https://indexer-v1.didao.id
```

This service can query all data. But as always, we recommend developers to build their own Indexer.

```Plaintext
https://indexer-not-use-in-production-env.didao.id
```

This service can query all the data you need, but it is not recommended that developers rely on this indexer in production environments.**Basic Indexer**

```Plaintext
https://indexer-basic.didao.id
```

This service can only query account info and reverse parsing records. The specific interface is as follows:

* das\_serverInfo
* das\_reverseRecord
* das\_accountInfo
* das\_accountList
* das\_accountRecords

**Frequency limit**At present, neither of the two public Indexers has a limit on the frequency of use, but you are still requested to use it as needed. If the frequency exceeds the service carrying capacity, the caller may be blocked ip.\


### Unifra Indexer Service

[**Unifra** ](https://unifra.io/)is a professional Web3 infrastructure service provider.Unifra provides high-performance and highly reliable .dao indexer services for the .dao community. If developers do not want to build the .dao Indexer themselves, we recommend using Unifra's services to save you a lot of development time.[**Unifra.dao Indexer doc**](https://unifra.io/)\


### das-account-indexer

If the developer needs to access .dao in the backend service, then [**das-account-indexer** ](https://github.com/DIDAO-id/ENS-CN)will be your choice.It continuously reads data from the EVM chain through the EVM node, and the parsed data will be stored in the local database (RocksDB), and provides high-performance JSON-RPC services for business to read the parsed data of .dao.

> It is also the backend service that [**das-sdk-js** ](https://github.com/DIDAO-id/ENS-CN)depends on.Deploying Indexer requires reliance on EVM nodes, see EVM [**Nodes and** ](https://github.com/DIDAO-id/ENS-CN)[EVM Indexer](https://didao.did/)[**Das-account-indexer API** ](https://github.com/DIDAO-id/ENS-CN)**doc**

\
**Use example**The following is obtaining basic user information as an example to illustrate the usage of .dao Indexer.\
**request**

```Plaintext
curl -X POST https://indexer-basic.didao.id -d'{"jsonrpc": "2.0","id": 1,"method": "das_accountInfo","params": [{"account":"phone.bit"}]}'
```

**response**

```Plaintext
{
  "errno": 0,
  "errmsg": "",
  "data": {
    "out_point": {
      "tx_hash": "0xabb6b2f502e9d992d00737a260e6cde53ad3f402894b078f60a52e0392a17ec8",
      "index": 0
    },
    "account_info": {
      "account": "phone.dao",
      "account_id_hex": "0x5f560ec1edc638d7dab7c7a1ca8c3b0f6ed1848b",
      "next_account_id_hex": "0x5f5c20  f6cd95388378771ca957ce665f084fe23b",
      "create_at_unix": 1626955542,
      "expired_at_unix": 1658491542,
      "status": 1,
      "das_lock_arg_hex": "0x0559724739940777947c56c4f2f2c9211cd5130fef0559724739940777947c56c4f2f2c9211cd5130fef",
      "owner_algorithm_id": 5, // 3: eth personal sign, 4: tron sign, 5: eip-712
      "owner_key": "0x59724739940777947c56c4f2f2c9211cd5130fef",
      "manager_algorithm_id": 5,
      "manager_key": "0x59724739940777947c56c4f2f2c9211cd5130fef"
    }
  }
}
```



### EVM Node and EVM Indexer

The data of .dao is stored on the [**Ethereum Mainnet** ](https://ethereum.org/)chain, so developers who build their own .dao Indexer need to deploy the corresponding EVM node and EVM Indexer.\
**Deployment method**For specific deployment methods, please refer to ETH official guide:[**ETH Node operation guide**](https://ethereum.org/en/) [ETH Node JSON - RPC protocol](https://ethereum.org/en/) [ETH Indexer Operating Guidelines](https://ethereum.org/en/) [ETH Indexer JSON - RPC Protocol](https://ethereum.org/en/)**Usage exampleEVM noderequest**

```Plaintext
curl -X POST https://mainnet.eth.dev/rpc -H 'content-type:application/json' -d'{"id":42,"jsonrpc":"2.0","method":"get_tip_header","params":[]}'
```

**response**

```Plaintext
{"jsonrpc":"2.0","result":{"compact_target":"0x190a0088","dao":"0xac8ffb215ff346419e9af198c38b26000e53d3ad69969403002bdb8b29d71a07","epoch":"0x41c03f40014bb","extra_hash":"0x0000000000000000000000000000000000000000000000000000000000000000","hash":"0x13251222fc73918701aafc8edbb08057dde7ca95d9709990616fb8802b73af9d","nonce":"0x990fa3bc251b0000000000086019030c","number":"0x6a37e1","parent_hash":"0x4ea3a7a40877471c9a6b98306fbe453007a5306887ff8a05ab5393166f7d0f86","proposals_hash":"0x91cea8c15a4b9b0324561f629ff13aff4522f8a925671dfb8650256f7e68692d","timestamp":"0x180509c0e87","transactions_root":"0xf908c0afd0650812557edf3c346ad0f5ae9a44c24cc6cd58db4e6171631f7bbb","version":"0x0"},"id":42}
```

**ETH Indexer**

**request**

```Plaintext
curl -X POST https://mainnet.eth.dev/indexer 7 -H 'content-type:application/json' -d'{"id":42,"jsonrpc":"2.0","method":"get_tip"}'
```

**response**

```Plaintext
{"jsonrpc":"2.0","result":{"block_hash":"0xc1d86e3986679d32090240f3e6abb641fe9d898976f8adb204b77d34ce11f3ec","block_number":"0x6a37db"},"id":42}
```

**Community node**If you don't want to deploy the EVM node yourself or are in the testing phase, you can use the public node provided by the community (not recommended for long-term use):

> [**Free EVM Node**](https://ethereum.org/en/)

**Next step**

* If you need front-end access to .dao, please read [**Front-end access**](https://app.skiff.com/file/d4bbe261-5c99-45f3-b97a-82dbe430413a)
* If you need to view the design guidelines, please view the [**design, interaction guidelines**](https://docs.did.id/zh/developers/design-guide.html)



### UI Components

For common front-end UI components, such as profile photo and account cards, we provide Vue components for developers to call directly, which can obtain the same visual style as the official.

> [**Das-ui-shared component library**](https://github.com/DIDAO-id/ENS-CN)
