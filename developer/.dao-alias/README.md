# .dao alias

### Set .dao Alias

Now the .dao alias supports addresses such as ETH/BSC/TRX/Polygon.Users can visit [**the .dao Alias App** ](https://didao.id/)and log in to the wallet, after which they can set the .dao alias of their corresponding address.

> [.dao Alias Setup Guide](https://didao.id/)

### Parse .dao aliases

#### **Front end analysis**

To frontend the .dao alias, use [**das-sdk-jsopen in new window** ](https://github.com/DIDAO-id/ENS-CN).

> See [**front-end integration.dao for details**](https://app.skiff.com/file/d853dab0-e75d-4d87-88c2-8e77f10ce95f)

After that, you only need to call the reverseRecord method and pass in relevant parameters to complete the front-end parsing of the .dao alias.**Example**

```Plaintext
const account = await das.reverseRecord({
  type: 'blockchain',
  key_info: {
    coin_type: '60',
    chain_id: '1',
    key: '0x1d643fac9a463c9d544506006a6348c234da485f'
  }
})

console.assert(account === 'imac.dao')
```

> Specific parameter values see the following [**parameter details**](https://app.skiff.com/file/d8eb025f-4341-4acc-b714-55b30c304536)



#### backend parsing

For the backend to resolve the .dao alias, you first need to deploy a [**das-account-indexeropen in new window** ](https://github.com/DIDAO-id/ENS-CN).

> See [**backend integration.dao for details**](https://app.skiff.com/file/69fe10fa-8fdd-44bc-a884-89168979ce4f)

After that, you only need to call the das\_reverseRecord method and pass in relevant parameters to complete the resolution of the backend's .dao alias.**ExampleCall**

```Plaintext
curl -X POST https://indexer-basic.didao.id -d'{"jsonrpc": "2.0","id": 1,"method": "das_reverseRecord","params": [{"type": "blockchain","key_info":{"coin_type": "60","chain_id": "1","key": "0x1d643fac9a463c9d544506006a6348c234da485f"}}]}
```

**response**

```Plaintext
{"id":1,"jsonrpc":"2.0","result":{"errno":0,"errmsg":"","data":{"account":"imac.dao"}}}
```

> Specific parameter values see the following [**parameter details**](https://app.skiff.com/file/d8eb025f-4341-4acc-b714-55b30c304536)

\


#### Detailed explanation of parameters

Whether it is a front-end function call or a back-end JSON - RPC, the parameters passed in are the same:

```Plaintext
{
  type: 'blockchain',
  key_info: {
    coin_type: '60',
    chain_id: '1',
    key: '0x1d643fac9a463c9d544506006a6348c234da485c'
  }
}
```

The values of each field are as follows:**type**The type of data that needs to be parsed, currently only supports blockchain, will support OpenPGP, SSL in the future.**coin\_type**The coin\_type that needs to be resolved follows the [**SLIP-0044 specification** ](https://github.com/satoshilabs/slips/blob/master/slip-0044.md).Here are some common values:

| coin\_type | 符号    | 链                   |
| ---------- | ----- | ------------------- |
| 0          | BTC   | Bitcoin             |
| 3          | DOGE  | Dogecoin            |
| 60         | ETH   | Ethereum            |
| 966        | MATIC | Matic               |
| 9006       | BSC   | Binance Smart Chain |

> See [**SLIP-0044 specification for details** ](https://github.com/satoshilabs/slips/blob/master/slip-0044.md).

[**#**](https://docs.did.id/zh/developers/dotbit-alias#chain-id)**chain\_id**If it is an EVM-compatible chain, you can further distinguish specific chains by chain\_id, such as ETH, BSC, HECO.The following are common values:

| chain\_id | 符号    | 链                   |
| --------- | ----- | ------------------- |
| 1         | ETH   | Ethereum            |
| 56        | BNB   | Binance Smart Chain |
| 137       | MATIC | Polygon             |

> Data sourced from [**Chainlist**](https://chainlist.org/)

**key**The specific value of the data to be parsed, such as the user's ETH address 0x1d643fac9a463c9d544506006a6348c234da485c.\
\
**".Dao Alias" is a feature introduced by .dao that gives you a globally unique alias for any address you own.**For example, you can give your BTC address: "bc123... 456" an alias of "mybtc.dao". This way, when other developers want to show their users the "bc123... 456" address, they can also show the alias of "mybtc.dao" so that users can verify the owner of the address.For more introductions, please refer to the .dao official website and articles:

> [**.Dao Alias official website**](https://didao.id/) [**Here comes the .dao alias**](https://didao.id/)
