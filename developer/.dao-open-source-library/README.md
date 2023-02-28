# .dao open source library

### front end

#### [**das-sdk-js**](https://github.com/DIDAO-id/ENS-CN)

This is a JS SDK for parsing .dao account data.

#### [**das-ui-shared**](https://github.com/DIDAO-id/ENS-CN)

This is a repository containing several common functions and UI components that can be reused to build projects similar to the official design style of .dao.\


### Backend

#### [**das-account-indexer**](https://github.com/DIDAO-id/ENS-CN)

#### This is a simple backend JSON - RPC service that provides parsing of data and aliases for .dao accounts.

This is also the backend service that [**das-sdk-js** ](https://github.com/DIDAO-id/ENS-CN)relies on.

#### [**das-database**](https://github.com/DIDAO-id/ENS-CN)

This is a simple block parsing tool that can parse different data of .dao from the ETH public chain (such as registration, editing, trading, transfer, etc.) and store it in the local database.

#### [**das-lib**](https://github.com/DIDAO-id/ENS-CN)

This repository is the underlying dependency of many .dao open source tools. It provides many features including the following:

* Assembly transaction
* Analyze transactions
* Signature transaction
* Cache on-chain data
* .dao 的 Molecule SDK

#### [**das-register**](https://github.com/DIDAO-id/ENS-CN)

Backend for the .dao registration service. You can fork this repository to build your own .dao registration site, just like [**https://app.didao.id** ](https://didao.id/).\


### Contract

(There is no content in the contract directory for the time being, to be added)\
\
We provide a number of different open source libraries to meet the development needs of different scenarios. We also welcome the community to contribute more open source repositories to prosper the entire .dao ecosystem.

> After the brand upgrade, we will upgrade the DAS brand to .dao, but in order to maintain forward compatibility, the open source library temporarily maintains the DAS name.
