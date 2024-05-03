# IMC-Prosperity-2024, Y-FoRM

## Major Reference Links
- Official Homepage of IMC: [https://prosperity.imc.com](https://prosperity.imc.com)
- Official Notion of IMC: [https://imc-prosperity.notion.site/Prosperity-2-Wiki-fe650c0292ae4cdb94714a3f5aa74c85](https://imc-prosperity.notion.site/Prosperity-2-Wiki-fe650c0292ae4cdb94714a3f5aa74c85)
- special thanks to jmerle : visualizer for results of submissions and local backtests (available online at [jmerle.github.io/imc-prosperity-2-visualizer/](https://jmerle.github.io/imc-prosperity-2-visualizer/)).

#### Final Rank: 189th overall (top 2%), 5th in Korea.

### Round Results

| Rank   | Overall | Manual | Algorithmic | Country |
|--------|---------|--------|-------------|---------|
| Round 1| 1913    | 2263   | 674         | 12      |
| Round 2| 290     | 1397   | 292         | 6       |
| Round 3| 279     | 971    | 280         | 6       |
| Round 4| 212     | 794    | 199         | 5       |
| Round 5| 189     | 576    | 177         | 5       |

| PnL    | Manual | Algorithmic | Overall | Cumulative |
|--------|--------|-------------|---------|------------|
| Round 1| 68,531 | 22,124      | 90,655  | 90,655     |
| Round 2| 113,938| 219,146     | 333,085 | 423,740    |
| Round 3| 75,107 | 49,707      | 124,814 | 548,555    |
| Round 4| 52,212 | 282,865     | 335,077 | 883,632    |
| Round 5| 69,785 | 108,109     | 177,895 | 1,061,527  |

---
## Team Y-FoRM

Yonsei Forum of Risk Management (Y-FoRM) algorithms in IMC Prosperity 2024!

- Ji Seob Lim
- Seong Yun Cho
- Sang Hyeon Park

---
## Round Summaries

### Common Content for All Rounds <br>
1. A kind of individual turn system. <br>
2. Orders are cancelled at every point in time, so re-processed to next timestamp. <br>
3. Based on AWS, so performance is limited. Need to simplify operations.(At most, linear regression) <br>
4. If server goes down(It happens sometimes), they might give you additional 24hours for given round.

### Tutorial Round
We spend most of our time in tutorial, understanding how the competition was going and how the algorithm worked.
At the end, we made our mind to deal with this round with Market Making and Market Taking by considering limit position.
There were two products that we was going to trade.

 **Amethesis"** <br>
 1. The fair value of amethesis was very clear (10000) <br>
 2. So it was easier than starfruit to Market Making and Taking given its fair value <br>

 **"Starfruit"** <br>
 1. A price of it was not stationary, so we tried its fair value by using rolling linear regression.
 2. Searched various periods to predict its fair value by heatmap and multi plot.

### Round 1: Market Making(MM) <br>
The algo side of round 1 appeared to be a continuation of the tutorial round on new data.
So we re-checked our algorithms logics and focused on reconstructing the code in a more object-oriented way. 

### Round 2: OTC Arbitrage Trading <br>
It was the most incomprehensible round.
The featured product was 'Orchid', which, according to official documentation, is sensitive to variations in sunlight and humidity.
However, the provided data was insufficient as it did not fully align with the descriptions in the document, making it challenging to use climate data as a leading or explanatory indicator for pricing. During the competition, there was significant debate on Discord among participants regarding the utility of climate data in our trading strategies. Ultimately, it was concluded that climate data was unsuitable for strategic purposes in this context. Initially, we attempted a preemptive pricing strategy based on climate data, but this approach was rejected.

Instead, the main strategy shifted to focus on arbitrage in the over-the-counter (OTC) market. Unlike Round 1, Round 2 allowed for OTC trades, which introduced more dynamic strategic options due to unexpectedly favorable conditions, such as lower than anticipated import tariffs and subsidies that reduced the impact of export tariffs.
The allowance for OTC trading meant that positions could be cleared more rapidly than in the previous round, making our approach more flexible and responsive. This strategic shift helped us to capitalize on market inefficiencies more effectively and adapt our tactics to the evolving trading environment.

Manual Trading was about triangular arbitrage.

### Round 3: Basket Arbitrage Trading <br>

Round 3 introduced the GIFT_BASKET, akin to an ETF product, accompanied by detailed data on each component's price and weight within the basket. This allowed us to calculate the Net Asset Value (NAV) of the gift basket.

By comparing the calculated NAV with the actual basket price, we determined the premium or discount at which the basket was trading. Utilizing the z-score of this premium, we calculated the expected price shift. This price shift was then added to the current market price to establish the Fair Value of the basket. Armed with this valuation, we employed a Market Making and Taking strategy similar to the previous rounds.

This round was particularly engaging as it mirrored real-world trading scenarios where ETFs do not always align perfectly in price movements with their underlying assets. The strategy not only tested our ability to quickly adapt and calculate under pressure but also allowed us to exploit these inefficiencies for potential gains.

Manual trading was about game theory.

### Round 4:  Call Option Trading (hedging delta and exposing to vega) <br>
4라운드는 COCONUT, COCONUT_COUPON으로 위장한 call option trading 라운드 였습니다.




### Round 5: Multi-agent  <br>
- In this round, the information and characteristics of the orderer are provided (i.e. multi-agent round) <br>
- At this time, the use of the concept of "Market Microstructure". <br>
 - Traditional economic theory that prices are continuous and found? Wrong <br>
 - Prices are discontinuous and formed by market participants <br>

 <br>

