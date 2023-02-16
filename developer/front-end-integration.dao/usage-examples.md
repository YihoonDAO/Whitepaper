# Usage examples

```
import Das from 'das-sdk'

const das = new Das({
  url: 'https://indexer-v1.didao.id',
})

das.records('dasloveckb.dao').then(console.log)
```

**Output**

```
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

If you need back-end access to .dao, please read [Back-end access](../../overview/faq/registration-related/can-i-register-a-sub-account.md)

If you need to see the design guide, please see [Design Guide](../../overview/faq/registration-related/can-i-register-a-sub-account.md)
