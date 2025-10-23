---
title: "[IFRS Issue Paper 412]KIFRS1109, Backsolve모형에 의한 비상장주식 공정가치 산출②"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250228162743131cl"
---
![](https://n2.news.naver.com/l.gif?type=content)**● 서론 (Introduction)**

​

비상장 기업(Privately Held Company)의 경우, 시장 데이터를 확보하는 것이 제한적이기 때문에 기업 가치 평가(Valuation)가 더욱 복잡해진다. 투자 전략이 발전하면서, 투자자들은 단순한 대략적 추정(Broad Approximations)이 아니라 정확하고 세밀한 평가(Precision & Accuracy)를 요구하게 되었다.

​

\[IFRS Issue Paper 406\]KIFRS1109, Backsolve모형에 의한 비상장주식 공정가치 산출①에서도 설명한 바와 같이 보통주 가치는 우선주가차를 행사가격으로 하는 Call Option이라는 사실이 Back solve모형의 핵심이다.

​

"아래 그림에서, 짙은색 영역은 우선주(preferred), 옅은색 영역은 보통주(common) 가치를 나타낸다. 여기서 Break Point는 2군데 존재한다. Break Point는 우선주주와 보통주주간의 순자산 배분기준이 달라지는 지점을 의미한다. 기업이 특정시점(ex : 청산)에 우선주에게 지급해야 할 절대금액까지 보통주는 지분이 없다. 이 구간은 맨 아래 짙은 색 영역이다. 그 지점 이후부터는 보통주에게 돌아가는 몫이된다면 보통주는 우선주에게 우선 지급한 절대금액을 초과하는 순자산에 대해 몫을 가질 것이며 이 부분은 가운데 옅은 영역이 된다. 그리고 난 다음 구간에서는 보통주와 우선주가 일정비율로 나누어가지는 경우를 형상화 한 것이다."

![](https://scs-phinf.pstatic.net/MjAyNTAyMjhfNDcg/MDAxNzQwNzI2OTUzMzcy.xlObJ6ImPiyrKIa5XPJT7YCVrVEXQyamJw0jcnaFc1Qg.L5mAA7RYtuqlNEwi3rOJbbnRi3iPS9aHuJBYvibsQ10g.PNG/image.png?type=w800)

보통주는 우선주가치를 행사가격으로 하는 옵션가치이다.

위에서 옅은 색 삼각형은 보통주 가치를 나타내는 영역으로 우선주 가치를 행사가격으로 하는 Call Option인데, Breakpoint 2에서는 다시 우선주 몫이 발생하므로 Call Option 전체가치가 되지 못하고 우선주 몫은 차감되어야 하는데 이 차감되는 우선주 몫 역시 Call Option의 형태로 표시되어 있음에 주목한다.

**1\. AICPA(미국 공인회계사 협회)의 가이드라인**

​

역산(Backsolve) 방법은 기업의 각 주식 등급의 권리와 우선순위를 고려하여, 최근 주식 거래 가격과 일치하는 총 주식 가치(Total Equity Value)를 계산하는 방법이다. **최근 거래가 신뢰할 수 있는(reliable) 경우, 역산 방법은 기업 가치 평가에서 가장 신뢰할 수 있는 방식이다.** 만약 거래가 \*\*독립적인 조건(Arm’s Length)\*\*에서 이루어지지 않았거나, 평가일(Valuation Date)과 시점이 다를 경우, 적절한 조정(Adjustments)이 필요하다.

​

1\. Stage 1 기업의 정의

​

AICPA 가이드에 따르면 Stage 1 기업이란 제품 매출(Product Revenue)이 없거나 매우 적거나, 비용내역(Expense History)이 거의 없는 경우, 신뢰할 수 있는 현금 흐름 예측(Cash Flow Forecasting)이 불가능힌 경우로 수익 접근법(Income Approach)을 활용한 평가가 어려운 경우이다. 이 때 역산 방법(Backsolve Method)\*\*이 보다 신뢰할 수 있는 평가 방식으로 활용된다.

​

2\. 역산 방법의 기본 응용 (Basic Application of Backsolve Method)

​

**(1) 기본 개념**

​

역산 방법은 특정 주식 등급의 최근 거래 가격을 기반으로, 블랙-숄즈-머튼(Black-Scholes-Merton) 옵션 가격 모델과 기업의 자본 구조(Capital Structure) 정보를 활용하여 주식의 공정 가치(Fair Value, FV)를 추정하는 방식이다.

​

**(2) 옵션 가격 모델이란?**

​

옵션 가격 모델(Option Pricing Model)은 주식을 매수(Call Option) 또는 매도(Put Option)할 수 있는 옵션의 이론적 가치를 평가하는 수학적 모델이다. 옵션은 보유자에게 주식을 일정 가격(행사가격, Strike Price)으로 특정 기간 동안 매수할 권리(콜 옵션)\*\*를 부여한다. 옵션 가격 모델은 변동성(Volatility), 금리(Interest Rate), 만기(Term to Expiration) 등 다양한 요소를 고려하여 이론적인 가치(Theoretical Value)를 산출한다.

**​**

**(3) 블랙-숄즈 옵션 가격 모델 (Black-Scholes Model)**

​

블랙-숄즈 모델(Black-Scholes Model)은 옵션 거래가 활성화되던 시기에 옵션의 공정 가치를 평가할 수 있는 공식(Formula)을 제공한 획기적인 모델이다.

​

1) 블랙-숄즈 모델의 주요 가정

​

- 기하 브라운 운동(Geometric Brownian Motion) : 주가(Stock Price)는 \*\*정규 분포를 따르는 랜덤 워크(Random Walk)\*\*를 기반으로 움직인다고 가정한다. 이는 \*\*주가의 변동성(Volatility)\*\*을 모델링하는 데 중요한 요소이다.
- 차익거래 없음(No Arbitrage Opportunity) : 옵션과 기초 자산(Underlying Asset) 간 무위험 차익거래(Risk-Free Arbitrage)가 발생하지 않는다.
- 연속적 거래(Continuous Trading) : 유럽형 옵션(European-Style Options)만을 가정하며, 옵션은 만기 시점에서만 행사 가능하다.
- 고정된 변동성(Constant Volatility) : 옵션 기간 동안 변동성(Volatility)이 일정하게 유지된다고 가정한다.
- 무위험 이자율(Risk-Free Rate) : 무위험 금리(Risk-Free Interest Rate)는 고정된 값으로 알려져 있다.

​

2) 블랙-숄즈 공식에 필요한 입력값

