---
title: "[IFRS Issue Paper 222] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ①"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240912152302571hg"
---
![](https://n2.news.naver.com/l.gif?type=content)**222**

**● Option valuation models**

​

이항모형은 전환금융상품과 Stock-Option(share-based compensation under IFRS2)의 공정가치에 적용되는 공통모형이다. 이항모형의 가장 큰 장점은 적용의 편리성이다. 이 장점은 기초자산(주가)의 변화를 특정 비율로 상승(Up) 또는 하락(Down) 2가지 시나리오만 가정하는데서 오는 것이다. 상승, 하락 비율과 함께 발생확률은 수학적인 기법을 통해 산출된 것이다. 이 두 변수는 이항모형의 핵심변수로 부여시점의 주가를 Stock-Option 행사기간 단위로 만기까지 확장시키는 Tree를 생성시키게 되고 각 시점의 주가와 행사가격의 차이는 그 시점의 option value를 생성하고 이들을 소급 현재가치화 하여 부여시점의 Option value를 결정하게 한다.

​

아래 그림은 이항 Tree를 단순 형상화 한 것이다. 미래의 추정 주식가격은 행사시점의 주가를 출발점으로 이항모형에 의해 상승, 하락을 반복하면서 펼쳐져 나간다. 이 때 필요한 변수는 상승계수(u)와 하락계수(d)이며 이 두 변수는 ① 부여시점의 주가, ② 무위험 이자율, ③ 주가 변동성, ④ 기간(시간) ⑤ 배당 5가지 변수에 의해 결정된다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MTJfMTEz/MDAxNzI2MTE3OTU3NTEw.LviyDutBntGgT4pKtyaaTI8TacAGup6VhkomAO0WZOAg.F07dnl-X_C0qOTUZ_U6OPKqGss7WOn0Zhx8OzQJOUOYg.PNG/image.png?type=w800)

이항모형의 주가 상승, 하락 Tree (source ; KPMG IFRS2 Hand-book)

​

주가 Tree는 미래 행사시점의 option value(내재가치)를 계산하기 위함이다. 각 시점의 주가와 행사가격의 차이는 0을 하한으로(option이므로) 그 시점의 옵션가치이다. 위에서 상승과 하락의 확률은 계산되어 있으므로 이 확률에 의한 가중평균값이 전단계 옵션가격이 되는 것이다. 이런 방식으로 위에서 만들어진 주가 Tree의 모든 시점별로 옵션가치는 계산되고 결국 맨 왼쪽 부여일의 옵션가치도 계산되는 것이다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MTJfNTEg/MDAxNzI2MTE4NjM2NzY3.95mD056Njf829pAZYrRCXdfKzXdUUbEmtrYGp_70Jckg.6E53o43I4OSDgLGu8ylcPw-1pn--80ehMVpI9FpACqYg.PNG/image.png?type=w800)

이항모형에 의한 옵션가치의 계산 (source ; KPMG IFRS2 Hand-book)

상식적으로 주가는 수많은 시나리오를 가질 것이다. 이 수많은 시나리오를 평가모형에 반영하는 것은 어려울 뿐 아니라 분석의 과정을 지나치게 복잡하게 만든다. 따라서 이항모형은 상승(by 상승계수), 하락(by 하락계수) 2가지 Step만 밟는다고 가정된다. 이 각각의 단계를 노드(node)라고 부른다.

​

가장 단순화된 모형인 Black-Scholes-Merton(BSM) 모형의 단점을 극복하기 위해 다소 복잡한 경우의 수까지 고려하는 방법이 2가지 있는데 "Lattice model(binomial model)"과 "Monte-Carlo-Simulation"이다.

​

