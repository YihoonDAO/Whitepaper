# Namespace

The key for parsing records is a hierarchy using . Hierarchical structures such as address.btc, profile.twitter, custom\_key.bitcc\_config, etc. are separated by . Among them, address, profile, custom\_key are called primary namespaces; btc, twitter, bitcc\_config are called secondary namespaces.

dao has strict constraints on the use of namespaces at the contract level, and currently provides four first-level namespaces.

**address**

**profile**

**dweb**

**custom\_key**

[See all .dao namespaces](../../overview/faq/inviters-registrar-channel-related/what-is-an-inviter-registrar-channel.md)



**Note that**

The .dao contract does not verify the legitimacy of the value of the parsed record, .dao just provides a convention. For example, it is common for users to set the value of address.btc to a BTC address. However, when using this value, the application should check if the value is actually a legitimate BTC address.
