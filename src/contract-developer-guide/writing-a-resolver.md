# 编写解析器

解析器在 [EIP137](https://github.com/ethereum/EIPs/issues/137) 中指定。解析器必须实现以下方法：

```文本
函数 supportsInterface(bytes4 interfaceID) 常量返回 (bool)；
```

`supportsInterface` 在 [EIP165](https://github.com/ethereum/EIPs/issues/165) 中定义，并允许调用者确定解析器是否支持特定记录类型。记录类型被指定为解析器必须一起实现的一组一个或多个方法。当前定义的记录类型包括：

| 记录类型 | 函数\(s\) | 接口编号 | 定义于 |
| :--- | :--- | :--- | :--- |
| 以太坊地址 | 地址 | 0x3b3b57de | [EIP137](https://github.com/ethereum/EIPs/issues/137) |
| ENS 名称 | 姓名 | 0x691f3431 | [EIP181](https://github.com/ethereum/EIPs/issues/181) |
| ABI 规范 | 阿比 | 0x2203ab56 | [EIP205](https://eips.ethereum.org/EIPS/eip-205) |
| 公钥 | 公钥 | 0xc8690233 | [EIP619](https://github.com/ethereum/EIPs/pull/619) |
| 文字记录 | 文字 | 0x59d1d43c | [EIP634](https://eips.ethereum.org/EIPS/eip-634) |
| 内容哈希 | 内容哈希 | 0xbc1c58d1 | |

`supportsInterface` 还必须为 interfaceID 值 0x01ffc9a7 返回 true，这是 `supportsInterface` 本身的接口 ID。

此外，`content` 接口被用作 Swarm 哈希的事实标准，接口 ID 为 0xd8389dc5。新的实现应该改用 `contenthash`。

## 示例解析器

仅支持 addr 类型的简单解析器可能如下所示：

```文本
合同 SimpleResolver {
    函数 supportsInterface(bytes4 interfaceID) 常量返回 (bool) {
        返回接口 ID == 0x3b3b57de；
    }

    函数地址（bytes32 nodeID）常量返回（地址）{
        返回地址（这个）；
    }
}
```

这个简单的解析器总是返回它自己的地址作为所有查询的答案。实用的解析器可以使用他们希望的任何机制来确定返回什么结果，尽管它们应该是恒定的，并且应该尽可能减少气体使用。