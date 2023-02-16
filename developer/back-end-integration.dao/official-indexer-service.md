# Official Indexer Service

Given the stability of the service and the individual needs of the business, we recommend building your own indexer service and keeping up with the official .dao iterations. (Yes! Decentralization!) .

dao team provides a public Indexer with limited functionality for developers to develop and debug in the early stages.

**Full-featured Indexer**

```
https://indexer-v1.didao.id
```

This service can query all data. But as always, we recommend developers to build their own Indexer.

```
https://indexer-not-use-in-production-env.didao.id
```

This service can query all data, but as described in its domain name, it is not recommended that developers use this Indexer in a production environment

**Basic Indexer**

```
https://indexer-basic.didao.id
```

This service can only query account information and reverse resolution records. The specific interface is as follows:

* **das\_serverInfo**
* **das\_reverseRecord**
* **das\_accountInfo**
* **das\_accountList**
* **das\_accountRecords**

**Frequency limitation**

There are no frequency restrictions on either public Indexer, so please use them as needed. However, if the frequency exceeds the capacity of the service, the caller may face the possibility of IP blocking.
