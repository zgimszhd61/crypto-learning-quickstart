要在Python中监听Polygon链上的交易，你需要使用Web3.py库，这是一个Python库，用于与以太坊兼容的区块链进行交互。以下是一个快速入门指南，展示了如何设置一个简单的脚本来监听Polygon网络上的交易。

### 必要条件
- Python 3.x
- Web3.py库
- 一个Polygon RPC节点的URL，可以是Infura、Alchemy或其他提供商的节点

### 安装Web3.py
首先，确保你已经安装了Web3.py。如果还没有安装，可以使用pip进行安装：

```bash
pip install web3
```

### 监听交易的脚本
以下是一个Python脚本的示例，它使用Web3.py监听Polygon网络上的新交易：

```python
from web3 import Web3

# Polygon RPC URL，替换为你的RPC提供商的URL
polygon_rpc_url = 'https://polygon-rpc.com'

# 创建Web3连接实例
w3 = Web3(Web3.HTTPProvider(polygon_rpc_url))

# 检查是否连接成功
if w3.isConnected():
    print("Connected to Polygon Network")
else:
    print("Failed to connect to Polygon Network")
    exit(1)

# 监听新交易
def handle_event(event):
    print(f"New transaction: {event.hex()}")

# 主函数，监听新交易
def main():
    while True:
        block = w3.eth.get_block('latest')
        if block and block.transactions:
            for tx in block.transactions:
                handle_event(tx)

# 运行主函数
if __name__ == "__main__":
    main()
```

这个脚本会连接到Polygon网络，并不断检查最新的区块中的新交易。每当发现新交易时，它会打印出交易的哈希值。

请注意，这个脚本是同步的，并且会一直运行，不断检查新区块。在实际应用中，你可能需要使用异步编程技术或设置一个定时任务来定期检查新区块，以避免无限循环。

此外，这个脚本只是一个基础的示例，实际应用中可能需要更复杂的逻辑来处理交易，例如过滤特定的事件或地址、解析交易数据等。

### 注意事项
- 这个脚本不包括错误处理逻辑，你可能需要添加异常处理来确保脚本的稳定运行。
- 如果你需要监听特定的智能合约事件，你需要合约的ABI来创建合约实例，并使用`contract.events.YourEvent.createFilter()`来创建事件过滤器。
- 监听链上交易可能需要消耗大量的资源，特别是在高吞吐量的网络上，因此请确保你的环境能够处理这些数据。

Citations:
[1] https://learnblockchain.cn/docs/etherscan/
[2] https://cloud.tencent.com/developer/article/2365837
[3] https://dexnav.com/6939.html/
[4] https://blog.chain.link/how-to-create-an-erc-20-token-on-polygon-zh/
[5] https://learnblockchain.cn/article/4112
[6] https://cloud.tencent.com/developer/article/2152769
[7] https://www.oklink.com/docs/zh/
[8] https://learnblockchain.cn/article/4309
[9] https://openprompt.co/conversations/1352
[10] https://plisio.net/zh/blog/polygonscan-what-it-is-and-how-to-use-it
[11] https://blog.csdn.net/Ximerr/article/details/126336333
[12] https://docs.infura.io/tutorials/ethereum/monitor-transfers-using-python
[13] https://cloud.tencent.com/developer/article/2152788
[14] https://etherscan.io/address/0xe843afe7aDEA400bCdb0fF70F8166e5D427C44E5
[15] https://github.com/AmazingAng/WTF-Solidity/blob/main/Topics/Tools/TOOL03_Ganache/readme.md
[16] https://www.volcengine.com/theme/5184796-R-7-1
[17] https://juejin.cn/s/web3%20%E8%B0%83%E7%94%A8%E5%90%88%E7%BA%A6
[18] https://learnblockchain.cn/question/4126
[19] https://learnblockchain.cn/article/3517
[20] https://juejin.cn/post/7309547029800337458