# Back-end Analysis

To resolve .dao aliases on the backend, you first need to deploy a [das-account-indexeropen in new window.](../../../joint-construction/promoters.md)

See Backend integration of [.dao for details.](../../../joint-construction/promoters.md)

After that you just need to call the <mark style="color:orange;">das\_reverseRecord</mark> method and pass in the relevant parameters to complete the backend parsing of .dao aliases.

Example

Calling the

```
curl -X POST https://indexer-basic.didao.id -d'{"jsonrpc": "2.0","id": 1,"method": "das_reverseRecord","params": [{"type": "blockchain","key_info":{"coin_type": "60","chain_id": "1","key": "0x1d643fac9a463c9d544506006a6348c234da485f"}}]}
```

Response

```
{"id":1,"jsonrpc":"2.0","result":{"errno":0,"errmsg":"","data":{"account":"imac.dao"}}}
```

> [Specific parameter values are shown below Parameter details](../../../joint-construction/promoters.md)
