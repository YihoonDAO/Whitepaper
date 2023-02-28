# das-account-indexer

If developers need to access .dao on the backend, then [das-account-indexer](../.dao-open-source-library/back-end.md) is the right choice for you.

It continuously reads data from the EVM chain through the EVM node, parses it and stores it in a local database (RocksDB), and provides a high-performance JSON-RPC service for the business to read parsed data from .dao.

It is also the backend service on which [das-sdk-js](../.dao-open-source-library/back-end.md) relies.

Deploying Indexer depends on EVM nodes, see EVM Nodes [and EVM Indexer](../.dao-open-source-library/back-end.md)

[das-account-indexer](../.dao-open-source-library/back-end.md)[ API documentation](../.dao-open-source-library/back-end.md)

**Usage examples**

The following is an example of how to use the .dao Indexer to get basic information about a user.

**Requesting**

```
curl -X POST https://indexer-basic.didao.id -d'{"jsonrpc": "2.0","id": 1,"method": "das_accountInfo","params": [{"account":"phone.bit"}]}'
```

**Response**

```
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