​

- 기초 주식 가격(Current Stock Price)
- 옵션 행사가격(Option Strike Price)
- 옵션의 예상 만기(Expected Term to Expiration)
- 주가 변동성(Expected Volatility)
- 무위험 금리(Risk-Free Rate)

​

3) 역산 방법에서 고려해야 할 변수

​

역산 방법을 적용할 때, \*\*두 가지 주요 미지수(Unknowns)\*\*가 존재한다.

​

- 현재 주식 가격(Current Share Price) (이는 우리가 구하려는 값이다)
- 옵션의 행사가격(Option’s Strike Price)

​

또한 예상 만기(Expected Term)와 변동성(Volatility)도 불확실하다.

​

4) 예상 만기 및 변동성 추정

​

미국 기업의 IPO(기업공개)까지의 평균 기간(5~10년)을 고려하여 예상 만기를 설정할 수 있다. 변동성(Volatility)\*\*은 유사한 상장기업(Peer Group)의 변동성을 참고하여 추정하는 것이 일반적이다.

​

**(4) 배당 및 분배 구조가 평가에 미치는 영향**

​

역산 방법에서는 배당금 지급 및 분배 우선순위가 콜 옵션의 행사 가격(Exercise Price)으로 해석될 수 있다.

​

예제: 우선주와 보통주 간 배분 구조

