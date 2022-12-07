# 介绍

以太坊名称服务 （ENS） 是基于以太坊区块链的分布式、开放且可扩展的命名系统。

ENS的工作是将人类可读的名称（如“alice.eth”）映射到机器可读的标识符，例如以太坊地址，其他加密货币地址，内容哈希和元数据。ENS 还支持“反向解析”，可以将元数据（如规范名称或接口描述）与以太坊地址相关联。

ENS的目标与DNS（互联网域名服务）相似，但由于以太坊区块链提供的功能和限制，其架构明显不同。与DNS一样，ENS在一个名为域名的点分隔分层名称系统上运行，域名所有者对子域拥有完全控制权。

顶级域名，如“.eth”和“.test”，由称为注册商的智能合约拥有，这些合约指定了管理其子域名分配的规则。任何人都可以通过遵循这些注册商合约规定的规则，获得域名的所有权供自己使用。ENS 还支持导入用户已拥有的 DNS 名称，以便在 ENS 上使用。

由于 ENS 的分层性质，任何拥有任何级别域的人都可以根据需要为自己或他人配置子域。例如，如果Alice拥有“alice.eth”，她可以创建“pay.alice.eth”并根据需要进行配置。

ENS部署在以太坊主网络和几个测试网络上。如果使用库，例如 [ensjs](https://www.npmjs.com/package/@ensdomains/ensjs) Javascript库或终端用户应用程序，它将自动检测您正在与之交互的网络，并在该网络上使用ENS部署。

您现在可以通过使用[ENS 管理应用程序](https://app.ens.domains)亲自试用ENS，或使用[我们主页](https://ens.domains)上许多已启用应用程序中的任意一个。

## ENS架构

ENS 有两个主要组成部分：[注册表](contract-api-reference/ens.md) 和 [解析器](contract-api-reference/publicresolver.md)。

![](<.gitbook/assets/ens-architecture (1).png>)

ENS 注册表由一个智能合约组成，该合约维护所有域和子域的列表，并存储有关每个域和子域的三个关键信息：

> * 域名的所有者
> * 域名的解析程序
> * 域名下所有记录的缓存生存时间

域的所有者可以是外部帐户（用户）或智能合约。注册商只是一个智能合约，它拥有一个域，并向遵循合约中定义的一组规则的用户颁发该域的子域。

ENS 注册管理机构中域名的所有者可以：

> * 设置域名的解析程序和 TTL
> * 将域名的所有权转移到另一个地址
> * 更改子域名的所有权

ENS 注册表故意简单明了，它的存在只是为了从一个名称映射到负责它的解析程序。

解析器负责将名称转换为地址的实际过程。任何实施相关标准的合约都可以充当 ENS 中的解析器。通用解析程序实现是为要求简单的用户提供的，例如为名称提供不经常更改的地址。

每种记录类型（加密货币地址、IPFS内容哈希等）都定义了解析器必须实现的一个或多个方法，以便提供此类记录。可以随时通过 EIP 标准化流程定义新的记录类型，无需更改 ENS 注册表或现有解析器即可支持它们。

在 ENS 中解析名称分为两个步骤：首先，询问注册表哪个解析程序负责该名称，其次，向该解析程序询问查询的答案。

![](https://lh5.googleusercontent.com/\_OPPzaxTxKggx9HuxloeWtK8ggEfIIBKRCEA6BKMwZdzAfUpIY6cz7NK5CFmiuw7TwknbhFNVRCJsswHLqkxUEJ5KdRzpeNbyg8\_H9d2RZdG28kgipT64JyPZUP--bAizozaDcxCq34)

在上面的例子中，我们试图找到“foo.eth”指向的以太坊地址。首先，我们询问注册管理机构哪个解析器负责“foo.eth”。然后，我们向该解析器查询 'foo.eth' 的地址。

### 名称哈希

智能合约中的资源限制使得直接与人类可读名称的交互效率低下，因此ENS纯粹使用固定长度的256位加密哈希。为了从名称派生哈希，同时仍保留其层次结构属性，使用称为 Namehash 的过程。例如，“alice.eth”的namehash是0x787192fc5378cc32aa956ddfdedbf26b24e8d78e40109add0eea2c1a012c3dec;这是ENS内部专门使用的名称的表示形式。

Namehash 是一个递归过程，可以为任何有效的域名生成唯一的哈希。从任何域的名称哈希开始 - 例如，“alice.eth” - 可以派生任何子域的名称哈希 - 例如“iam.alice.eth” - 而无需知道或处理原始人类可读的名称。正是此属性使 ENS 能够提供分层系统，而无需在内部处理人类可读的文本字符串。

在使用 namehash 进行哈希处理之前，首先使用称为 UTS-46 规范化的过程对名称进行规范化。这可确保对大写和小写名称等效处理，并禁止使用无效字符。任何对名称进行哈希处理和解析的操作都**必须**首先对其进行规范化，以确保所有用户都能获得一致的 ENS 视图。

有关 namehash 和规范化如何工作原理的详细信息，请参阅开发者文档中的[名称处理](contract-api-reference/name-processing.md)。

## 入门

ENS 为各种受众提供了文档，包括 dapp 开发人员和合约开发人员，以及参考文档。

#### 我是一名 dapp 开发者，想要向我的 dapp 添加 ENS 支持

查看 dapp 开发者指南，从[ENS 启用您的 Dapp](dapp-developer-guide/ens-enabling-your-dapp.md)。您需要从众多可用的[ENS 文档](dapp-developer-guide/ens-libraries.md)中选择一个来开始使用ENS。

#### 我是一名合约开发者，想通过我的合约代码与 ENS 交互

查看合约开发者指南，从[解析链上的名称](contract-developer-guide/resolving-names-on-chain.md)开始。您也可以[编写自己的解析器](contract-developer-guide/writing-a-resolver.md)（自定义查找名称的过程），或您自己的[注册器]（(contract-developer-guide/writing-a-registrar.md)（自定义注册新名称的过程）。

#### 我想要 ENS 智能合约的参考文档

查看合约 API 参考。我们有 ENS 核心合约的参考文档，[注册表](contract-api-reference/ens.md)，[解析器](contract-api-reference/publicresolver.md)，以及常用的注册器，如[测试注册商](contract-api-reference/testregistrar.md)、[反向注册器](contract-api-reference/reverseregistrar.md)，和[.eth注册商](contract-api-reference/.eth-permanent-registrar/)。
