# Private Key Management

In the process of actual Dapp development and use, users may lose their private keys. With the simple public-private key pair structure of traditional blockchain accounts, losing the private key means losing the account privileges, which means permanently losing the assets they belong to, an unbearable pain.

In the case of Dapp with DID account structure, when such a situation occurs, the user can generate a new public-private key pair locally and initiate on-chain change operation through the management account to replace the original public key (the private key is still in the local area), thus completing the re-binding of the new public-private key pair with the DID account and regaining ownership of the assets, which is safe and secure.