Lattice model은 binomial model로써 BSM에서는 고려하지 못했던 Stock Option의 조기행사(early exercise)를 고려할 수 있다. 실제 Stock-Option이 BSM의 가정인 각 기간말(Node 시점)에만 행사되는 것만은 아닐 것이다. 즉, 옵션가치가 각 노드시점의 할인된, 가중평균 내재가치만은 아니라는 점을 고려한 것이다. 노드와 노드 사이 기간에도 주가와 행사가격의 차이에 따라 행사가능성이 존재한다. BSM과 달리 Lattice model은 S/X 비율(이 비율이 높을 수록 행사가능성은 높아진다), 가득기간 종료 후 종결되는 비율, 배당금 지급 등을 고려함으로써 Stock-option의 조기행사를 가치평가에 고려한다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MTJfMTY2/MDAxNzI2MTIyMzA4MDg3.p8yjsOy-OF0gqyFLBYahFhVy3qW01DiX0WV37rS-iqsg.kxF039uBqiFlKUeu1A9PdDcr4DqxjBQ-GRTHNhis66gg.PNG/image.png?type=w800)

​

**● 평가모델의 선택**

**​**

**실무적으로 IFRS2에 따른 재무보고 목적의 Stock-option 평가모델은 단순화된 모형(Black-Scholes-Merton)보다는 Lattice model(binomial model)이나 Monte Carlo models과 같은 보다 복잡한 조건을 해결할 수 있는 모형의 사용이 권고 된다. BSM은 가장 단순한 모델로 적용이 간편하다는 장점이 있지만 시장조건(market condition)이나 옵션 조기행사 가능성을 반영하지 못하는 한계점이 있기 때문이다.**

**​**

1. **Closed-form models ; e.g. the BSM model**
2. **Lattice model**
3. **simulation model ; e.g. Monte Carlo models**

**​**

**위 모들은 만약 동일한 가정을 적용한다면 대체로 결과값도 비슷하게 산출된다. 그러나 어떤 Stock-Option 계약조건은 결제방식과 적용할 가정이 일반적이지 않거나 복잡할 수 있다. 가령, BSM 모델도 계약상 기간보다 짧은 기대기간 가정을 사용함으로써 조기행사 가능성을 평가에 고려할 수 있다. 반면 Lattice 모델이나 Monte Carlo model은 보다 복잡한 조기행사 가능성(early exercise behavior)을 모델에 녹일 수 있다.**

**​**

**모델의 선택은 보상의 복잡성(가령, 시장조건을 가진 보상에 BSM을 적용할 수는 없다), 단순히 시간(time) 보다 더 신뢰성 있는 조기행사 지표를 추정할 수 있는 능력에 의존한다. 그러므로 비록 Lattice 또는 Monte Carlo model이 보다 복잡한 조기행사 가능성을 모델링화 할 수 있더라도 해당 지표가 신뢰성 있고 이용가능해야 한다.**

**​**

