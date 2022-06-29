ERC20标准只描述了你的合约需要的必要和可选的方法，但你可以添加额外的方法。

在本节中，我们通过使用OpenZeppelin扩展，增加了销毁和铸造代币的功能，以及暂停合约的能力。

当然，你可以编写你自己的ERC20代币合约实现或扩展，并将它们导入你的合约中。但OpenZeppelin合约已经过安全专家的审核，是一个增加所需功能的好方法。

### 可铸造
mint函数允许合约的创建者在合约部署后铸造（创建）额外的代币（第22行）。作为输入参数，该函数需要代币将被铸造的地址，以及应该被铸造的代币数量。

我们不必从另一个合同中导入`mint()`，因为mint函数已经是OpenZeppelin的 <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol" target="_blank">ERC20 contract</a> 实现的一部分。我们导入 `Ownable` （第7行），它是一个合约模块，提供了一个基本的访问控制机制，允许所有者对特定的功能有排他性的访问。在这个合约中，我们为`mint`方法（第22行）添加了继承的`onlyOwner`修饰符，并将对该方法的访问限制在 "所有者 "身上。

该合同将从 <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/access/Ownable.sol" target="_blank">Ownable contract </a> 中继承额外的函数，如 owner(), transferOwnership() 和 renounceOwnership() 以管理访问。

### 可销毁
通过导入 "ERC20Burnable"（第5行）并继承其功能（第9行），我们的合约允许代币持有者销毁他们的代币以及他们的allowance中的代币。
欲了解更多信息，请看 <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/extensions/ERC20Burnable.sol" target="_blank">ERC20Burnable contract</a>.

### 可暂停
通过 "可暂停 "合约模块（第6行和第9行），所有者能够暂停（第14行）和取消暂停（第18行）合约。在暂停状态下，代币不能被转移，这在紧急情况下可能会有帮助。
欲了解更多信息，请看 <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/security/Pausable.sol" target="_blank">Pausable contract</a>.

请看一下OpenZeppelins的 <a href="https://docs.openzeppelin.com/contracts/4.x/wizard" target="_blank">Contract Wizard</a>, 它允许你轻松地添加额外的功能。

如果你成功地完成了这个课程，请尝试Learneth NFT课程，作为你的下一阶段的学习。

## ⭐️ 作业
1. 尝试在部署后将代币铸造到一个账户。调用`totalSupply()`和`balanceOf()`以确认正确执行。
2. 销毁代币，然后调用`totalSupply()`和`balanceOf()`来确认正确的执行。
3. 测试暂停功能，使用所有者账户暂停合约，并尝试用第二个账户进行转账。该交易应该无法执行，并将抛出异常。"Pausable: paused"。
