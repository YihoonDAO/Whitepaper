# 在链上解析名称

用于链上解析的 Solidity 库尚不可用，但 ENS 解析非常简单，无需库即可轻松完成。首先，我们定义一些精简的接口，只包含我们需要的方法：

```文本
abstract contract ENS {
    function resolver(bytes32 node) public virtual view returns (Resolver);
}

abstract contract Resolver {
    function addr(bytes32 node) public virtual view returns (address);
}
```

对于解析，只需要ENS合约中的`resolver`函数即可；其他方法允许从拥有名称的合约中查找所有者和更新 ENS。

使用这些定义，在给定节点哈希的情况下查找名称非常简单：

```文本
contract MyContract {
    // Same address for Mainet, Ropsten, Rinkerby, Gorli and other networks;
    ENS ens = ENS(0x00000000000C2E074eC69A0dFb2997BA6C7d2e1e);

    function resolve(bytes32 node) public view returns(address) {
        Resolver resolver = ens.resolver(node);
        return resolver.addr(node);
    }
}
```

虽然合约可以将人类可读的名称处理成节点哈希，但我们强烈建议改用节点哈希，因为它们使用起来更容易、更高效，并且允许合约离开规范化的复杂工作在区块链之外为他们的调用者命名。在合约总是解析相同名称的情况下，这些名称可以转换为节点哈希并作为常量存储在合约中。

