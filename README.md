
Arbitrage Trading Bot:

Arbitrage trading bot is not a new idea, and it has been around for many years. Though, it is not very effective in the traditional centralized market since they are using order book structure, which increases the efficiency and the speed.
In Ethereum, decentralized exchanges (Automated Market Makers) do not use the order book anymore. Instead, we use the identical ratio of price over quantity for a pair of cryptos to induce the increase in the price of one specific token when its liquidity being decreased. For more information about this protocol please visit: https://www.youtube.com/watch?v=rnVi-b7UqmY.

What we have tried to do above is to come up with a trading bot that uses many exchanges and tokens. We use the exchanges such as: Uniswap, Sushiswap, Balancer, Kyber and OneSplit and tokens DAI, LINK, WBTC, COMP, BAND, MKR, UNI, YFI, SNX, PNK, OMG, REN, CRV. We also used dy/dx to get flashloans as leverage to increase the payoff. 

Though the code works just fine, this is not an appropriate way to implement arbitrage trading, since LOTS of gass will be spent on every transaction. I think it would be much batter to write contracts with only one pair of exchanges. We can have different contracts with different pairs and then call them when we find out opportunities. This will take us to the second problem: how to realize the opportunities? We used Infura above but it will only give us around 10000 requests in a day, which is not that much. Note that the arbitrage opportunities are not that common since there are hundereds (if not thousands) of other arbitragers searching the market for them. It is necessary to check the market as frequent as we can to detect any opportunity. We can solve this problem by implementing the searching algorithm using the off-chain blockchain data. We can use the api of one of the websites that provide the sufficient data of the network such as https://www.blockchain.com/explorer.

One final issue was to test the code using the ethereum test networks. Not only different protocols have implememted their projects in different networks, but also these implementations are not up to date. It might be possible that you write your code based on the final version of a protocol but the test network version does not have any idea about the recently updated functions. To solve this part, we can fork the main network for a short time to test our contract and its functionalities and then upload it to the main network.
After all, gas fee is really an issue fo us especially for sending complicated transactions such as aritrage or liquidation. We can instead focus on the blockchains that use POS since their transaction fees are not that high. I am passionately looking forward to Ethereum version 2 with 100,000 transactions in a sec!
