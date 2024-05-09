# IMC-Prosperity-2024, Y-FoRM
[ENG. ver link]()

## IMC Prosperity란?
- IMC Prosperity는 IMC Trading에서 주최하는 17일간의 알고리즘 및 메뉴얼 트레이딩 대회입니다.
- 가상 시장은 SeaShells라는 가상 화폐단위와 Strawberrie와 같은 제품이 거래되는 군도로 설정되어있습니다.
- 알고리즘 트레이딩의 경우, 파이썬 파일을 제출하여 limit order book에서 봇과 거래합니다.
- 올해의 주제는 마켓 메이킹, OTC 트레이딩, 바스켓 트레이딩, 옵션 트레이딩을 포함했습니다.
- 수동 트레이딩의 경우, 수학과 게임 이론에 관한 트레이딩 결정과 관련된 퍼즐이 주어집니다.

## 주요 참고 링크
- [IMC Prosperity](https://prosperity.imc.com)
- [Prosperity Wiki](https://imc-prosperity.notion.site/Prosperity-2-Wiki-fe650c0292ae4cdb94714a3f5aa74c85)
- [jmerle](https://github.com/jmerle)에게 별도의 감사를 표합니다.
- 그는 오픈소스 도구들인 [Visualizer](https://jmerle.github.io/imc-prosperity-2-visualizer/)와 [Backtester](https://github.com/jmerle/imc-prosperity-2-backtester/tree/master)는 대회참여자 모두에게 큰 도움을 주었습니다.

---

## 결과
### 최종 순위: 전체 189위 (상위 2%), 한국 5위

| 순위    | 전체 | 메뉴얼 | 알고리즘 | 국가 |
| ------ | ------- | ------ | ----------- | ------- |
| 라운드 1 | 1913    | 2263   | 674         | 12      |
| 라운드 2 | 290     | 1397   | 292         | 6       |
| 라운드 3 | 279     | 971    | 280         | 6       |
| 라운드 4 | 212     | 794    | 199         | 5       |
| 라운드 5 | 189     | 576    | 177         | 5       |

| 손익     | 메뉴얼  | 알고리즘 | 전체 | 누적 |
| ------- | ------- | ----------- | ------- | ---------- |
| 라운드 1 | 68,531  | 22,124      | 90,655  | 90,655     |
| 라운드 2 | 113,938 | 219,146     | 333,085 | 423,740    |
| 라운드 3 | 75,107  | 49,707      | 124,814 | 548,555    |
| 라운드 4 | 52,212  | 282,865     | 335,077 | 883,632    |
| 라운드 5 | 69,785  | 108,109     | 177,895 | 1,061,527  |

---

## 팀 Y-FoRM
저희는 연세대학교의 학부생들로 구성된 팀이며, 2명은 산업공학 전공, 1명은 경제학 전공입니다.
또한 저희 팀 이름에서 알 수 있듯이, 저희는 연세대학교 금융공학 및 리스크 관리 학회 [Y-FoRM](https://yform.co.kr/)의 학회원입니다.

- 임지섭 [LinkedIn](https://www.linkedin.com/in/jimmylim0823/)
- 조성윤 [LinkedIn](https://www.linkedin.com/in/seongyun0727/)
- 박상현 [LinkedIn](https://www.linkedin.com/in/sang-hyeon-park-84612a271/)

---
## 라운드 요약
1. [모든 라운드에 공통적인 고려사항](#모든-라운드에-공통적인-고려사항)
1. [튜토리얼 라운드: 마켓 메이킹](#튜토리얼-라운드-마켓-메이킹)
1. [라운드 1: 마켓 메이킹 (이어짐)](#라운드-1-마켓-메이킹-이어짐)
1. [라운드 2: OTC 트레이딩 (거래소-OTC 차익거래)](#라운드-2-OTC-트레이딩-거래소-OTC-차익거래)
1. [라운드 3: 바스켓 트레이딩 (NAV 트레이딩)](#라운드-3-바스켓-트레이딩-NAV-트레이딩)
1. [라운드 4: 옵션 트레이딩 (베가 트레이딩)](#라운드-4-옵션-트레이딩-베가-트레이딩)
1. [라운드 5: 비익명화된 거래 데이터](#라운드-5-비익명화된-거래-데이터)

### 모든 라운드에 공통적인 고려사항
- 주문장부(Order book)가 있지만, 동시에 작동하는 것이 아니라 차례로 운영됩니다 (보드 게임과 같은 턴제로 진행).
- 모든 주문은 각 시점이 지나면 취소되고 다음 타임스탬프로 재처리됩니다.
- 모든 제품은 각가의 포지션 수량 제한을 가지며, 거래량과 금액 가치로 잠재적인 손익이 결정됩니다.
- 주문이 포지션 수량 제한에 도달할 가능성이 있다면, 주문은 취소될 것이므로 주문 크기를 제한해야 합니다.
- 스크립트는 AWS에서 실행되며, 작년에는 복잡한 알고리즘을 가진 많은 팀이 Lambda 문제를 겪었습니다. (ML,DL 사용 불가)
- AWS에서는 클래스 변수가 손실될 수 있지만, `traderData`를 통해 타임스탬프 간에 직렬화된 데이터를 전달할 수 있습니다.
- Prosperity 서버가 다운되는 경우가 두 번 있었으며, 그럴 경우 대회는 24시간 연장되었습니다.
- 이전 라운드의 제품은 시장에 남아 있지만, 시장의 흐름은 변할 수 있습니다.

### 튜토리얼 라운드: 마켓 메이킹
저희는 튜토리얼에서 [트레이딩 코드](https://imc-prosperity.notion.site/Writing-an-Algorithm-in-Python-658e233a26e24510bfccf0b1df647858)의 메커니즘과 구조를 이해하는 데 대부분의 시간을 보냈습니다.
결국 저희는 공정 가치를 중심으로 시장을 만들고 포지션 제한을 고려한 손절매를 결정했습니다.

**관찰된 몇 가지 사항**
- 두 제품 모두에서 주문장부에는 주로 두 명의 에이전트가 있었습니다:
    - 매우 수동적인 마켓 메이커: 중간가격에서 +-5의 크고 대칭적인 주문을 제시합니다 (항상 worst).
    - 적극적인 트레이더 (noise or informed): 더 작고 비대칭적인 크기로 +-5 주문을 밑도는 주문을 합니다.
- 포지션 제한은 불리한 선택에 반하여 재고 관리에 일정 부분 기여합니다.
    - 인벤토리가 특정 방향으로 쌓이게 되면 해당 방향의 최대 허용 주문 크기가 감소합니다.
    - 우리는 불리한 측면에서 주문 크기를 더 줄여 자신을 보호할 수 있었습니다.

**마켓 메이킹 (MM) 로직**
1. 상품의 공정 가치(FV) 업데이트
1. 공정 가치 또는 그 이하로 평가된 주문에 market taking 진행 (worst 매수/매도 호가에는 주문을 넣지 않음)
1. 인벤토리가 특정 수준 이상으로 쌓일 경우 손절매(stop loss) (worst 매수/매도 호가에는 주문을 넣지 않음)
1. FV 부근에서 재고를 고려한 최대 주문 크기를 통해 시장을 조성

**Amethesis(상품1)**
- FV는 명확히 10k이며 중간가격은 매우 안정적(10k +- 2), 따라서 우리는 고정된 FV인 10k를 사용했습니다.
- 위의 마켓 메이킹 로직을 그대로 적용하였으며, FV 업데이트는 필요하지 않았습니다.

**Starfruit(상품2)**
- 가격에는 추세(강한 드리프트)가 있으며 하루 동안에 추세가 반전됨을 데이터에서 파악하였습니다.
- 저희는 롤링 선형 회귀(Rolling Linear Regression) $P_t=\beta_0+\beta_1 t$를 사용하여 다음 타임스탬프의 가격을 예측했습니다 $\hat{P_{t+1}}=\hat{\beta_0}+\hat{\beta_0}(t+1)$.
- [SOBI](https://www.cis.upenn.edu/~mkearns/projects/sobi.html) (정적 주문장부 불균형)를 활용하여 주문장부의 중간가격(mid price)이 아닌 중간-vwap을 데이터 큐에 저장했습니다. 이렇게 하면 소량의 최우선 매수/매도에 잡음이 있을 때 이를 제거할 수 있다고 판단하였습니다.
- 또한 저희는 heat map와 그래프를 활용하여 다양한 rolling window size를 탐색하며 최적의 예측 window를 찾았습니다.

### 라운드 1: 마켓 메이킹 (이어짐)
- 1라운드는 튜토리얼의 연장선으로, 시장 조성 주제의 게임이 계속 진행되었습니다. 그래서 저희는 데이터 분석을 통해 전략을 최적화하는 데 중점을 두었으며, 코드를 더 객체지향적일 수 있도록 Class를 활용해 지속적으로 리팩토링하였습니다.
- `Strategy` 클래스는 각 제품을 위한 기본 클래스로, Product configuration, order book features, 주문 관련 변수들(submission, expected position, sum of buy and sells)이 인스턴스 변수로 정의됩니다. 각 제품 유형별로 `Strategy` 타입의 객체를 선언하였습니다.
- `MarketMaking` 클래스는 `Strategy`의 super class로부터 상속받으며 추가적인 전략 구성을 포함합니다. `scratch_under_valued`, `stop_loss`, `market_make` 메서드가 MM 로직을 구현하고, `aggregate_orders` 메서드는 모든 3개의 주문 생성 메서드를 호출하고 주문 목록을 반환합니다. 이 주문 목록은 `Trader` 클래스의 `run` 메서드에서 Prosperity 시스템에 제출될 `results[product]`의 입력이 됩니다. `AMETHYSTS`에 대한 주문은 `run` 메서드에서 `MarketMaking` 클래스에 의해 생성됩니다.
- `LinearRegressionMM` 클래스는 `MarketMaking`의 super class로부터 상속받으며, 추가적인 롤링 회귀 구성을 포함합니다. 유일한 추가 메서드는 `predict_price`로, 외부적으로 클래스 변수에 저장된 데이터를 사용하여 선형 회귀와 예측을 수행합니다. Rolling Linear Regression은 deque를 통해 쌓은 데이터의 크기 만큼만 구현합니다. `STARFRUIT`에 대한 주문은 `run` 메서드에서 `LinearRegressionMM` 클래스에 의해 생성됩니다.
- 저희의 자본 곡선은 매우 높은 샤프 비율의 PnL을 보였으며, 거의 0의 하락을 경험했습니다. 두 제품에 대한 이익은 거의 동일했으며, 대회 종료까지 각 라운드별로 이익을 유지할 수 있었습니다.

**메뉴얼 트레이딩 문제**  
1라운드는 확률 분포와 최적화에 관한 것이었으며, 저희는 문제를 잘못 이해하여 답을 크게 놓쳤습니다. 저희는 이익을 극대화하기 위해 입찰해야 했으며, 입찰 가격은 판매자의 판매 의사 가격(저희의 입찰에 대한 판매 의사)의 확률 분포에 따라 결정되었습니다. 수동 트레이딩의 잠재적인 수익은 알고리즘 트레이딩보다 훨씬 컸기 때문에, 저희는 느린 출발과 긴 상승을 겪었습니다.

<div align=center><img src = "https://raw.githubusercontent.com/jimmylim0823/IMC-Prosperity-2/master/img/R1_PnL.png?raw=True" width="50%" height="50%"> </div>

### 라운드 2: OTC 트레이딩(거래소-OTC 차익거래)

- 대회 참여자 모두에게 가장 큰 논의가 되었던 것은 의도적으로 모호하게 제공된 제품 `ORCHIDS`의 사양을 이해하는 것이었습니다. [Prosperity Wiki](https://imc-prosperity.notion.site/Round-2-accf8ab79fdf4ce5a558e49ecf83b122)와 [Prosperity TV](https://www.youtube.com/watch?v=k4mV5XZZM-I)에 따르면, `ORCHIDS`의 가격은 햇빛과 습도에 영향을 받습니다. 그러나 제공된 데이터는 설명력이 낮고 단위가 알려지지 않아 이해하기 어려웠습니다. 저희는 분석적(함수 구축) 및 통계적(2개의 예측변수를 가진 선형 회귀, 잔차에 대한 선형 회귀 등) 방법을 시도했으나 모두 성공하지 못했습니다.
- 대신, 저희는 장외 시장 차익 거래 기회에 집중했습니다. 저희는 거래소에서 얻은 `ORCHIDS`(롱 숏 모두)를 장외 시장에서 Seashells로 전환(포지션 클로징)할 수 있었습니다. 장외시장은 독립적인 매수/매도가 있으며,호가 주도형 시장으로 교환을 위한 어떤 크기의 주문도 받아들입니다만, 운송비와 수입/수출 관세를 지불해야 합니다. 이는 일종의 싱글 딜러 플랫폼으로, 저희는 즉시 포지션을 종료할 수 있는 무한 유동성을 가졌습니다. 따라서 저희는 거래소에서 매수하거나 매도하여 장외시장에서 포지션을 종료했습니다. `OTCArbitrage` 클래스는 다음과 같은 메서드를 포함합니다:
1. `arbitrage_exchange_enter`를 사용하여 거래소에서 직접적인 장외 차익 거래 기회를 제공하는 주문을 입력할 수 있습니다. 기회는 희귀하며, 1 타임스탬프 동안 가격 변동의 위험이 있습니다. 따라서 저희는 `self.min_edge`보다 큰 차익 우위에서만 진입할 것입니다.
1. 또한 OTC 가격 + 거래 비용 + `self.mm_edge`을 통해 차익기회가 없는 가격으로 시장을 조성하였습니다.
1. 마지막으로, 모든 잔여 포지션을 장외시장에 던지며 종료하여 마진을 확보하는 `arbitrage_otc_exit`을 사용했습니다.
- 이 모든 것은 강력한 수입 관세(보조금) 덕분에 가능했으며, 해당 전략의 모든 거래는 숏으로 이루어졌습니다(장외시장에서 매수할 경우 재고비를 추가로 요구했기 때문에 기회가 거의 발생하지 않음). OTC에서의 무한 유동성은 한 방향으로 재고가 쌓이는 문제를 해결해 주었고, 저희는 2라운드에서 엄청난 이익을 얻을 수 있었습니다. 안타깝게도, 3라운드부터는 수입 보조금이 감소하여, 해당 전략으로는 수익을 거두는 것이 불가능해졌고, 해당 거래 전략에 의존하던 저희 팀과 많은 다른 팀은 누적 손익에 큰 부정적 영향을 받았으며, 대회가 끝날 때까지 습도/햇빛을 이용한 알파는 찾지 못했습니다.

**메뉴얼 트레이딩 문제**  
2라운드는 전환율 행렬이 주어진 삼각 차익 거래에 관한 것이었습니다. 저희는 행렬 크기가 작기 때문에 무차별 대입 알고리즘을 사용했습니다.

<div align=center><img src = "https://raw.githubusercontent.com/jimmylim0823/IMC-Prosperity-2/master/img/R2_PnL.png?raw=True" width="50%" height="50%"></div>

### 라운드 3: 바스켓 트레이딩 (NAV 트레이딩)
- `GIFT_BASKET`은 다음과 같은 구성품의 조합의 지수와 동등하게 여겨집니다: 4 `CHOCOLATE`, 6 `STRAWBERRIES`, 그리고 1 `ROSES` .
- 바스켓은 항상 NAV보다 프리미엄으로 거래되었으며, 저희는 바스켓-NAV 스프레드의 z-점수를 계산했습니다.
- 저희는 z-점수를 사용하여 바스켓과 구성 요소 간의 통계적 차익 거래를 시도했으나, market taking만으로는 성공하지 못했습니다.
- 바스켓은 큰 스프레드를 가지고 있었고 구성 요소는 작은 스프레드를 가지고 있었기 때문에, 저희는 구성 요소를 사용하여 책정한 'GIFT_BASKET'에 한하여 시장 조성을 진행하기로 결정했습니다.
- 저희는 공정 가치를 구성 요소의 중간-vwap를 사용하여 계산하고, 평균화된 프리미엄과 스프레드 z-점수를 추가하여 조정했습니다.
- `aggregate_basket_orders`의 메커니즘은 마켓 메이킹과 유사하게 작동합니다. `BasketTrading` 클래스는 `GIFT_BASKET`에 대해서만 주문을 생성합니다.
1. `self.basket`의 유형은 `Strategy`이고 `self.constituent`의 유형은 `Dict[Symbol: Strategy]`입니다.
1. `calculate_fair_value`는 중간-vwap, 평균화된 프리미엄, 스프레드 z-점수를 사용하여 바스켓의 FV를 계산합니다.
1. 2라운드와 유사하게, 긁어오기, 손절매, 시장 조성을 수행합니다. 그러나 두 가지 차이점이 있습니다:
   - `scratch_under_valued(mid_vwap=True)`: 공정 가치가 아닌 중간-vwap을 기준으로 저평가/적정가를 스크래치합니다 (저희는 이미 공정 가치를 업데이트했기 때문).
   - `aggresive_stop_loss`: 손절주문을 strong queue에 속한 bid/ask에 내어, 빠르게 물량을 청산합니다. 
- 저희는 대회 내내 바스켓에서 수용할 만하고 안정적인 이익을 얻었습니다. 그러나 스프레드가 0에서 1사이로 매우 작아 시장 조성이 불가능하였지만, 'ROSES'를 제외한 구성 요소를 거래하지 못한 점이 아쉬움으로 남습니다.

**메뉴얼 트레이딩 문제**  
3라운드는 게임 이론에 관한 것이었으며, 우리는 지도에서 몇 개의 그리드를 선택하여 보물을 찾아야 했습니다. 모험은 최대 3회까지 가능했으며, 비용이 크게 증가합니다. 우리는 참가자들과 함께 찾은 보물을 공유해야 했기 때문에, 가장 매력적인 옵션에 대한 경쟁을 피하려고 노력했습니다. 우리는 최고가 아닌 좋은 옵션 하나와 그럭저럭인 두 옵션을 선택했습니다.

<div align=center><img src = "https://raw.githubusercontent.com/jimmylim0823/IMC-Prosperity-2/master/img/R3_PnL.png?raw=True" width="50%" height="50%"> </div>

### 라운드 4: 옵션 트레이딩 (베가 트레이딩)
- `COCONUT`는 기초 자산이며, `COCONUT_COUPON`은 행사가격이 10,000이고 만기까지 250일(라운드)인 유럽형 콜 옵션입니다.
- 옵션 그릭스에 대한 기본 지식을 사용하여, 장기 옵션의 가격은 변동성 변화(기초 자산 가격 변화를 제외하고)에 가장 크게 영향을 받습니다.
- 계산 능력의 한계를 고려하여, [Hallerbach (2004)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=567721)에서 제공하는 분석 추정기를 사용하여 암시적 변동성을 계산했습니다. 우리는 IV가 하루 중에 높은 평균회귀 경향을 보인다는 것을 알아냈으며, 이를 기반으로 롤링 z-점수를 사용한 베가 트레이딩으로 이익을 얻기로 결정했습니다.
- 처음에는 IV의 평균회귀에 기반한 피라미드 스타일 그리드 트레이딩을 시도했습니다. 하지만 z-점수가 낮을 때 신호가 약하다는 것을 발견하고, 트레이딩 스타일을 임계값 아래의 피라미드 하단을 자르는 사다리꼴 스타일로 수정했습니다. 놀랍게도, z-점수가 낮은 근처(1.5 근방)에서 모두 투자하는 것이 가장 수익성이 높았습니다.
- 처음에는 델타 헤징을 시도했고, 이로 인해 지속적인 손실이 발생했습니다. 우리의 감마는 비슷한 비율로 길고 짧았지만, 장기 옵션의 낮은 감마로 인해 우리가 지불해야 할 것은 스프레드와 짧은 감마로 인한 일부 손실뿐이었습니다. 우리는 헤지를 할지, 하지 않을지, 또는 헤지를 전환할지 결정해야 했습니다. 우리는 헤지를

 제한적으로 사용하기로 결정했으며, 이는 긍정적인 결과를 가져왔습니다.

대회는 많은 학습과 도전으로 가득했습니다. 우리는 트레이딩의 다양한 방법과 전략을 실험하며 각 라운드의 독특한 요구사항에 맞게 전략을 조정했습니다. 결과적으로, 저희 팀은 새로운 접근 방식과 함께 시장에서 적응력을 높이며 다양한 상황에서 기회를 찾는 방법을 배웠습니다. 이러한 경험은 향후 금융 시장에서의 커리어에 큰 자산이 될 것입니다.
**메뉴얼 트레이딩 문제**  
4라운드는 1라운드와 비슷했지만 게임 이론이 추가되었습니다. 모든 참가자의 평균 입찰가에 의해 결정되는 구매 의사의 확률 분포가 있었습니다. 저희는 보수적인 접근을 선택하고 최선의 답에서 너무 멀어지지 않았습니다.

<div align=center><img src = "https://raw.githubusercontent.com/jimmylim0823/IMC-Prosperity-2/master/img/R4_PnL.png?raw=True" width="50%" height="50%"> </div>

### 라운드 5: 비익명화된 거래 데이터
- 5라운드에서는 새로운 제품이 소개되지 않았지만, 시장 거래와 개인 거래 모두에서 거래자(매수자 및 매도자)의 이름이 표시되었습니다.
- 저희는 중간 가격을 표시하고 주어진 거래자가 매수하고 매도한 타임스탬프를 레이블하여 각 거래자의 특성에 대한 통찰을 얻었습니다.
- 특정 거래자의 이름 첫 글자(A, R, V)와 관련된 몇 가지 패턴을 발견했습니다:
  - A로 시작하는 거래자(아마추어를 의미하는 듯?)는 시장을 잘못 이해하고, 항상 반대 방향으로 거래했습니다.
  - R로 시작하는 거래자(신참을 의미하는 듯?)도 시장을 잘못 이해하는 경우가 많았습니다.
  - V로 시작하는 거래자(베테랑을 의미하는 듯?)는 시장 만들기를 잘하고 대부분 고빈도 거래를 했습니다.
- 거래 크기와 미래 가격 움직임 사이의 관계를 발견했습니다.
- 거래량과 PnL 사이의 선형 회귀는 좋은 P-value를 보였지만 R-squared 값은 좋지 않았습니다.
- 모델 적합도에 따라 신호를 조정하기 위해 회귀 계수에 R-squared 값을 곱하여 신호를 집계하기로 결정했습니다.
- 좋은 P-values는 1라운드 제품에서만 발견되었으며, 다른 제품들은 모델 적합도가 좋지 않았습니다.
- 거래자 기반 신호는 `AMETHYSTS`와 `STARFRUIT`에만 적용되었지만, 추가 이익은 미미했습니다.

**메뉴얼 트레이딩 문제**  
5라운드는 뉴스 트레이딩에 관한 것이었습니다. 북부 군도에서 가장 신뢰할 수 있는 뉴스 소스 "Iceberg"(Bloomberg가 아님)를 기반으로, 저희는 총 포지션 한도 100%로 매수와 매도 포지션을 배분해야 했습니다. 저희는 모든 제품에 대해 포지션을 취함으로써 몇몇 잘못된 답변의 영향을 줄이려고 했습니다. 저희는 5개의 정답과 4개의 오답을 얻었지만, 올바른 답변 하나의 이익이 잘못된 답변들의 손실을 모두 상쇄할 수 있었습니다.

<div align=center><img src = "

https://raw.githubusercontent.com/jimmylim0823/IMC-Prosperity-2/master/img/R5_PnL.png?raw=True" width="50%" height="50%"> </div>

---

## 마무리
- 많은 알고리즘 트레이딩 대회 중에서도 IMC Prosperity는 매력적인 스토리라인과 잘 설계된 그래픽으로 높은 몰입력을 제공합니다. 진행 도중 다양한 문제가 있었지만, Python을 활용한 알고리즘 트레이딩을 경험할 수 있는 매우 즐거운 경험이었습니다.
- 대회 진행 도중 예상치 못한 서버 다운이 2번 발생하여 많은 참가자들의 일정에 불편을 초래했습니다. 또한 4라운드의 경우 지난 대회의 데이터와 중복이 되는 부분이 있었기에, 이를 파악하여 오버피팅을 진행한 팀들이 높은 성적을 올릴 수 있었다는 문제도 있었습니다. 그럼에도 불구하고 이토록 매혹적인 이벤트를 주최해 준 IMC에 감사의 마음을 전합니다.
- 그리고 이 대회를 소개해주고 같이 팀으로 참여한 지섭이에게 깊은 감사를 표합니다. 그의 주도로 우리는 시장 미시구조, CLOB, 객체지향 프로그래밍, 알고리즘 트레이딩 전략을 깊이 있게 탐구할 수 있었습니다. (고맙다! 지섭아!)
- 또한 어려운 난이도에도 불구하고 포기하지 않고 메뉴얼 트레이딩 문제를 담당하고 꼼꼼하게 회의록을 작성해준 상현이에게도 진심으로 감사를 표합니다. (고생했다! 상현아!)
- 시험 기간과 겹쳐 시간이 매우 부족했음에도 불구하고, 매일 자정부터 2시간 이상 Zoom 회의를 하여도 싫은 소리 하나 없던 우리 팀! 너무 고마워! 덕분에 너무너무너무 재밌었어
- 만약 Prosperity3가 개최된다면, 저는 다시 참여할 계획이며 한국에서도 더 많은 사람들이 관심을 가지고 참여하기를 바랍니다.
- 이 글이 Prosperity를 처음 참여하게 되는 사람들에게 등대와 같은 역할을 할 수 있으면 좋겠습니다 :)