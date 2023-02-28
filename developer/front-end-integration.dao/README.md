# Front-end integration

### Das-sdk-js

🔗 [**Das-sdk-js** ](https://github.com/DIDAO-id/ENS-CN)is an npm package that encapsulates JSON - RPC calls to the indexer.The Dapp only needs to integrate the SDK and call the corresponding interface (data by .dao 🔗 [**das-account-indexer** ](https://github.com/DIDAO-id/ENS-CN)) to get the required data.

> Note that after the application gets the value of the data set by the user, it needs to verify the validity of its value

> [**Das-sdk-js doc**](https://github.com/DIDAO-id/ENS-CN)



### Dependence/support

Using this SDK depends on the JSON - RPC service provided by [**das-account-indexer** ](https://github.com/DIDAO-id/ENS-CN).We strongly recommend that developers build their own .dao Indexer, but developers can also use the official .dao Indexer service for development and testing during the development stage.See also:

> [**Official Indexer Service**](https://github.com/DIDAO-id/ENS-CN)



### Example of use

```Plaintext
import Das from 'das-sdk'

const das = new Das({
  url: 'https://indexer-v1.didao.id',
})

das.records('dasloveckb.dao').then(console.log)
```

**Output**

```Plaintext
[{
  key: 'address.eth',
  label: 'coinbase',
  value: '0x1234...4567',
  ttl: 300,
  avatar: 'https://display.didao.id/identicon/dasloveckb.dao'
}, {
  key: 'address.eth',
  label: 'onchain',
  value: '0x2345...6789',
  ttl: 300,
  avatar: 'https://display.didao.id/identicon/dasloveckb.dao'
}]
```

**Next step**

* If you need backend access to .dao, please read [**Backend access**](https://app.skiff.com/file/f936f5ae-0627-4b3e-bf4b-39bfc1af15d0)
* If you need to see the design guidelines, please see [**the design guidelines**](https://github.com/DIDAO-id/ENS-CN)