​

- 20X3년 12월 31일, 한 기업이 우선주(Preferred Shares)를 $1,000,000에 발행
- 우선주 보유자는 기업이 매각되거나 배당을 지급할 경우,
- 최초 투자금 $1,000,000과 20%의 추가 배당($200,000)\*\*을 우선적으로 받음
- 이후 보통주(Common Stock) 보유자가 배당을 받을 수 있음

​

**⇒ 보통주의 가치는 결국 "콜 옵션"의 가치와 동일**

​

즉, 보통주 투자자는 우선주 투자자가 $1,200,000을 먼저 받기 전까지는 배당을 받을 수 없다. **일반 주주가 보유한 지분은 총 행사가격이 $1,200,000 또는 $1,000,000 + $200,000인 회사 주식에 대한 콜 옵션으로 비유할 수 있는 것이다.** 이는 일반 주주가 자신들의 지분에서 혜택을 받을 수 있는 경우에만 가능하기 때문이다.

​

위 공식은 우선주 주주에게 $1,200,000을 배당한 후, 모든 추가 배당금이 일반 주주에게 귀속된다고 가정하는 것이다.

​

위 예제에서 볼 수 있듯이, 회사의 특정한 자본 구조와 배당권을 이용하면 공정가치(FV) 평가 전문가가 공정가치 평가와 주식 옵션을 포함하는 방정식을 도출할 수 있는 것이다. 본질적으로, 블랙-숄즈(Black-Scholes) 공식도 이러한 두 변수를 포함하는 방정식이다. 즉, 두 개의 미지수(주식의 공정가치와 옵션의 공정가치)를 포함하는 두 개의 방정식을 풀어 미지수의 값을 결정할 수 있는 것이다.

​

이러한 미지수를 결정하는 방법은 "시행착오(trial and error)" 접근 방식으로, 전문가가 여러 가지 주식 가치(또는 옵션 가치)를 고려하여 두 방정식이 적절하게 해결되도록 하는 것이다. 배당금 또는 기타 분배 한도가 변경되면서 분배 권리가 달라지는 기준점을 "브레이크포인트(breakpoints)"라고 하는 것이다. 즉, 브레이크포인트는 옵션의 행사 가격을 결정하는 역할을 하는 것이다.

​

전반적으로 백솔브(Backsolve) 방법을 적용하는 절차는 다음과 같다.

​

Step 1 - 최근 주식 거래의 가격 조건을 확인하는 것이다.

Step 2 - 관련 배당/분배 권리 및 관련 "브레이크포인트"를 확인하는 것이다.

Step 3 - 공정가치(FV) 방정식을 작성하는 것이다.

Step 4 - 옵션 가격 모델에 필요한 입력값(무위험 이자율, 예상 기간, 변동성 등)을 추정하는 것이다.

Step 5 - "시행착오(trial and error)" 접근 방식을 사용하여 공정가치(FV)를 계산하는 것이다.

​

위 접근 방식을 예제와 함께 설명할 것이다. (예제: 두 개의 주식 클래스)

​

**(5) 백솔브(Backsolve) 방법 - 고급 응용**

​

위 섹션에서 고려한 예제는 두 개의 주식 클래스와 이에 해당하는 두 개의 브레이크포인트를 다루는 것이다. 여기서 중요한 질문은 동일한 방법 또는 수정된 접근법이 세 개 이상의 주식 클래스에도 적용될 수 있는지 여부이다. 이를 위해서는 주식의 공정가치(FV) 방정식을 수정해야 하는 것이다.

