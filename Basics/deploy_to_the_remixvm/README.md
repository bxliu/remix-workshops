

在之前的章节中，我们编译了一个合约——也就是说，solidity 代码已被转换为以太坊虚拟机（Ethereum Virtual Machine, EVM）字节码的小块。

现在我们将该代码放在测试区块链上。

1. 点击部署和运行图标 <img src="images/run.png" alt="run" style="zoom: 67%;" />。
2. 从环境下拉菜单中选择 **JavaScript VM**。
3. 点击部署按钮（或展开视图中的交易按钮）。
4. 您已将合约部署到 JSVM——在浏览器窗口内运行的模拟区块链。JSVM 是最简单、最快和最不现实的测试链。它与 Ganache 非常相似——如果您熟悉 Truffle。这不太现实，因为您不需要批准每笔交易。

您可以部署到其它测试链或主网。但要做到这一点，您需要连接到另一个**环境**——例如 Injected Web3 或 Web3 Provider。当您使用 Injected Web3 ——您需要安装 MetaMask。MetaMask 是一个钱包，它是一个浏览器插件。

