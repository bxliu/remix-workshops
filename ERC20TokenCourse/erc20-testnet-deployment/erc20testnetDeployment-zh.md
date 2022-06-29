在本节中，我们将使用Metamask（一个以太坊钱包）将我们的合约部署到以太坊区块链的测试网。这个测试网的行为与真正的区块链（主网）非常相似，但不需要真正的ETH来支付交易。

### 1. 安装 Metamask
**1.1** 访问 <a href="https://metamask.io/" target="_blank">metamask.io</a>.

**1.2** 点击下载按钮，然后为你的浏览器（如Chrome）点击安装，并将该扩展添加到你的浏览器。

**1.3** 按照描述创建一个钱包。

### 2. 获取测试网代币
为了在测试网进行交易，我们需要以太坊测试网的代币，你可以从一个叫做*水龙头*（*faucet*）的东西中获得。

**2.1** 通过点击 "Ethereum Mainnetwork "下拉菜单并选择 "Ropsten Test Network "来切换你的Metamask网络。如果你没有看到任何测试网络，点击 "显示/隐藏 "链接，在设置中启用 "显示测试网络"。

**2.2** 访问 <a href="https://faucet.ropsten.be/" target="_blank">https://faucet.ropsten.be/</a>, 输入你的账户地址，并索取testnet ETH。你也可以使用其他ropsten龙头，如 <a href="https://faucet.paradigm.xyz/" target="_blank">https://faucet.paradigm.xyz/</a> 或 <a href="https://app.mycrypto.com/faucet" target="_blank">https://app.mycrypto.com/faucet</a>. 请看一下 <a href="https://ethereum.org/en/developers/docs/networks/#testnet-faucets" target="_blank">ethereum.org</a> 上列出的水龙头，以了解更多。

### 3.部署
确保EduCoin合约被编译。

**3.1.** 在Remix IDE的 "ENVIRONMENT"下的 "DEPLOY & RUN TRANSACTIONS"模块中，选择 "Injected Web3"。它将要求你连接你的账户，你应该确认。

**3.2** 部署EduCoin合约并在Metamask中确认交易。

**3.3** 你的合约应该出现在 "Deployed Contracts"部分。复制合约地址。

**3.4** 在Metamask中，点击资产，然后点击 "Import tokens"链接，并将你的合约地址粘贴到输入栏中。

你现在应该看到你的钱包里有1000个EDC的余额。

### 4. 进行交易
**4.1** 点击Metamask钱包中的身份标识（你的地址的可视化表示），创建第二个账户（账户2）。

**4.2** 复制账户2的地址。

**4.3**  切换到第一个账户（账户1）并发送250 EDC到账户2。检查账户1和账户2的余额。你可能需要为账户2再次添加代币地址以导入代币，如果你想用这个账户进行交易，你将需要测试eth。

如果你在Remix中查看合约并使用账户1和账户2的地址调用`balanceOf`函数，你也可以看到你的账户余额。