N개의 주식 클래스를 고려할 경우, 공정가치(FV) 방정식은 다음과 같이 표현될 것이다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMjhfMzEg/MDAxNzQwNzI0ODIxNjk0.zHNTKsDfQWsxqJKTjTcFyZprLIBxNKWJYVYVQfDNsWAg.R1vIb672VwrXiweLVh6cDZ9zHsHGAbGCJITtOlCnWFwg.PNG/image.png?type=w800)

**​**

**● 백솔브(Backsolve) 방법 - 고급 응용**

​

단순한 백솔브 방법의 적용에서는 한 개의 주식 클래스의 공정가치(FV)가 알려져 있으며, 다른 주식 클래스의 공정가치는 블랙-숄즈(Black-Scholes) 공식과 특정한 배당 분배 우선순위를 반영한 주식 FV 방정식의 조합을 사용하여 결정하는 것이다.

​

이 접근 방식에서는 미지의 **주식 지분 공정가치를 해당 주식 지분에 대한 콜 옵션의 공정가치로 비유**하는 것이다. 동일한 접근 방식은 두 개 이상의 주식 클래스를 가진 회사의 공정가치를 추정하는 경우에도 적용될 수 있다.

​

세 개의 주식 클래스를 포함하는 예제에서 주식 FV 방정식은 각 클래스의 FV를 합산하는 방식이다. 이러한 합산 결과, 최종 주식 FV 방정식에서는 일반주(보통주)의 추정 FV가 제거되는 것이다. 또한, 방정식에는 Series B 주식에 귀속되는 10%의 잔여 지분도 포함되지 않는 것이다.

​

예제에서 최종 주식 FV 방정식은 다음과 같다.

​

***Equity FV at 12/31/20X3***

***​***

***\=1,000,000***

***\+ FV of Call Option on Series B Stock at break 1***

***−10%×Call Option on Series A Stock at break 3***

​

여기서 10%는 브레이크포인트 3 이후 회사 분배에서 Series A가 차지하는 비율을 의미하는 것이다. 유사한 배당 우선권을 가진 다른 주식 클래스가 존재할 경우, 주식 공정가치를 추정하는 방정식은 위와 동일한 일반적인 구성 요소를 포함할 것이다. 즉, N개의 주식 클래스를 포함하는 경우, 공정가치는 다음 요소들을 포함하는 것이다.

​

(e) Series A 주식의 알려진 달러 가치

(f) 브레이크포인트 1에서의 Series B 주식 콜 옵션의 FV

(g) 브레이크포인트 N 이후 배당에서 Series A가 차지하는 비율

(h) 브레이크포인트 N에서의 Series A 주식 콜 옵션의 FV

​

Series A 및 Series B 외의 기타 우선주 및 보통주(즉, 다른 모든 주식 클래스)의 FV는 최종 방정식에서 제거되는 것이다.

​

N개의 주식 클래스를 고려한 일반적인 주식 FV 방정식

​

Estimated Equity FV =

Estimated FV of Series A

\+ FV of Call Option on Series B Stock at break 1

– Series A Share in Distributions After Break N x Call Option on Series A Stock a

​

**● 두 개의 주식 클래스 - 예제**

​

1\. 사례 개요 (Fact Pattern)

​

회사 A는 20X3년 12월 31일 경 투자자들에게 Series A 우선주(Preferred Shares)를 발행하여 1,000,000을 조달헸고\*\*우선주 외에도, 보통주(Common Shares)\*\*가 존재하며, 이는 20X3년 12월 31일 이전에 이미 발행 및 유통 중인 것이다.

​

Series A 우선주의 배당(분배) 우선순위

​

유동성 이벤트 발생 시 (IPO, 기업 매각, 배당 지급 등), Series A 우선주 주주들은 먼저 다음 금액을 수령하는 것이다.

​

기본 투자금: $1,000,000

추가 배당금: $200,000

총합: $1,200,000

​

