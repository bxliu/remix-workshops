在本节中，我们将在浏览器中部署一个合约并测试其功能。

### 1. 部署合约
**1.1** 在Remix IDE的 "Solidity compiler"模块中编译你的EduCoin合约。

**1.2** 在 "Deploy & run transactions" 模块中, 在合约输入栏中选择你的合约 "EduCoin"，并点击 "Deploy" 按钮。 一定要确保在合约选择器输入栏中选择正确的合约。

**GIF** 编译和部署：
<img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_compileAndDeploy.gif?raw=true" alt="Compile and deploy contract" width="300"/>

### 2. 测试函数
在IDE中展开代币合约功能。

#### 2.1 Decimals
点击 "decimals" 按钮，调用 decimals() 函数。
它应该返回 "18"。

####  2.2 Name
点击 "name" 按钮，调用name()函数。
它应该返回 "EduCoin"。

#### 2.3 Symbol
点击 "symbol" 按钮，调用 symbol() 函数。
它应该返回 "EDC"。

#### 2.4 Total supply
点击 "totalSupply" 按钮，调用 totalSupply() 函数。
它应该返回 1000000000000000000000 (1000*10**18)。

**GIF** 测试 decimals, name, symbol, 和 totalSupply 函数:
<img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_test_functions.gif?raw=true" alt="Test transfer function" width="300"/>

#### 2.5 Balance of
**2.5.1** 进入侧边栏的 "ACCOUNT" 部分，使用旁边的复制图标，复制显示的地址。

**2.5.2** 将地址粘贴在 "balanceOf" 函数按钮旁边的输入栏中，然后点击按钮。
它应该返回 1000000000000000000000 (1000*10**18)。

**GIF** 测试 balanceOf 函数:
<img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_balanceOf.gif?raw=true" alt="Test transfer function" width="300"/>

#### 2.6 Transfer
我们将把EduCoin从一个账户转移到第二个账户。

**2.6.1** 进入侧边栏的 "ACCOUNT" 部分，点击显示的地址。这应该会打开一个下拉菜单。选择显示的第二个地址并复制其地址（账户2）。

**2.6.2** 打开下拉菜单，再次选择第一个账户（账户1），因为这是我们想用来转账的账户。

**2.6.3** 将地址粘贴在 "transfer" 函数按钮旁边的输入栏中，输入数字500000000000000，然后点击按钮。

**2.6.4** 如果你检查账户1和账户2的余额，它们都应该返回5000000000000000000的金额。

**GIF** 测试 transfer 函数:
<img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_transfer.gif?raw=true" alt="Test transfer function" width="300"/>

#### 2.7 Approve
我们现在将允许账户1代表账户2花费代币。

**2.7.1** 进入 "Account" 部分，复制账户1的地址，然后再将其设置为账户2。

**2.7.2** 在approve函数中，输入账户1的地址作为支出者的输入，并将金额设置为25000000000000000。

**GIF** 测试 approve 函数:
<img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_approve.gif?raw=true" alt="Test approve function" width="300"/>

#### 2.8 Allowance
在 "allowance" 按钮旁边输入账户2的地址作为所有者，账户1作为支出者；点击按钮。
它应该返回1000000000000000000000。

**GIF** 测试 allowance 函数:
<img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_allowance.gif?raw=true" alt="Test allowance function" width="300"/>

#### 2.9 TransferFrom
现在账户1将从账户2转移25000000000000000代币到自己的账户。

**2.9.1** 在 "ACCOUNT" 部分选择账户1。

**2.9.2** 在"transferFrom"按钮旁边输入账户2的地址作为发送方，账户1作为接收方，输入25000000000000000作为金额，然后点击按钮。

**2.9.3** 检查账户2和1的余额，它们应该返回25000000000000000和7500000000000。

**GIF** 测试transferFrom函数:
<img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_transferFrom.gif?raw=true" alt="Test transferFrom function" width="300"/>