# .dao namespace

dao is the core of .dao, and the power of .dao extends from the flexibility of parsing records. A parsed record is a key-value key-value pair, and .dao supports an infinite number of parsed records. As shown above, different applications will read different parse records to do different jobs. Therefore, the namespace management of the key of the parsed record is particularly important. The namespace usage specification is essentially a protocol that can be followed to enable good collaboration between applications.

### Namespace

The key for parsing records is a hierarchical structure separated by address.btc, profile.twitter, custom\_key.bitcc \_config, etc. Among them, address, profile, custom\_key are called first-level namespaces; btc , twitter, bitcc\_config are called second-level namespaces..dao has strict constraints on the use of namespaces at the contract level and currently provides four first-level namespaces.

* **address**
* **profile**
* **dweb**
* **custom\_key**

> **View all .dao namespaces (please add link 🔗)**

**Attention**

The .dao contract does not verify the legitimacy of the value of the parsed record, .dao just provides a convention. For example, in general, users will set the address.btc value to a BTC address. But when using this value, applications should check whether this value is really a valid BTC address.\


### First-level namespace addition

Currently .dao only provides address, profile, dweb, custom\_key four first-level namespaces, but this is not the final result. The .dao team will gradually increase the first-level namespace according to the situation. At the same time, we also need developers in the community to provide us with effective suggestions. If you think some namespaces should be added to make applications work better together. You can send us 🔗 [**Issues** ](https://github.com/DIDAO-id/ENS-CN)in Github.

<figure><img src="https://bytedancecampus1.feishu.cn/space/api/box/stream/download/asynccode/?code=MDFkMzdjOWU4NzVlZmUwZjBkZGFlYzI0NjVjOTZlY2Ffd05yT2c3MUxJT3NwbVR4QzhITjZRakFiajdPQmhBcEpfVG9rZW46Ym94Y25scUhhTUZYbllUM3dqVmYzaGxjQlRoXzE2Nzc1ODQxODA6MTY3NzU4Nzc4MF9WNA" alt=""><figcaption></figcaption></figure>

\
Parsing records is the core of .dao, and the powerful expansion ability of .dao also comes from the flexibility of parsing records. A parsing record is a key-value Attribute-Value Pair, and .dao supports countless parsing records. As shown in the figure above, different applications will read different parsing records to complete different tasks. Therefore, the namespace management of the key of the parsing record is particularly important. The namespace usage specification is essentially a protocol. Following this protocol allows good collaboration between applications.
