

库看起来像**合约**，但使用关键字 `库（library）`。

库通常是位于区块链上的有用函数的集合，任何合约都可以使用。由于该库已经部署，因此节省了许多使用它的合约的部署成本。

在以下合约中：

- 创建一个名为 `LibraryForTest` 的库。

可以将一个库与另一个合约放在同一个文件中。所以把库放在合约下面。

这个库应该有一个名为 `getFromLib` 的方法，它返回 `3`。

- 更新 `test` 合约中的 `get` 方法以使用 `LibraryForTest` 库。函数 `get` 应该返回它从 `getFromLib` 接收到的值。

------

您可以在 [Solidity 文档的这一部分](https://solidity.readthedocs.io/en/latest/contracts.html?highlight=library#libraries) 中找到有关库的更多信息。