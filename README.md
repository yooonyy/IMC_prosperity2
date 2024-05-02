---
# IMC-Prosperity-2024, Y-FoRM

## Major Reference Links
- Official Hompage of IMC (https://prosperity.imc.com) <br>
- Official Discord of IMC (https://discord.com/invite/KajAga3sFz) <br>
- Official Notion of IMC (https://imc-prosperity.notion.site/Prosperity-2-Wiki-fe650c0292ae4cdb94714a3f5aa74c85) <br>


#### Final Rank: ? th of n teams


---
## Team < Y-FoRM >

Yonsei Forum of Risk Management <br>
Y-FoRM's algorithms in IMC Prosperity 2024!

Ji Seob Lim  <br>
Seong Yun Cho  <br>
Sang Hyeon Park  <br>


---
## Round Details

### Common Content for All Rounds <br>
1. A kind of individual turn system. <br>
2. Orders are cancelled at every point in time, so re-processed to next timestamp. <br>
3. Based on AWS, so performance is limited. Need to simplify operations.(At most, linear regression) <br>
4. If server goes down(It happens sometimes), they might give you additional 24hours for given round.
 <br> <br>

 
### Round 1: Market Making(MM) <br>
- Market Creation (Contract with Exchange) <—> LP Liquidity Supply (Individual Products, Contract with Issuer) <br>
- Market Making ~ Designated Quote Offer <br>
- Market Taking ~ Market Street <br>

 <details>
  <summary> Official Description for Round 1 </summary>  <br>
 
   Version history <br>
   Your uploaded algorithms are evaluated against historic data. Results in the log output are not indicative of performance in the next round. <br>

   STEP 1 <br>
   Use the Wiki and all other information you can find to write your algorithm. <br>

   STEP 2 <br>
   Upload your algorithm here (you can re-upload another algorithm as often as you like. The newest accepted file will overwrite the previous one.) <br>

   STEP 3 <br>
   You will receive your results in the next game round. <br>

<details>
  <summary> Description Summary </summary>
  **"Amethesis"** <br>

  1. The fair value of it is very clear (10000) <br>
  2. So it was easy to Market Making and Taking given its fair value <br>

  **"Starfruit"** <br>

  1. A price of it is not stationary, so we tried its fair value by using rolling linear regression.
  2. Searched various periods and shifts by heatmap and multi plot.
  3. 
</details>
 
 <br> <br>

### Round 2: OTC Arbitrage Trading <br>
- "Statistical Arbitrage": Arbitrage trading based on the process of returning to the law of "one's work. <br>
- Not economical, But statistical. <br>
- "Pairs trading": Two highly correlated stocks sold up (high valuation) and down (low valuation) after normalization. <br>
- At this time, covariance is also used to normalize. <br>

<details>
  <summary> Description Summary </summary>
  **"Orchid"** <br>
 
  1. 내가 위치한 아키펠라고(군도)의 거래소(시장)에서 사는 방법 <br>
 
  2. 남쪽의 오리들이랑 거래 (conversion): 수출입   <br>
   - 살때: 오리가 제시한 매도호가 + 수송비용 + 수입관세   <br>
   - 팔때: 오리가 제시한 매수호가 + 수송비용 + 수출관세   <br>
  오키드를 가지고 있으면 보관비용 발생 (상수 = 0.1)(cost of carry) - OTC Forward와 유사   <br>
  오키드의 가격 결정 요인: 수송비용, 수출입관세, 보관비용, 습도, 일조량에 영향 - 영상에서 benchmark   <br>
 
  3. Sunlight   <br>
   - f sunlight < 7 hours a day:   <br>
     production decrease 4% for every 10 minute   <br>
      → 일간 일조량: 7시간 이상: a원   <br>
      → 6시간 50분: 0.96a   <br>
      → 6시간: (-1시간 = -6*10분) = (1-0.04 * 6) * a = (1 - 0.24)a = 0.76a   <br>

   4. Humidity   <br>
    - if ideal humidity not in 60~80%:   <br>
     production decrease 2% for every 5%p of humidity change   <br>
      → 습도 60 ~ 80 % 적정: a원   <br>
      → 2% 감소 / 5%p 변화   <br>

   5. Storage <br>
    - max storage 5000, storage fee 0.1 seashell / orchid timestamp <br>
</details>


 <br> <br>

### Round 3: Basket Arbitrage Trading <br>
- Buying Undervalued Places Comparing KOSPI 200 ETF NAV And Component (1CU) <br>

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

### Round 4:  Call Option Trading (vega trading while hedging  <br>
- "Theta": Sensitivity Over Time of Options. <br>
- Round reflecting value over time. <br>


 <br> <br>

### Round 5: Multi-agent  <br>
- In this round, the information and characteristics of the orderer are provided (i.e. multi-agent round) <br>
- At this time, the use of the concept of "Market Microstructure". <br>
 - Traditional economic theory that prices are continuous and found? Wrong <br>
 - Prices are discontinuous and formed by market participants <br>

 <br>

---
## Proceedings

### 04/05 00:00 Meeting

<details>
 
 <summary> Due 04/07 </summary>   
  1. Basic Market making Logic Thinking <br>
  2. Inventory Management Sys needs to be managed well (but how?) <br>
  3. Signal Section & Intergrating (Maybe due to the release of the 2nd place code, this is the part that distinguishes the top ranks in this competition) <br>
 
</details>
  
### 04/07 00:00 Meeting
<details>
  <summary> Due 04/08 </summary>  

   1. Starfruits Rolling Regression(SY)
   
   2. Markdown(SH)
    
   3. AM 어디까지 undercut할지(JS)
      
   4. AM parameter tuning(optimization ASAP)(SH) <br>
      a. cf. tutorial.py <br>
      b. dec.var: SL_INVENTORY, SL_SPREAD, MM_SPREAD <br>
      c. obj: max P/L <br>
      d. constaints: <br>
          (1) 0 ≤ SL_INVENTORY ≤ 20 <br>
          (2) 0 ≤ SL_SPREAD ≤ MM_SPREAD ≤ 4 <br>
          (3) SL_INVENTORY, SL_SPREAD, MM_SPREAD integer <br>
            ⇒ 하나씩 늘리지 말고 (상중하, 상 중상 중 중하 하) 적당히 구간 나눠서 대충 파악하기 naive하게..
    
   5. AM  안움직이는 구간 해결해야함. 분석하기 (552, 710, 1020..) (SH) <br>
      a. log 파일 가져와서 시각화해서 뭐가 문제였을까 분석 “position_no_change.log” 참고 <br>  
          ⇒ 포지션 상태(중립, 수량적은지 많은지), 호가 뎁스, 전후 거래량 많은지 적은지 <br>
          ⇒ 예측 가능한지, 얼마나 빨리 식별 가능한지, 어떻게 대응할지.. 강제로 턴다든가 등등.. 묶여있는 상태일 수도 있으니까 어떻게 해결해야 하는 건지를 분석 <br>
          ⇒ 우리 position의 resting time(time to change in p/l)이 얼마나 되는지. 멈춰있는 구간의 길이를 따져보고 우리가 얼마나 안 움직이고 있으면 비정상인건지 ( = 얼마 안에 털어야 정상인지!) <br>
        
   6. Starfruits base model coding(SY) <br>
      a. 복붙(변수명만 다 고치기) <br>
      b. 데이터 저장 (queue로!) <br>
      c. window 전까지 임시 회피코드 (fix value) <br>
      d. fair value를 rolling regression y predict로 대체 <br>
      e. window 전까지 임시 회피 개선 <br>

   7. visualizer logger(SH) - optional

</details>

<details>
 
  <summary> Due 04/09 </summary>  
  1. Inventory Model Implementing: fair value, mm_spread, order_quantity <br>
    a. inventory positive → fair value 높여야함, inventory negative → fair value 낮춰야함 <br>
  
</details>

 <br> <br>
 
### 04/08 00:00 Meeting


<details>
 
  <summary> Due 04/09 II </summary>  
  
   1. stop loss order 0개 해결 (JS)   <br>
   2. starfruit deque로 담기 (SY)   <br>
   3. 전반적 inv 관리   <br>
   4. 최후 청산   <br> 
   5. 가격리스트 → (ARIMA 참고해서) TR, DI 코딩 (SH)   <br>
   6. csv mid_price 롤링윈도우 20으로 해서 TR(n) DI(n) 가격 범위 찾기 (SH) (cf.https://www.grahamcapital.com/blog/the-trendiness-of-markets/)   <br>
   +. Trader class 안에 (INSTANCE VARIABLE로 담아보기 + DICT  형식으로)   <br>
       - class trader 바로 밑에 생기기   <br>
       - data = {’STARFRUITS’:{’PRICE’:deque()}}   <br>
       - 일단 가격이 담기는지 확인해보고 담기면 predict 추가 <br>
  
</details>
 
 <br> <br>

### 04/09 - 04/10 all night

<details>
  <summary> todo list </summary>  
 
   1. inv 관리   <br>
   2. 최후 청산   <br>
   3. 선형회귀 반영 및 고도화 (cf. Graham Capital Management)     <br>
</details>

 <br> <br>

### 04/11 00:00 Meeting

<details>
  <summary> Due 04/11 </summary>  
 
   1. Scratch best but also worst bid   <br>
   2. floor ceil → market make fair value   <br>
   3. scratch level vs SL level → market take   <br>
   4. scratch를 포지션 방향과 무관하게 할까? (caution: stop loss와의 중복 주문) ⇒ 만약 잘되면 AM에도 적용   <br>
   5. parameter tuning   <br>
   6. 파일 일괄화 → 최종 파일 github에   <br>
   7. Manual Trading (SH) <br>
</details>

 <br> <br>

### 04/12 00:00 Meeting

<details>
  <summary> Due 04/12 </summary>  
 
   <details>
    <summary> [Pricing] </summary>     <br>
     1. sunlight unit(단위) 확인 (0.1 minute이 맞는지) (SH)   <br>
     2. storage data 어디서 얻을 수 있는지 (SH)   <br>
     3. sunilght, humidity: feature engineering: 그냥 회귀 때리지 말고 어떤 함수를 씌운 다음에 회귀 돌려야함 (SY)   <br>
       - 0 = f(sunlight, humidity,  storage) → 이거에 대한 pricing funtion을 만들어야..    <br>
     4. 안정적으로 계수 추정하는 multivariable linear regress (on the fly(데이터가 하나씩 추가되면서 n번째에는 n개 데이터로 하는 거) / rolling 불가!) ← QR decomposition / inverse matrix (SY)   <br>
     5. hard coding VS rolling(numpy를 사용하자..) (SY)   <br>  
     6. regress를 통해 뭘 찾을지 (price / diff / return 중에서..) (JS)   <br>
     7. cost of carry 반영 어떻게 할 건지 (JS)   <br>
   </details>

   <details>
    <summary> [Trading] </summary> <br>
     8. 기회 식별 어떻게 할 건지 (very good fair value가 필요함)   <br>
     9. 위험 관리 어떻게 할지   <br>
     10. 거래소 내에서는 make? take? where? (spread가 굉장히 크기 때문에..)   <br>
   </details>
   
   <details>
    <summary> [Manual Trading] </summary>   <br>
    - brute force   <br>
    - dijkstra algorithm(멋있게 풀고 싶다면) (cf. https://reasonabledeviations.com/2019/03/02/currency-arbitrage-graphs/)   <br>
   </details> 
</details>
 
 
 <br> <br>

 
### 04/13 00:00 Meeting

<details>
  <summary> Due 04/13 </summary>  
   1. day 0에 overfitting해서 pricing function (SY)   <br>
   2. fair value VS OTC VS exchange → arb (JS)     <br>
   3. OOP 구조 개선 (JS)   <br> 
   4. manual trading (SH)   <br>
   5. traderData (SH)   <br>
    - STARFRUIT 가격 data->손실 <br>  
    - traderData로 복원   <br>
    - data->toJSON->traderData 보내기->if 데이터 손실->traderData 받아오기->data 복원   <br>
</details>

 <br> <br>
 
### 04/14 00:00 Meeting

<details>
  <summary> Due 04/14 </summary>  <br> 
  1. heuristic pricing for shift (좋좋 좋안 안좋 안안) (SY)
  2. traderData (JS) <br>
  3. 코드 소화 및 도큐먼테이션 (SH) <br>
</details>

 <br> <br>

### 04/15 00:00 Meeting
 
<details>
  <summary> Due 04/15 </summary>   <br>
  1. 코드 베이스 만들기: OTC ARB 재탕 -> JS   <br>
  2. eda 리서치: mid_vwap 기준 평균 및 표준편차 계산, 진입시그널 k에따라서 빈도 히스토그램, drawdown period 분포 -> 곱하면 기대값 → SY   <br>
  3. 매뉴얼챌린지, 라운드2 패러미터 튜닝 -> SH   <br>
   - 매뉴얼 챌린지: 다른 참여자 없다하고 최적화 -> 그 결과를 모든 참여자가 따른다하고 최적화 -> 2~3회 반복   <br>
   - 라운드2: min_edge, mm_edge 튜닝 (라운드2 백테 50k 이상 나오는 조합들만), mm_edge 먼저 최적화 후 min_edge    <br>
</details>

<br> <br>




---
## Results

### Round 1
{
"Round_1": {
            "Overall_Rank": 1913, "Manual_Rank": 2263, "Algorithmic_Rank": 674, "Country_Rank": 12,
            "Manual_PL": 68.531, "Algorithmic_PL": 22.124, "Overall_PL": 90.655, "Cumulative_PL": 90.655
            }, 


### Round 2



---
## Version History

* 0.1.1  
  2024-04-08 (Initial Release / Round 1 begins)  
* 0.1.2  
  2024-04-09  
* 0.1.3  
  2024-04-10  
* 0.2.1  
  2024-04-11 (Round 2 begins)
* 0.2.2  
  2024-04-13  
* 0.3.1    
  2024-04-14 (Round 3 begins)    
* 0.3.2  
  2024-04-16 (시험 기간 )  
 
---
## License

This project is licensed under the [MIT] License - see the LICENSE.md file for details
