# 编写注册器

ENS 中的注册商只是拥有名称的任何合约，并根据合约代码中定义的一组规则分配其子域。下面演示了一个简单的先到先得合同：

```text
contract FIFSRegistrar {
    ENS ens;
    bytes32 rootNode;

    function FIFSRegistrar(address ensAddr, bytes32 node) {
        ens = ENS(ensAddr);
        rootNode = node;
    }

    function register(bytes32 subnode, address owner) {
        var node = sha3(rootNode, subnode);
        var currentOwner = ens.owner(node);

        if (currentOwner != 0 && currentOwner != msg.sender) throw;

        ens.setSubnodeOwner(rootNode, subnode, owner);
    }
}

您可能希望设置自定义规则来为您的用户分配新名称；你设定的规则完全取决于你。

您还应该记住，只要您保留父名称的所有权（直接或通过其他合同），您的用户就不能保证您不会收回他们名称的所有权并改变他们的决定。您可能希望考虑将名称的所有权提交给限制您控制它的能力的合同。有关此示例，请参阅 [ENSNow](https://github.com/ensdomains/subdomain-registrar)。  