![](https://scs-phinf.pstatic.net/MjAyNDA5MTJfNjIg/MDAxNzI2MTIwNTc3ODU0.XjSM__sWJC_h16giUBqD3J5inI-NrAVZrYQgNwNI4NAg.1UByncbohJp9h25cugoTPSRCMBsdNKBt4rMkKwV3Xykg.PNG/image.png?type=w800)

Stock-option valuation model selection

​

**● View & Opinion**

**​**

BSM 모델의 투입변수(input)는 옵션가치에 영향을 미치는 변수이다. 아래 변수 중 옵션가치에 가장 민감하게 영향을 미치는 요소는 예상변동성(Expected Volatility)과 예상 기간간격(Expected term)이다. Option은 주가하락 위험을 Protect하므로 상승 가능성인 변동성이 클 수록 가치는 커진다. 또한 이 변동성을 주가에 반영하는 기간간격이 길수록 (ex : 1년 > 6개월) Node별 추정 주가의 폭은 커지므로 옵션가치 역시 그만큼 커지게 된다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">변수(Variable)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">Option Value가 커짐</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  "><div><p style=""><span style="">주식가격(Share parice)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  "><div><p style=""><span style="">높을 수록</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 10.75px;  "><div><p style=""><span style="">행사가격(Exercise Price)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 10.75px;  "><div><p style=""><span style="">낮을 수록</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 10.75px;  "><div><p style=""><span style="">예상 변동성(Expected Volatility)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 10.75px;  "><div><p style=""><span style="">클수록</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 10.75px;  "><div><p style=""><span style="">예상 배당(Expected dividend not receivable)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 10.75px;  "><div><p style=""><span style="">낮을 수록</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 5.38px;  "><div><p style=""><span style="">무위험이자율(Risk-free rate)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 5.38px;  "><div><p style=""><span style="">높을수록</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 5.37px;  "><div><p style=""><span style="">예상 행사기간 간격(Expected term)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 5.37px;  "><div><p style=""><span style="">(일반적으로) 길수록</span></p></div></td></tr></tbody></table>

**KPMG IFRS2 Handbook에서는 다른 모든 조건이 동일하다는 전제 하에 기대변동성(Expected Volatility)과 기대 간격(Expected term)의 변화에 따른 옵션가치를 아래의 표로 예시하고 있다. 이 표가 의미하는 바는 변동성이 클수록, 기대간격이 길수록 옵션가치는 커진다는 것인데, 유의할 점은 기대간격이 2배가 된다고 하여 옵션가격도 2배가 되지는 않는다는 점이다. 아래에서 변동성이 50%인 경우 기대간격이 4년인 경우, 2년인 경우에 비해 옵션가격은 200%가 아닌 142%(44.4 / 31.2) 상승함을 알 수 있다.**

![](https://scs-phinf.pstatic.net/MjAyNDA5MTJfOSAg/MDAxNzI2MTIxOTEwMDky.aAvLgxQeV_e7PjZIVUCIu3WJfEwY0srv_inr256ipREg.TbYVQESP4OgU2Jkx2vuawkhxlPLWwXLCa-ajqZUvHrwg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MTJfNDEg/MDAxNzI2MTIyMDY1ODc4.zhCRIeEIHPAsP-sX9bqKDiztfrW9ey8zeWSq8bahsCwg.SEw7GMuoNIMq9maNQ67FGFriDviFNnQBCe1gvE78-5Qg.PNG/image.png?type=w800)

source ; KPMG IFRS2 Handbook

위 사실은, 옵션가치 측정시 기대간격을 단순히 "평균값(simple average)"을 적용하기 보다는 (가능하다면) 행사기간별로 층화(stratifying)하여 산출하는 것이 더 정확하다는 의미이다. 가령 과거 행사시점의 분포(distribution)을 관찰할 때, 행사가능기간의 시점별로 Grouping 가능하다면 각 행사시점별로 측정하는 것이 단순히 평균값을 적용하는 것보다 정확한 측정이 된다는 의미이다.

​

실무적으로 복잡한 option pricing model의 technical한 로직을 모두 알 필요는 없다. 보통 기술적인 평가와 검증은 가치평가 전문가의 도움을 받는다. 재무담당자와 외부감사 담당 회계사는 Stock-option 계약조항들이 평가모델에 누락없이 녹여져 있는지 여부를 식별할 수 있는 능력을 갖출 필요가 있다. 모델의 단순화로 인한 평가값의 오차가 커지지 않는 범위 내에서 평가방법은 단순화 될 수 있을 것이다.

​

**● Global IFRS Reference**

**​**

![](https://scs-phinf.pstatic.net/MjAyNDA5MTJfMjY1/MDAxNzI2MTI0OTg5Mjk3.FAcQPePeNbx1z3hzOCnaC1kDIsIF4Oj3Bj0cIUrK3wIg.31mKi1ixzwZOtOe5lN6S49wmuu9nw1MdTyOo8Qi3V7cg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MTJfMTk4/MDAxNzI2MTI1MzQ4NDE2.k3r70CZuWTelQHFM1gFWpFI_Je5XPJFXUai8haZA5Lcg.lL_lDDnXgsA0T66WO3_U_bAoC-GdipyZVWDCaFr6e8og.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MTJfOCAg/MDAxNzI2MTI1NDA1Njkx.Jbrg9xb7-X0W-5LZkgYEvQH3kx5rCP0Qc0WvNv0KnJsg.pfuvKbDH3xKHhKQe_UFgjI2FcWsO1u9VSb0a85TuVT8g.PNG/image.png?type=w800)

**​**