Series A 주주들이 $1.2M을 받은 후, 추가적인 분배금이 있다면, 이는 보통주 주주들에게 지급되며 최대$1.2M을 초과할 수 없다 이후 추가적인 분배금이 발생하는 경우, 보통주와 우선주는 다음 비율로 분배하는 것이다.

​

우선주(Series A) 주주: 10%

보통주 주주: 90%

​

2\. 분석 (Analysis)

​

회사의 공정가치(Fair Value) 평가 목표는 20X3년 12월 31일경의 총 주식 공정가치(FV)를 추정하는 것이다.

이러한 평가를 위해 다음 단계를 고려하는 것이다.

​

**(1) 주식 FV 방정식 설정**

​

**주식의 공정가치는 각 주식 클래스의 FV를 합산한 값이어야 하는 것이다. S**eries A 주주들은 우선적으로 $1.2M을 수령하므로, 첫 번째 브레이크포인트(Breakpoint 1)는 $1,200,000이다. 보통주 주주들은 그 이후 최대 $1.2M을 수령할 수 있으므로, 두 번째 브레이크포인트(Breakpoint 2)는 $2,400,000이다.

이후 추가적인 분배는 10%(우선주) 대 90%(보통주) 비율로 이루어지는 것이다.

​

**(2) Black-Scholes 옵션 모델을 활용하여 보통주 및 우선주의 옵션 가치 평가**

​

보통주는 브레이크포인트 1 이후부터 실질적인 가치가 발생하므로, 보통주의 FV는 콜 옵션의 가치로 표현될 수 있는 것이다. 마찬가지로, Series A 우선주의 일부 FV도 콜 옵션 형태로 모델링될 수 있는 것이다.

​

**(3) "시행착오(trial and error)" 접근 방식 적용**

​

공정가치를 추정하는 방정식을 수립하고, 여러 FV 가정을 적용하여 결과가 수렴하도록 조정하는 것이다.

​

**(4) 결과 도출**

​

위 분석을 기반으로, 회사의 주식 공정가치는 두 개의 주식 클래스 및 해당 옵션 가치를 반영하는 방정식을 통해 도출되는 것이다.

​

위의 과정을 반복하여, 최적의 주식 공정가치(FV)를 도출하면 다음과 같은 값이 나온다.

​

주식 공정가치(FV) = $5,022,875

브레이크포인트 1에서 보통주의 콜 옵션 FV = $4,430,673

브레이크포인트 2에서 우선주의 콜 옵션 FV = $4,077,981

​

이 값들은 \*\*Black-Scholes 계산을 통해 도출된 값(Schedule 1 - Black-Scholes Calculations 참고)\*\*이며,

주식 FV 방정식과 일치하도록 시행착오(trial and error) 방식을 통해 결정되는 것이다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>input</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>Break Point 1</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>Break Point 2</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>Equity Value</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 43.0px;  "><div><p style=""><span style="">5,022,875</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 43.0px;  "><div><p style=""><span style="">5,022,875</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>Exercise Price</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">1,200,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">2,400,000</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>Term-years</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">6</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">6</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>Volatility</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">80%</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">80%</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 5.38px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>Divedend Rate</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 5.38px;  "><div><p style=""><span style="">0%</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 5.38px;  "><div><p style=""><span style="">0%</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 2.69px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>Risk-Free Rate</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 2.69px;  "><div><p style=""><span style="">4%</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 2.69px;  "><div><p style=""><span style="">4%</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 2.68px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>Call Option-FV</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 2.68px;  "><div><p style=""><span style="">4,430,673</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 2.68px;  "><div><p style=""><span style="">4,077,981</span></p></div></td></tr></tbody></table>

Equity FV at 12/31/20X3 = FV of Series A + FV of Call Option on Common at break 1 - 10% of Call Option on Common at break 2

​

\= $ 5,022,875 = $ 1,000,000 + $ 4,430,673 - 0.1 \* 4,077,981

​

Overall, estimated FV of equity at 12/31/20X3 is $ 5,022,875.