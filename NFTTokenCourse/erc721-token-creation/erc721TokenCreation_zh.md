在本合约中，我们使用 OpenZeppelin 的 ERC721 代币合约实现（第 4 行）。

在 <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/ERC721.sol" target="_blank">ERC721 contract</a> 中看下他们的实现。除了 ERC721 标准中指定的功能外，该合约还提供了其他功能，我们稍后会看到。

## myToken 
我们创建了自己的合约并命名为 MyToken（第 7 行），它继承了（第 7 行）OpenZepplin `ERC721` 代币合约实现和我们导入的 `Ownable` 的功能（第 4 行）。 如果您不记得 Ownable 合约模块，请查看 ERC20 扩展部分。

这里 ERC721 实现使用 EIP 中指定的 IERC721Metadata 扩展。 我们的合约继承了 `name()` 和 `symbol()` 函数，并有一个构造函数，允许在合约部署期间设置它们的值（第 8 行）。
在这种情况下，我们将使用默认值。 我们将我们的代币命名为与合约 `“MyToken”` 相同的名称，并将 `“MTK”` 作为其符号。

### Base URI
通过 ERC721 合约，我们能够创建各种代币，每个代币都有自己的 tokenId。 正如我们在 IERC721Metadata 接口中看到的，每个代币都可以有自己的 `tokenURI`，它通常指向一个 JSON 文件来存储元数据，如名称、描述和图像链接。
如果合约铸造了多个代币，ERC721 实现通常使用相同的 URI 作为所有代币的基础 （`baseURI`），并且仅通过在末尾通过连接添加其唯一的 `tokenId` 来区分它们。 在下一部分中，我们将看到它在实践中的样子。

在此示例中，我们将数据存储在 IPFS 上————下一节将详细介绍。 我们的 baseURI 是 <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/</a> （第11行）

通过连接，id为 0 的代币的代币 URI 将是<a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0</a> , id为 1 的代币的代币 URI 将是<a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1</a>, 后续同上。

使用 IPFS 并遇到"504 Gateway Time-out" 的报错时，你可能必须等待并重试，直到数据可用。

### safeMint
使用 safeMint 函数（第 14 行），我们使所有者能够在合约部署后创建具有专用代币 ID 的新代币。
safeMint 函数是 OpenZeppelin 的 ERC721 实现的一部分，它让我们可以安全地将挖到的id 为 `tokenId` 的代币关联到地址为 `to` 的帐户。 对于访问控制，我们使用我们之前导入的 Ownable 访问控制合约模块中的 `onlyOwner` 修饰符（第 5 行）。

在下一节中，我们将了解如何为 NFT 创建和托管元数据。

## ⭐️ 作业
1. 将您的合约重命名为 `Geometry`。
2. 将您的令牌重命名为 `Geometry`。
3. 将您的代币符号更改为 `GEO`。
4. 将 `_baseURI` 更改为 https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/。