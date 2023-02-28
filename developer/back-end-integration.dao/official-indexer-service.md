# Official Indexer Service

Considering the stability of the service and the personalized needs of the business, we suggest to build your own indexer service and follow up the iterative update of the .dao official. (Yes! Decentralization!).But at the same time, the .dao team provides a public Indexer with limited functionality for developers to develop and debug at an early stage.

\
**Full Feature Indexer**

```Plaintext
https://indexer-v1.didao.id
```

This service can query all data. But as always, we recommend developers to build their own Indexer.

```Plaintext
https://indexer-not-use-in-production-env.didao.id
```

This service can query all the data you need, but it is not recommended that developers rely on this indexer in production environments.



**Basic Indexer**

```Plaintext
https://indexer-basic.didao.id
```

This service can only query account info and reverse parsing records. The specific interface is as follows:

* das\_serverInfo
* das\_reverseRecord
* das\_accountInfo
* das\_accountList
* das\_accountRecords

****

**Frequency limit**

At present, neither of the two public Indexers has a limit on the frequency of use, but you are still requested to use it as needed. If the frequency exceeds the service carrying capacity, the caller may be blocked ip.
