# ENS 部署

如果您正在使用[ENS库](dapp-developer-guide/ens-libraries.md)，您的库将自动找到您需要的 ENS 部署。如果出于任何原因，您需要直接与 ENS 交互，此处详细介绍了当前支持的部署的详细信息。

ENS 注册表部署在 0x00000000000C2E074eC69A0dFb2997BA6C7d2e1e。在Mainnet(主网)和[Goerli](https://www.alchemy.com/overviews/migrate-from-rinkeby-to-goerli)(戈尔利)中使用相同的地址。

On mainnet, the following registrars are deployed:
在主网上，部署了以下注册商：

* .eth，使用 .eth 永久注册商。
* .xyz，通过 DNS 集成
* .luxe， 通过[自定义集成](http://join.luxe/)这允许 .luxe DNS 名称的任何所有者使用 ENS。
* .kred， 通过[自定义集成](http://domains.kred/)自动将 .kred ENS 令牌同步并更改为 DNS。
* .art，通过自定义集成

要找出每个 TLD 的合约地址，请检查 TLD 的“控制者”地址（例如：[https://app.ens.domains/name/xyz](https://app.ens.domains/name/xyz) 查找 `.xyz`

![](.gitbook/assets/screenshot-2021-05-19-at-17.54.17.png)

Ropsten 测试网络部署了 .test 注册商。该注册商允许任何人立即注册域以进行测试;这些域将持续 28 天。

此外，测试网络还部署了 .eth 注册商以进行测试。

对于其他合约地址，如root、multisig、controller、public解析器等，您可以在下面看到它们的地址[https://app.ens.domains/name/ens.eth/subdomains](https://app.ens.domains/name/ens.eth/subdomains)

早在 2020 年 2 月，ENS 注册表就迁移到新的合约地址以修补安全漏洞（阅读更多详细信息[此处](ens-migration-february-2020/technical-description.md)).以前的注册表地址是：

* Mainnet(主网)，在[0x314159265dd8dbb310642f98f50c066173c1259b](https://etherscan.io/address/0x314159265dd8dbb310642f98f50c066173c1259b#code)。
* Goerli(戈尔利)，在[0x112234455c3a32fd11230c42e7bccd4a84e02010](https://goerli.etherscan.io/address/0x112234455c3a32fd11230c42e7bccd4a84e02010)。

