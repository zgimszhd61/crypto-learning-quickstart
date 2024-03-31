ERC20标准定义了一组API，这些API允许智能合约在以太坊网络上实现代币的基本功能。这些API包括了一系列的函数和事件，它们共同定义了ERC20代币的行为和特性。以下是ERC20最常用的API：

1. **totalSupply()**：这个函数返回代币的总供应量。它是一个只读函数，不接受任何参数，并返回一个`uint256`类型的值，表示代币的总量[1][2][5][7][10][15][17]。

2. **balanceOf(address _owner)**：这个函数用于查询某个地址（`_owner`）的代币余额。它接受一个地址作为参数，并返回该地址所持有的代币数量，返回值类型为`uint256`[1][2][5][7][10][15][17]。

3. **transfer(address _to, uint256 _value)**：允许代币的持有者将自己的代币转移给另一个地址（`_to`）。这个函数接受两个参数：接收者的地址和转移的代币数量。如果转账成功，它会返回一个布尔值`true`，并触发一个`Transfer`事件[1][2][5][7][10][15][17]。

4. **approve(address _spender, uint256 _value)**：允许代币持有者授权第三方（`_spender`）从自己的账户中转出最多`_value`数量的代币。这个函数也会返回一个布尔值表示操作是否成功，并在成功时触发一个`Approval`事件[1][2][5][7][10][15][17]。

5. **allowance(address _owner, address _spender)**：查询授权给第三方（`_spender`）从代币持有者（`_owner`）账户中转出代币的最大数量。这个函数返回一个`uint256`类型的值，表示允许转出的最大代币数量[1][2][5][7][10][15][17]。

6. **transferFrom(address _from, address _to, uint256 _value)**：允许第三方（之前通过`approve`函数获得授权的）从代币持有者（`_from`）的账户中转出代币到另一个账户（`_to`）。这个函数接受三个参数：发送者地址、接收者地址和转移的代币数量。如果转账成功，它会返回一个布尔值`true`，并触发一个`Transfer`事件[1][2][5][7][10][15][17]。

这些API构成了ERC20代币标准的核心，使得代币可以在以太坊网络上被创建、分发、转移和查询。通过这些标准化的接口，ERC20代币能够与以太坊生态系统中的其他智能合约和服务无缝交互。

Citations:
[1] https://moralis.io/exploring-the-ultimate-erc20-token-api/
[2] https://cryptoapis.io/layers/erc20
[3] https://www.quicknode.com/token-api
[4] https://learnblockchain.cn/docs/etherscan/
[5] https://ethereum.org/en/developers/docs/standards/tokens/erc-20/
[6] https://ethbook.abyteahead.com/ch9/erc20.html
[7] https://docs.tokensafer.com/openzeppelin/Tokens/erc20.html
[8] https://docs.openzeppelin.com/contracts/4.x/api/token/erc20
[9] https://docs.openzeppelin.com/contracts/2.x/api/token/erc20
[10] https://docs.moonbeam.network/cn/builders/pallets-precompiles/precompiles/erc20/
[11] https://learnblockchain.cn/article/6557
[12] https://docs.bitquery.io/docs/examples/transfers/erc20-token-transfer-api/
[13] https://docs.infura.io/api/networks/ethereum/how-to/interact-with-erc-20-tokens
[14] https://www.volcengine.com/theme/6427627-R-7-1
[15] https://blog.csdn.net/cljdsc/article/details/125204450
[16] https://learnblockchain.cn/article/4327
[17] https://www.liaoxuefeng.com/wiki/1207298049439968/1207298073798912
[18] https://www.uduncloud.com/news/36/129
[19] http://cw.hubwiz.com/card/c/etherscan-api/
[20] https://blog.csdn.net/sinat_34070003/article/details/79105284