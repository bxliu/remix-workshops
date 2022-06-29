`sampleContract.json` 中的 `Deploy` 属性包含告诉 Remix IDE 特定网络的库地址所需的一切。

- `<address>` 包含已部署的库的地址。您必须为每个网络指定此地址。
- `autoDeployLib` 是一个布尔值，它告诉 Remix IDE 是否应该在部署合约之前自动部署库。

基本上如果 `autoDeployLib` 是 **true**，`<address>` 将不会被使用，Remix 会在部署合约之前自动部署库。

出于本演示的目的——我们正在模拟已部署库的情况，因为这是更常见的情况。

因此，对于条目 `VM:-` ，将 `autoDeploy` 设置为 **false**。

移至下一步。

