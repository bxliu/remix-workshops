ERC20 (Ethereum Request for Comments 20) 是一个在以太坊区块链上管理同质化代币的代币合约标准。

同质化代币之间都是平等的，具有相同的价值、行为和权利。同质化代币通常被用作交换媒介，如货币ETH或BTC。然而，它们也可以有其他的使用情况，如投票权或声誉。

如果你想了解更多关于ERC20代币标准的信息，请看一下它的说明 <a href="https://eips.ethereum.org/EIPS/eip-20" target="_blank">Ethereum improvement proposal</a>.

## 接口
为了了解ERC20代币合约所需的功能，我们将看一下与ERC20合约交互的接口。
这个接口（第9行）是开源合约库的一部分，由 <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.4.0/contracts/token/ERC20/IERC20.sol" target="_blank">OpenZeppelin </a> 提供。

## ERC20 函数
符合ERC20标准的合约必须实现以下六个函数：

### totalSupply
函数 `totalSupply`（第13行）返回可用的代币总量。

### balanceOf
函数`balanceOf`（第18行）返回地址为`account`的账户所拥有的代币数量。

### transfer
函数 `transfer` （第27行）将 `amount` 个代币转移到地址 `recipient`.
这个函数**必须**发出（产生）一个 `Transfer` 事件（见下文），并且当发送者没有足够的代币来进行转移时，**应该**抛出一个异常。

### approve
函数 `approve` （第52行）代表调用该函数的账户为地址 `spender` 创建一个allowance来转移 `amount` 个代币

### allowance
函数 `allowance`（第36行）返回地址 `spender` 被允许代表地址为`owner`的账户花费的代币数量。

### transferFrom
函数 `transferFrom` （第63行）代表地址`sender` 向地址`recipient` 转移`amount` 的代币。 这个方法 **必须** 发出一个 `Transfer` 事件。

## ERC20 事件
ERC20 合约也必须发出两个事件:

### Transfer
`Transfer`（第71行）事件必须在 `value` 数量的代币从地址为 `indexed from` 的账户转移到 `indexed to`的账户时发出。 参数 `from` 和 `to` 是 `indexed` ，允许我们使用索引参数作为过滤器来搜索这些事件。

### Approval
当账户 `indexed owner` 批准账户 `indexed spender` 以其名义转移 `value` 数量的代币时，必须发出  `Approval`（第77行）事件。

## ERC20 可选函数
除了强制性的函数和事件外，ERC20标准中还规定了三个可选函数，在这个接口中没有实现：

### name
`function name() external view returns (string);`

返回代币的名字。

### symbol
`function symbol() external view returns (string);`

返回代币的符号

### decimals
`function decimals() external view returns (uint8);`

返回代币使用的小数位数。

你可能想用小数来使你的代币在显示时可以分成任意量，如1.5ETH。EVM（以太坊虚拟机）只支持整数。这就是为什么ERC20标准建议实现小数功能，指定一个代币有多少个小数位。小数点后18位是工业标准。
