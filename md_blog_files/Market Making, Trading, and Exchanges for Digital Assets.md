### Introduction:


### Types of Market Participants:


Investors
- Investors bring knowledge (perceived or otherwise real) to the market
- They use this knowledge to allocate economic resources(capital) to specific projects or assets (Increasing price or market cap)
- Primarily use digital assets as a store of value, or more so an appreciating investment similar to stock or real estate
- Need markets to be liquid in to find a counterparty when entering or exiting an investment opportunity
- Do not care about small price changes, but rather desire efficient execution of their trade
Defi Users

Speculators
Market Makers
Arbitrageurs

### Types of Exchanges:

Centralized Exchanges(CEX)
- Facilitated by a centralized custodial third party, through a limit order book(CLOB)
Decentralized Exchanges(DEX)
- Typically facilitated by swap protocols(AMMs)
- Utilizes a liquidity pool often pooled by staked capital from liquidity providers who earn a share of transaction fees.
- However there are now examples of hybrid CLOB DEX exchanges, notably(dYdX)
Over-The-Counter(OTC)
- generally reserved for large market participants looking to trade large volume directly with a counterparty, often facilitated by a third party(CEX). 
- Theoretically could be any trade that happens as an independent agreement between two parties.
- In some sense provides similar privacy to large players that a dark pool would, however any on-chain transaction quickly becomes public knowledge.

DEX Exchanges

