在本节中，我们将创建元数据并以去中心化的方式存储它。

IPFS（InterPlanetary File System）是一个用于以分布式方式存储文件的点对点网络。 Pinata.cloud 是一种固定服务，允许用户在 IPFS 网络上轻松托管文件。

我们想在 IPFS 上托管我们的图像和 JSON 文件及其元数据。

### 创建图像文件夹
在此示例中，我们将为三个代币创建元数据。 正如您在下面看到的，我们创建了三个存储在一个文件夹中的图像。

```
geo-img
├── geo_1.png
├── geo_2.png
├── geo_3.png
```
### 在 Pinata 上注册
现在，我们希望将这些图像托管在某个地方，以便我们可以在代币的元数据中指向它们。 让我们以去中心化的方式进行，并使用 Pinata 将它们托管在 IPFS 上。

首先，您需要一个 Pinata 帐户。 在 <a href="https://app.pinata.cloud/register" target="_blank">Pinata.cloud</a> 并创建一个帐户。在Pinata 上，你最多可以免费上传 1 GB 的数据。

注册后，你应该在 Pin Manager 视图中。


<img src="https://i.imgur.com/yKpD65m.png" alt="Pin Manager Pinata" width="300"/>

### 将图像上传到 IPFS
单击上传按钮并上传包含图像的文件夹。
上传文件夹后，您应该会看到文件夹的名称以及与之关联的 CID（内容标识符）。 如果文件夹中的内容发生变化，CID 也会发生变化。

要访问您在 IPFS 上的文件夹，请输入此地址“https://ipfs.io/ipfs/"  并添加您的 CID。 对于我们当前的示例，您可以使用以下命令访问您的文件夹：
<a href="https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P" target="_blank">
    https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P
</a>

你可以使用以下命令来访问某个图片：
<a href="https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_1.png" target="_blank">
    https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_1.png
</a>

### 创建 JSON 文件
我们创建另一个文件夹来存储三个 JSON 文件。
```
geo-json
├── 0
├── 1
├── 2
```

在 JSON 文件中，为代币创建元数据，例如名称、描述和图像。
对于图像 URL，我们将使用 IPFS 上图像的 URL。 如果你愿意，可以添加其他数据； 在这个例子中，我们为每个代币添加了一些独特的属性。

这是第一个代币的 JSON 的结构：
```
{
    "name": "Geometry#0",
    "description": "Geometry is an NFT collection for educational purposes.",
    "image": "https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_1.png
",
    "attributes": [
        { "trait_type": "background", "value": "cyan" },
        { "trait_type": "color", "value": "red" },
        { "trait_type": "shape", "value": "circle" }
    ]
}
```

这是第二个代币的 JSON 的结构：
```
{
    "name": "Geometry#1",
    "description": "Geometry is an NFT collection for educational purposes.",
    "image": "https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_2.png",
    "attributes": [
        { "trait_type": "background", "value": "magenta" },
        { "trait_type": "color", "value": "green" },
        { "trait_type": "shape", "value": "square" }
    ]
}
```

如上所示，本例中的文件夹名为“geo-json”。 在这个文件夹中，我们有三个 JSON 文件。
第一个 JSON 文件称为“0”，第二个 JSON 文件称为“1”，第三个 JSON 文件称为“2”。

确保您的 JSON 文件没有文件结尾，并且命名与其对应的 tokenIds 相同。
在 pinata.cloud 上的 pin 管理器中，单击上传按钮并上传包含 JSON 文件的文件夹。

如果要访问你在IPFS上的文件夹，输入如下地址 "https://ipfs.io/ipfs/" 并添加你的 CID。
对于我们当下的案例，你可以访问你的文件夹通过使用：
<a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp" target="_blank">
    https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp
</a>

这将会是我们的baseURI。

您可以访问特定的 JSON 文件，然后只需添加斜杠和 tokenId，使用：
<a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/0" target="_blank">
    https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/0
</a>


在合约中，将 baseURI 替换为你自己的 baseURI。 在此示例中，baseURI 包含 URL
"https://ipfs.io/ipfs/", CID包含了JSON文件夹，和一个结尾的斜杠"/"。

现在将通过将 tokenId 添加到 baseURI 为每个合约创建一个单独的 tokenURI——这正是我们在上面的示例中手动执行的访问 JSON 文件的操作。
