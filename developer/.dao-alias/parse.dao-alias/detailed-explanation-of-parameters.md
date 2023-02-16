# Detailed explanation of parameters

Whether it is a front-end function call or a back-end JSON-RPC, the parameters passed in are the same: the

```
{
  type: 'blockchain',
  key_info: {
    coin_type: '60',
    chain_id: '1',
    key: '0x1d643fac9a463c9d544506006a6348c234da485c'
  }
}
```

The values of each field are taken as follows:

**type**

The type of data to be parsed, only blockchain is supported now, OpenPGP, SSL, etc. will be supported in the future.

**coin\_type**

The coin\_type of the address to be parsed, following the [SLIP-0044 specification.](../../../joint-construction/promoters.md)

The following are some common values:

| coin\_type | Symbols | Chain               |
| ---------- | ------- | ------------------- |
| 0          | BTC     | Bitcoin             |
| 3          | DOGE    | Dogecoin            |
| 60         | ETH     | Ethereum            |
| 966        | MATIC   | Matic               |
| 9006       | BSC     | Binance Smart Chain |

> [See the SLIP-0044 specification for details.](../../../joint-construction/promoters.md)
>
>
>
> **#chain\_id**
>
> In the case of EVM-compatible chains, the chain\_id can be used to further distinguish specific chains, such as ETH, BSC, HECO.
>
> The following values are commonly taken:
>
> >

| chain\_id | Symbols | Chain               |
| --------- | ------- | ------------------- |
| 1         | ETH     | Ethereum            |
| 56        | BNB     | Binance Smart Chain |
| 137       | MATIC   | Polygon             |

[Data from Chainlist](../../../joint-construction/promoters.md)

**key**

The specific value of the data that needs to be parsed, such as the user's ETH address 0x1d643fac9a463c9d544506006a6348c234da485c
