在本节中，我们将使用 Metamask（以太坊钱包）将我们的合约部署到以太坊区块链的 Rinkeby 测试网，铸造 NFT，并在 NFT 市场 OpenSea 上查看它。

### 1. 安装Metamask
**1.1** 前往 <a href="https://metamask.io/" target="_blank">metamask.io</a>.

**1.2** 点击下载按钮，然后单击浏览器（例如 Chrome）的安装并将扩展程序添加到浏览器。

**1.3** 按照描述创建一个钱包。

### 2. 获取 Rinkeby 的测试网代币
为了在测试网上进行交易，我们需要以太坊测试网代币。

**2.1** 将您的 Metamask 从“以太坊主网络”切换到“Rinkeby 测试网络”。

**2.2** 前往 <a href="https://faucet.paradigm.xyz/" 
target="_blank">https://faucet.paradigm.xyz/</a>, 输入账户的地址并索取测试网 ETH。

您也可以使用其他 ropsten faucets，例如 <a href="https://faucet.paradigm.xyz/" target="_blank">https://faucet.paradigm.xyz/</a> 或者 <a href="https://app.mycrypto.com/faucet" target="_blank">https://app.mycrypto.com/faucet</a>。可以在 <a href="https://ethereum.org/en/developers/docs/networks/#testnet-faucets" target="_blank">ethereum.org</a> 中查看可用的 faucets 并了解更多

### 3. 合约部署
**3.1** 在“ENVIRONMENT”下的 Remix IDE 的“DEPLOY & RUN TRANSACTIONS”模块中，选择“Injected Web3”。 然后它应该要求您连接您的帐户，您应该确认。然后您应该会在“Injected Web3”下看到 Rinkeby 网络徽章。

**3.2** 部署你的代币合约并在Metamask中确认交易

**3.3**  您的合约应出现在“已部署的合约”部分。

### 4. 铸造一个 NFT 代币
**4.1** 在 IDE 中展开您的合约，以便您可以看到函数的按钮。

**4.2** 展开 safeMint 按钮旁边的输入字段。 在 “to：” 输入字段中输入连接到 Remix 的帐户的以太坊地址。 在输入字段 “tokenID：” 中输入 “0”。点击交易。

**4.3** 在 Metamask 中单击资产，然后单击 “导入代币” 链接，并将您的合约地址粘贴到输入字段中。 您可以将小数设置为 0。

您现在应该在 Metamask 的“资产”视图中看到代币合约的符号名称（例如 GEO）。您应该拥有这些代币之一。

### 5. 在 OpenSea 中看到你的 NFT
<a href="https://opensea.io/" 
target="_blank">OpenSea</a> 是最著名的在线NFT交易场所之一。 OpenSea 统一提供一个版本，你可以在测试网中查看资产在 <a href="https://testnets.opensea.io/" 
target="_blank">https://testnets.opensea.io/</a>

**5.1** 前往 <a href="https://testnets.opensea.io/login" 
target="_blank">https://testnets.opensea.io/login</a>.

**5.2** 连接您的 Metamask 钱包，您应该被重定向到您的帐户 <a href="https://testnets.opensea.io/account" target="_blank">https://testnets.opensea.io/account</a> 在 OpenSea 的视图, 你应该可以在这里看到你的 NFT。你应该看到你的 NFT 的图像； 当您单击它时，您应该会看到名称、描述和属性，以及您创建的属性。

如果您成功完成本课程并熟悉 Solidity 开发的基础知识，我们鼓励您通过学习如何从 Learneth 资源创建自己的 NFT 拍卖合约来继续您的学习之旅。