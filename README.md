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

### Round 3: Basket Arbitrage Trading <br>
- Buying Undervalued Places Comparing ETF NAV And Component (1CU) <br>

<details>
 <summary> Official TV Broadcasting Summay </summary>
  1. 이전 라운드의 트로피칼 거래가 종료되었으며, 선수들은 성과를 확인하고 전략을 조정해야 합니다.    <br> 
  2. "러브 버그"가 열대 군도 전역에 퍼졌으며, 거래자들은 자신의 crush들을 감동시키기 위해 딸기, 초콜릿, 장미가 포함된 선물 바구니를 구매하도록 권장됩니다.     <br>
  3. 신비한 메시지가 담긴 병이 해안가에 떠밀려왔으며, 그 안에 전설적인 이구아나 존스의 보물 지도가 있었습니다. 보물 상자에는 각각 7,500개의 조개 껍질이 들어 있습니다.     <br>
  4. 거래자들은 첫 번째 탐험은 무료지만 이후의 탐험에는 비용이 발생하며, 같은 위치를 표시한 모든 사람들과 보물을 나누어 가져야 하므로, 보물 위치를 표시하는 탐험을 권장받고 있습니다.    <br> 
  5. 진행자는 거래자들이 빨리 행동해야 한다고 상기시키며, 약탈자들이 이미 움직이고 있고 이는 부자가 될 수 있는 평생 한 번뿐인 기회라고 말합니다.     <br>
</details>

<details>
 <summary> R3 Manual Trading </summary>
  첫 번째 탐험은 무료지만, 두 번째와 세 번째 탐험에는 비용이 발생합니다. 자신만이 탐색하고 있는 것이 아니라는 점을 염두에 두어야 하며, 같은 장소를 탐색하는 다른 사람들과 보물을 나누어야 합니다. 탐험을 신중하게 계획하면 가장 큰 보물을 가져올 수 있습니다.   <br> <br>
 
  탐험의 수익은 다음과 같이 계산됩니다:   <br> <br>

   - 각 장소마다 **보물 배수율**(최대 100)과 **사냥꾼들**(최대 8)이 있습니다.   <br>
   - 해당 장소의 총 보물은 **기본 보물**(7500, 모든 장소에서 동일)과 그 장소의 특정 보물 배수율의 곱입니다.   <br>
   - 그러나 그 결과 금액은 사냥꾼의 합과 (다른 플레이어의) 모든 탐험의 백분율(%)에 의해 나뉩니다. 예를 들어, 어떤 필드에 5명의 사냥꾼이 있고 모든 탐험의 10%가 그곳으로 향한다면, 그 필드에서 받는 상금은 15로 나뉩니다.   <br>
   - 나눈 후에는 **탐험 비용**(있는 경우)이 적용되며, 남은 것이 수익이 됩니다.   <br> <br>

  두 번째와 세 번째 탐험은 선택 사항이며, 모든 3회를 해야 할 필요는 없습니다. 제출된 탐험 순서는 등급에 영향을 미치지 않습니다. <br>
</details>

<details>
 <summary> How to Solve </summary>   <br>
  <details>
   <summary> Main Approach </summary>   <br>
    ** OTC Arb 매우 유사 **   <br>
    1. 공정가치 평가->엣지 확인   <br>
    2. basket make cu take 유리   <br>
    3. under-valued basket take   <br>
    4. edge를 확보할 수 있는 pricing으로 basket make   <br>
    5. 예측 기반 pricing edge 있으면 shift ?   <br>
  </details> <br> <br>
 
  <details>
   <summary> 고민사항 </summary>     <br> <br>
    1. mid_vwap 으로 spread: ok     <br>
    2. bid ask 따로 pricing 어떤 bid / ask, best? vwap? worst?   <br>
     - basket take: basket best cu best 평가 -> for loop min_edge까지   <br>
     - baset make: cu worst로 공정가치 평가해서 market make   <br>
    3. mean->basket premium (깔끔한 숫자: 380), std: day012전체의 표편 -> mid_vwap으로 내기   <br>
    4. 진입 시그널 = mm_edge -> k * spread_std, set k = 0.5   <br>
     - 포지션 비례해서 k를 조정 58세트 -> 좀 생각해봐야함     <br>
    5. market taking: spread > 0.5 -> short spread (반복) -> spread > 1 (손실누적) 시그널=2   <br>
    6. 리니어 / 이차함수 또는 분모하는 형태로   <br>
    7. marekt making: 동일   <br>
    8. 진입 시그널/mm_edge 작을 수록 체결 확률이 높아서 불리하게 움직일 가능성 높음   <br>
  </details>
   
</details>
 <br> <br>

### Round 4:  Call Option Trading (vega trading while hedging delta)  <br>
- "Theta": Sensitivity Over Time of Options. <br>
- Round reflecting value over time. <br>


 <br> <br>

### Round 5: Multi-agent  <br>
- In this round, the information and characteristics of the orderer are provided (i.e. multi-agent round) <br>
- At this time, the use of the concept of "Market Microstructure". <br>
 - Traditional economic theory that prices are continuous and found? Wrong <br>
 - Prices are discontinuous and formed by market participants <br>

 <br>

