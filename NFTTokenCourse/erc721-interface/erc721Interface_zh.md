ERC721是管理以太坊区块链上非同质化（NFT）的代币合同标准。

每个非同质化代币都是唯一的，不能互换。NFT可以具有不同的属性、行为或权限。非同质化代币用于表示艺术品、收藏品或房地产等独特数字和实物资产的所有权。

如果你想要了解更多关于ERC721代币标准的信息，可以查看 <a href="https://eips.ethereum.org/EIPS/eip-721" target="_blank">Ethereum improvement proposal</a>.

## 接口
ERC721 标准比 ERC20 标准更复杂，并且具有可选扩展。符合 ERC721 的合同必须至少实现 ERC721 和 ERC165 接口，我们将在本节中介绍。

此接口（第 11 行）是由提供的开源合同库的一部分 <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/IERC721.sol" target="_blank">OpenZeppelin</a>.

## IERC721 的函数
符合 ERC20 标准的合约必须实现以下功能：

### balanceOf
函数 `balanceOf` （第 30 行）返回地址为 `owner` 的账户拥有的代币数量

### ownerOf
函数 `ownerOf`（第 39 行）返回持有 id 为 `tokenId` 的代币的帐户的地址 `owner`。

### safeTransferFrom
函数 `safeTransferFrom`（第 55 行）将 id 为 `tokenId` 的代币的所有权从地址为 `from` 的帐户转移到地址为 `to` 的帐户。

函数 `safeTransferFrom`（第 137 行）与函数 `safeTransferFrom`（第 55 行）几乎相同。唯一的区别是，此函数具有非空的有效负载 `data`。

如果要接收传输，智能合约必须实现 `ERC721TokenReceiver` 接口。这将确保合同能够处理 ERC721 代币传输，并防止代币被锁定在无法锁定的合约中。

### transferFrom
函数 `transferFrom`（第 55 行）将id为 `tokenId` 的代币的所有权从地址为 `from` 的帐户转移到地址为 `to` 的帐户

**建议尽可能使用 `SafeTransfrom` 而不是 `transferFrom`**。`transferFrom` 函数不安全，因为它不检查作为传输接收方的智能合约是否实现了 ERC721TokenReceiver 接口，并且能够处理 ERC721 代币。

### approve
调用函数 `approve`（第 94 行）可以让地址为 `address` 的帐户拥有代表自己管理 id 为 `tokenId` 的 NFT 的权限。

### getApproved
函数 `getApproved`（第 103 行）返回有权管理 id 为 `tokenid` 的 NFT 的账户的地址 `operator`。

### setApprovalForAll
调用函数 `setApprovalForAll` （第 115 行）可以将自己拥有的所有的 NFT 的管理权限赋予 `operator` 地址对应的账户，或者从这个账户收回。

### isApprovedForAll
函数 `getApproved` （第103行）返回一个布尔值。如果地址为 `operator` 的账户被批准管理地址为 `owner` 的账户的所有代币，则函数 `getApproved` 返回 true。

## IERC721 事件
ERC721 合约还必须触发以下事件：

### Transfer
当 id 为 `tokenId` 的代币从地址为 `from` 的账户转移到地址为 `to` 的账户时，必须触发`Transfer` 事件（第 15 行）。

### Approval
当地址为 `owner` 的账户批准地址为 `spender` 的账户代表其管理 id 为 `tokenId` 的代币时，必须发出 `Approval` 事件（第 20 行）。

### ApprovalForAll
当地址为 `owner` 的帐户授予或删除地址为 `operator` 的帐户的权限（`_approved`）以管理其所有代币时，必须发出 `ApprovalForAll` 事件（第 25 行）。

## IERC165
除了 ERC721 接口之外，符合 ERC721 的合约还必须实现 ERC165 接口。

通过 ERC165 接口的实现，合约可以声明对特定接口的支持。 然后，想要与另一个合约交互的合约可以在进行交易之前查询另一个合约是否支持此接口，例如 向它发送他们可能不支持的令牌。

我们的 IERC721 接口在这里导入（第 6 行）并从 IERC165 接口继承（第 11 行）。

这就是ERC165接口的 <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/introspection/IERC165.sol" target="_blank">OpenZeppelins implementation</a> 大致格式

```sol
interface IERC165 {
    function supportsInterface（bytes4 interfaceId） external view returns （bool）;
}
```

例如，EIP721 中指定的 ERC721 接口的 ERC165 标识符为“0x80ac58cd”。想要了解如何计算接口标识符以及有关 ERC165 的更多信息可以在这里进一步了解 <a href="https://eips.ethereum.org/EIPS/eip-165" target="_blank">improvement proposal</a>。

## 其他接口
必须实现 <a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">IERC721TokenReceiver</a> 接口以接受安全传输。

EIP721 中指定了 ERC721 合约的两个可选扩展：

IERC721Enumerable 使合约能够发布其完整的代币列表并使其可被发现。

IERC721Metadata 使合约能够将附加信息与代币相关联。 我们将在下一节中对此进行更详细的研究。
