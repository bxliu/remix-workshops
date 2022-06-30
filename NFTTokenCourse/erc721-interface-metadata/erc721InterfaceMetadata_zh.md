元数据扩展是可选的。 它允许我们向我们的 ERC721 代币添加额外的信息。 我们可以指定一个名称、一个符号和一个 URI（统一资源标识符），它们可以指向一个文件，我们可以在其中以 JSON 的形式添加更多信息。

## ERC721 元数据 函数

### name
函数 `name`（第 16 行）返回代币集合的名称。 代币集合是指使用您的 ERC721 代币合约实施创建的所有代币。 此集合中的每个代币都将具有此名称，无论其 tokenId 是什么。

### symbol
`symbol` 函数（第 21 行）返回代币集合的符号。

### tokenURI
函数 `tokenURI`（第 26 行）返回标识为 `tokenId` 的代币的 URI。 在这种情况下，它不是整个集合的 URI，而是集合中单个代币的 URI。

## ERC721 Metadata JSON Schema
tokenURI指向的文件应符合<a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">EIP-721</a>中指定的元数据JSON模式

```
{
    "title": "Asset Metadata",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "Identifies the asset to which this NFT represents"
        },
        "description": {
            "type": "string",
            "description": "Describes the asset to which this NFT represents"
        },
        "image": {
            "type": "string",
            "description": "A URI pointing to a resource with mime type image/* representing the asset to which this NFT represents. Consider making any images at a width between 320 and 1080 pixels and aspect ratio between 1.91:1 and 4:5 inclusive."
        }
    }
}
```
根元素必须是object类型。此根对象应具有键的属性：name、description和image，它们都应为字符串类型。

ERC721标准非常灵活，tokenURI不需要指向JSON文档，JSON不需要具有所有属性，通常还具有其他属性。