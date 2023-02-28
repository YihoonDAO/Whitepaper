# Application development based on .dao

There are several ideas for developing applications based on .dao.

Consider .dao accounts as a practical NFT asset and develop a trading/auction/rental marketplace for .dao

dao account as a public key-value database that can only be modified by the user and can store any type of parsed records. Developers can build applications based on this.



### Preparations

Different types of applications require different preparations.Develop a trading/auction/leasing marketplace for .dao as a useful NFT asset. Here's what you need to know:1. Ethereum's basic principles, data structures and transaction structures (learn Ethereum)2. Basic principles, data structures and transaction structures of .dao (learn .dao)If you develop an application based on the parsing record of a .dao account, you don't need to know the Nervos CKB and the technical details of .dao. Just learn how to use das-account-indexer or das-sdk-js to get the parsing record of an account, check if an address holds a .dao account, and understand the namespace specification for its parsing record.\


### Future .dao applications

We believe the following .dao-based applications should emerge in the future:1. Send end-to-end Encrypted Messages using a .dao account2. Aggregate reputations across multiple chains using .dao accounts3. Use your .dao account to log in to the centralized service4. Decentralized personal homepage/social network based on .dao account\
\


### Application example: dao.cc - Decentralized Personal Homepage

🔗 https://didao.id It is typical to think of a .dao account as a .dao application that exposes key-value data. dao.cc can be seen as a decentralized version of LinkTree or a decentralized personal homepage. Unlike other personal homepage products, the information displayed on the homepage provided by dao.cc is centrally stored. There are and only .dao account owners who can modify, dao.cc cannot delete your personal homepage.If Alice has alice.dao and adds her connections to various social networks to the resolution record. dao.cc will display these links in a very beautiful style that other users can access through alice.dao.cc. The performance of dao.cc is completely controlled by Alice by setting the resolution record. For example:

1. Alice can decide whether to display your decentralized home page in daytime or nighttime mode by setting the resolution record custom\_key.daocc \_theme value to light or dark.
2. Alice can set the parsing record custom\_key.daocc \_redirect value to Alice's personal website link. This way, when someone visits alice.dao.cc, the page will automatically retarget Alice's personal website.

These functions are realized because dao.cc responding based on Alice's parsed records. In the future, dao.cc can also present all of Alice's NFT based on Alice's parsed records. alice.dao.cc is a true decentralized personal homepage belonging to Alice.🔗 dao.cc use doc🔗

![](https://bytedancecampus1.feishu.cn/space/api/box/stream/download/asynccode/?code=NjI5ZjQxMGM0YWFjY2E3ZjgxZGI4NGZjNmFjZTI5NDdfaThsOWN3YzhqblZxYjZYeFNxb004VWlTSkJFZnNzTHdfVG9rZW46Ym94Y245NWxCQ0FEMG5aUUtpbWdiM1hrN3poXzE2Nzc1ODM2NjQ6MTY3NzU4NzI2NF9WNA)

There are several ideas for developing applications based on .dao:

1. Develop a trading/auction/leasing marketplace for .dao as a practical NFT asset
2. Think of a .dao account as a public, user-modifiable key-value database that can store any type of resolution record. Developers can build applications on top of this.
