# 介绍

以太坊名称服务 （ENS） 是基于以太坊区块链的分布式、开放且可扩展的命名系统。

ENS的工作是将人类可读的名称（如“alice.eth”）映射到机器可读的标识符，例如以太坊地址，其他加密货币地址，内容哈希和元数据。ENS 还支持“反向解析”，可以将元数据（如规范名称或接口描述）与以太坊地址相关联。

ENS的目标与DNS（互联网域名服务）相似，但由于以太坊区块链提供的功能和限制，其架构明显不同。与DNS一样，ENS在一个名为域名的点分隔分层名称系统上运行，域名所有者对子域拥有完全控制权。

顶级域名，如“.eth”和“.test”，由称为注册商的智能合约拥有，这些合约指定了管理其子域名分配的规则。任何人都可以通过遵循这些注册商合同规定的规则，获得域名的所有权供自己使用。ENS 还支持导入用户已拥有的 DNS 名称，以便在 ENS 上使用。

由于 ENS 的分层性质，任何拥有任何级别域的人都可以根据需要为自己或他人配置子域。例如，如果Alice拥有“alice.eth”，她可以创建“pay.alice.eth”并根据需要进行配置。

ENS部署在以太坊主网络和几个测试网络上。如果使用库，例如 [ensjs](https://www.npmjs.com/package/@ensdomains/ensjs) Javascript库或终端用户应用程序，它将自动检测您正在与之交互的网络，并在该网络上使用ENS部署。

您现在可以通过使用[ENS 管理应用程序](https://app.ens.domains)亲自试用ENS，或使用[我们主页](https://ens.domains)上许多已启用应用程序中的任意一个。

## ENS架构

ENS 有两个主要组成部分：[注册表](contract-api-reference/ens.md)和[解析器](contract-api-reference/publicresolver.md)。

![](<.gitbook/assets/ens-architecture (1).png>)

The ENS registry consists of a single smart contract that maintains a list of all domains and subdomains, and stores three critical pieces of information about each:

> * The owner of the domain
> * The resolver for the domain
> * The caching time-to-live for all records under the domain

The owner of a domain may be either an external account (a user) or a smart contract. A registrar is simply a smart contract that owns a domain and issues subdomains of that domain to users that follow some set of rules defined in the contract.

Owners of domains in the ENS registry may:

> * Set the resolver and TTL for the domain
> * Transfer ownership of the domain to another address
> * Change the ownership of subdomains

The ENS registry is deliberately straightforward and exists only to map from a name to the resolver responsible for it.

Resolvers are responsible for the actual process of translating names into addresses. Any contract that implements the relevant standards may act as a resolver in ENS. General-purpose resolver implementations are offered for users whose requirements are straightforward, such as serving an infrequently changed address for a name.

Each record type - cryptocurrency address, IPFS content hash, and so forth - defines a method or methods that a resolver must implement in order to provide records of that kind. New record types may be defined at any time via the EIP standardization process, with no need to make changes to the ENS registry or to existing resolvers in order to support them.

Resolving a name in ENS is a two-step process: First, ask the registry what resolver is responsible for the name, and second, ask that resolver for the answer to your query.

![](https://lh5.googleusercontent.com/\_OPPzaxTxKggx9HuxloeWtK8ggEfIIBKRCEA6BKMwZdzAfUpIY6cz7NK5CFmiuw7TwknbhFNVRCJsswHLqkxUEJ5KdRzpeNbyg8\_H9d2RZdG28kgipT64JyPZUP--bAizozaDcxCq34)

In the above example, we're trying to find the Ethereum address pointed to by 'foo.eth'. First, we ask the registry which resolver is responsible for 'foo.eth'. Then, we query that resolver for the address of 'foo.eth'.

### Namehash

Resource constraints in smart contracts make interacting directly with human-readable names inefficient, so ENS works purely with fixed length 256-bit cryptographic hashes. In order to derive the hash from a name while still preserving its hierarchal properties, a process called Namehash is used. For example, the namehash of 'alice.eth' is _0x787192fc5378cc32aa956ddfdedbf26b24e8d78e40109add0eea2c1a012c3dec_; this is the representation of names that is used exclusively inside ENS.

Namehash is a recursive process that can generate a unique hash for any valid domain name. Starting with the namehash of any domain - for example, 'alice.eth' - it's possible to derive the namehash of any subdomain - for example 'iam.alice.eth' - without having to know or handle the original human-readable name. It is this property that makes it possible for ENS to provide a hierarchal system, without having to deal with human-readable text strings internally.

Before being hashed with namehash, names are first normalized, using a process called UTS-46 normalization. This ensures that upper- and lower-case names are treated equivalently, and that invalid characters are prohibited. Anything that hashes and resolves a name **must** first normalize it, to ensure that all users get a consistent view of ENS.

For details on how namehash and normalization works, see the developer documentation on [name processing](contract-api-reference/name-processing.md).

## Getting Started

ENS has documentation for a variety of audiences, including dapp developers and contract developers, as well as reference documentation.

#### I'm a dapp developer and want to add ENS support to my dapp

Check out the dapp developer guide, starting with [ENS Enabling your Dapp](dapp-developer-guide/ens-enabling-your-dapp.md). You'll want to choose one of the many available [ENS Libraries](dapp-developer-guide/ens-libraries.md) to get started working with ENS.

#### I'm a contract developer and want to interact with ENS from my contract code

Check out the Contract Developer Guide, starting with [Resolving Names On-chain](contract-developer-guide/resolving-names-on-chain.md). You can also [write your own resolver](contract-developer-guide/writing-a-resolver.md) (to customise the process of looking up names), or your own [registrar](contract-developer-guide/writing-a-registrar.md) (to customise the process of registering new names).

#### I want reference documentation for the ENS smart contracts

Check out the Contract API Reference. We have reference documentation for ENS's core contract, the [registry](contract-api-reference/ens.md), for [resolvers](contract-api-reference/publicresolver.md), and for commonly-used registrars such as the [Test registrar](contract-api-reference/testregistrar.md), [reverse registrar](contract-api-reference/reverseregistrar.md), and the [.eth registrar](contract-api-reference/.eth-permanent-registrar/).