Automated Market Makers (AMM's)
- AMMs operate on decentralized exchanges (DEXs) and replace the traditional CLOB model with algorithms that automatically determine token prices based on a predetermined formula.
- Liquidity in AMM swaps is provided by users who stake funds into liquidity pools. These swaps contain pools of token pairs, and users accrue a portion of fees by providing liquidity to these pairs.
- Users initiate swaps by interacting directly with the smart contract of the decentralized exchange. They specify the input token and the desired output token, and the AMM calculates the appropriate exchange rate.
- When an order is executed the ratio of {TOKEN XYX - TOKEN ABC} in a given pool changes slightly, indicated by the "Price Impact" of any given swap. Larger swaps have greater price impact.
- AMM's typically only provide market orders, with the ability for a user to specify price slippage and gas fees to incentivize or guarantee quick execution. 
	- While slippage and gas fees are two separate functions of your interaction with the smart contract, they both contribute to the MEV(Miner/Maximum-extractable-value) of your transaction. This means they both provide the opportunity for the some entity(miner or block builder) to earn value from processing your transaction.
	- Fees are then a separate charge accrued to the Liquidity providers (LP's)
	- These nuances typically make DEX trading a more fractioned market with more opportunities for inefficiency.

CEX Exchanges
- Centralized exchanges facilitate the majority of transactions
- Compared to most legacy markets, centralized crypto markets experience a large degree of market fragmentation. 
- Many exchanges rely on arbitrageurs or cross-exchange-market-makers to maintain competitive pricing, or "The law of one price".
- Most exchanges,  in both legacy and crypto markets rely on CLOB's to match up buyers and sellers and enable efficient, transparent, and fair exchange of assets
- CLOB's provide a variety of benefits to all types of markets participants
- We will explore CLOB's further to understand why this component of market structure is so important.

Central Limit Order Books (CLOB's)
- The central limit order book operates on the principle of connecting buyers and sellers by compiling and displaying their respective orders. Orders are generally categorized as either limit orders or market orders.
	- Limit orders(MAKER orders)
		- Traders specify the price at which they are willing to buy or sell an asset. These orders are placed in the order book until they are matched with a counterparty or canceled by the trader.
		-  add liquidity to the order book (MAKE liquidity)
		- passive order flow
		- the heavier hand, the advertisement, the patient participant
		- cheaper fee structure (rebate in some cases)
	- Market orders(TAKER orders)
		- Traders request immediate execution at the best available market price. Market orders are matched with the best existing limit orders in the order book.
		- remove liquidity from the order book (TAKE liquidity)
		- aggressive/active order flow
		- the weaker hand, the urgent participant
		- more expensive fee structure, plus spreads
	- There are various more advanced order types available in many cases, however for the purposes of our discussion we will not cover these. (This includes buy stops, sell stops iceberg orders, contingent orders, etc.)
	
	Key Components
- **Bids and Asks:** The prices buyers are willing to pay is known as bids, while prices sellers are willing to accept are called asks. (asks are sometimes referred to as an offer).
- **Spread:** The difference between the best bid and best ask price on the order book represents the market spread. This reflects the cost of executing a market order. (Often referred to as the bid-ask spread).
- **Depth:** Order books display the depth of the market by illustrating the cumulative quantity of orders at different price levels. (Sometimes referred to as Depth of market, or DOM)

### Introduction to the market microstructure of CLOB's
- As discussed, markets are made up of two opposing forces, makers and takers.  Understanding how these forces interact to create price discovery is an important concept to any market user, and will show us why CLOB's are such an key characteristic of markets.

A primer to market microstructure of CLOB's:
Volume versus Liquidity: Volume and liquidity are important market concepts that go hand in hand but have unique implications. Volume simply refers to the total volume of assets that have been exchanged in a given time period. Liquidity refers to the ease and speed with which an asset or security can be bought or sold in a market without significantly affecting its price. One fallacy some market participants have is that an asset or market with large volume is inherently liquid. This is often the case, but not always true. 

Liquidity is driven by the accumulation of passive interest in a market, or the **Stacking** of limit orders. Liquidity can fade when interest declines and limit orders are removed from the order book, known as **Pulling**.

Volume is driven by


Simple metrics for discerning market liquidity:

Volume is easy quantify by summing the quantity of trades executed during a period of time. Liquidity is more difficult to quantify, however there are two simple metrics we can observe to get an idea of a markets liquidity, namely order book depth and bid-ask spread. 

**Order book depth** is two sided metric encompassing the cumulative size of bids and asks on the order book, in other words it measures the quantity and size of passive limit orders resting on the order book. It provides insight into market liquidity by showing the depth of **demand (buy orders)** and **supply (sell orders)** at different prices. As we know supply and demand is the primary driver of crypto asset prices so this can be valuable information for any market participant.

**Bid-Ask spread** is simply the difference between the **BEST bid** and the **BEST ask**. The bid-ask spread is often quoted as a percentage of the ask price, however it can also be quoted in absolute terms of the quoting asset, for example on an ETH-USDT pair the bid-ask spread might be quoted in absolute USDT. 

The price we see on a price chart or trading screen is known as the **mid-price**. This is simply the average between the best bid and offer. As bid ask spreads tighten the price at which you buy or sell approaches the mid-price. However, when placing a market order (known as "Crossing the spread", as you cross the spread from your side of the book to take a limit order from the opposing side) you will incur the bid-ask spread as part of your trading fees.


As limit orders stack up on the order book (increasing depth of market), competition between passive market participants increases (primarily represented by market makers). This competition forces passive participants to place limit orders increasingly close to the mid-price in order to remain on top of the book, leading to tighter spreads.

### Simple example analyzing the liquidity of markets on kraken for ETH-USD versus ETH-USDT.
				![[Pasted image 20240213192600.png]]
				Above we can see a chart of the order book depth for ETH-USD on kraken (02/13/24 ~7:30PM)
				![[Pasted image 20240213192707.png]]
				And here we can see a chart of the order book depth for ETH-USDT on kraken (02/13/24 ~7:30PM)
			
				![[Pasted image 20240213193222.png]]
				Above we can see a visualized slice of the order book for ETH-USD on kraken (02/13/24 ~7:30PM)
				![[Pasted image 20240213193313.png]]
				And here we can see a visualized slice of the order book for ETH-USDT on kraken (02/13/24 ~7:30PM)

In these images we can see that in relative terms, the market for ETH-USD is more liquid than for ETH-USDT. This is because kraken primarily uses USD as the quoting asset for trading pairs on their exchange, so there is more market participants providing token supply and demand for the USD denominated markets. This is reflected by the discrepancy in market depth between the two pairs. This is not the case on many other exchanges where USDT is the primary quoting asset.

It is important to remember that the bid-ask spread is quoted using the best bid and ask, or the "Top of book", so it can be misleading at times. As we can see in the ETH-USDT order book, many of the sell orders(or asks)on the "top of book" are for relatively small amounts of ETH. 

Say for example that we wanted to place a larger buy market order, say for 20 ETH. We would end up wiping out the first 8 levels of the order book until we reached the order for 18 ETH. This  "Clearing" of limit orders is the primary driver of changes in market price. For example, before our market order the mid-price of ETH would be ({2,624.95 + 2,625.57} / 2) = **$2625.26**. However after clearing the best 8 market offers (containing about 16 ETH worth of liquidity), the mid price would move up to ({2,626.36 + 2,624.95} / 2) = **$2625.66**. From this example we can see why it is important to look at multiple factors to determine the liquidity of a market, and how a lack thereof can increase our trading costs and allow price to move more easily.



