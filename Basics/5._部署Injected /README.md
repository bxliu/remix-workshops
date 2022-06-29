## 部署到公共测试网。

1. 下载浏览器插件 **MetaMask**。
2. 单击浏览器中的 MetaMask 图标。登录并选择一个测试网络。
3. 为该网络获取一些测试 ETHER。例如，如果您选择了 Goerli Network，则搜索 `Goerli faucet`，您会找到一个可以获取测试以太币的网站。
4. 回到 Remix。在 **Deploy & Run** 中，在 **Environment** 下拉菜单中，选择 **Injected Web3**。
5. 看看您是否可以将您编译的 2_Owner.sol 部署到您刚刚选择的测试网络上。如果您在 **CONTRACT** 选择框中看到 2_Owner.sol 作为选项，请单击 **Deploy** 按钮。
   - 如果您在此选择框中看不到任何内容，则需要再次编译 ballot.sol 。如果您确实需要再次编译 2_Owner.sol ，请确保它是**编辑器**中的活动文件，然后转到 **Solidity 编译器**进行编译。
   - 然后，转到 **Deploy & Run** 插件并部署到您在步骤2中选择的网络。
6. 您将看到 MetaMask 弹出窗口要求您支付交易费用。

至此，您已经完成了本教程。您现在拥有在 Remix IDE 中打开、编译、部署和交互智能合约的经验。