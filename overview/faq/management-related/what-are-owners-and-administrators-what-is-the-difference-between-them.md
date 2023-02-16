# What are owners and administrators? What is the difference between them?

Owner, each account has an owner, who owns the .dao account and can modify the owner and administrator.

Administrator, each account has an administrator, who owns the .dao account and can modify the account's resolution records.

The design of owner and administrator is practicing the idea of separation of ownership and management. Modifying the resolution record is a high-frequency operation, while modifying the ownership is a low-frequency operation. The high-frequency operation will then use the private key frequently, which increases the risk of losing the private key. This separation design allows users to still have ownership of the account when the administrator's private key is lost. The owner and administrator can be the same address or different addresses. However, we highly recommend using different addresses for the owner and administrator.\
\
[Translated with DeepL](https://www.deepl.com/translator?utm\_source=macos\&utm\_medium=app\&utm\_campaign=macos-share)
