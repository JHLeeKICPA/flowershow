---
title: "[IFRS Issue Paper 236] KIFRS1113, DCF 평가시 Stock Option 희석화효과(dillution effect) 반영"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240926170552318ef"
---
![](https://n2.news.naver.com/l.gif?type=content)**236**

**● Stock Option Dilution Effect의 DCF 반영**

​

DCF Valuation시 종업원스톡옵션(ESO)은 EBITDA(Earning Before Interest, Tax, Depreciation, Amortization) 계산 과정에서 손익계산서상 "주식기준보상(expense)"을 현금의 유출이 없는 비용으로 가산(add-back)하고 종결하는 경우가 많은데, 이 방법은 적정하지 않다. 많은 평가자들이 주식기준보상비용을 현금유출이 없는 비용이라는 점에서 상기 방법의 적절함을 주장하지만 이 비용은 기업가치의 증분에 대한 반대급부로 실질적인 원가(real-cost)에 해당한다. 즉, EOS로 인한 기업가치의 증분은 Cash-Inflow로 반영하면서 이에 대한 원가는 Cash-Outflow로 반영하지 않음으로써 주식가치를 과대평가하게 된다.

​

ESO가 행사되면 기존주주 지분을 잠식하므로 총주주지분의 감소로 반영해야 한다. 그렇지 않을 경우 ESO의 성과는 현금흐름에 내재적으로 반영되는 반면 이에 대한 원가(cost)는 반영되지 않는 결과가 됨에 유의해야 한다. 따라서 ESO로 인한 기존주주 지분의 감소는 현금유출(Cash-outflow)로 반영해야 한다.

​

**● 가득된 부분과 미가득된 부분**

**​**

가득된(Vested) ESO에 대해 희석주식수(diluted share)를 적용하거나, 이보다 더 보수적인 방법으로 가득여부와 무관하게 모든 ESO 잠재적 주식수를 분모 발행주식수에 가산하여 총 주식수를 계산하는 방법을 사용하기도 한다. 또는 가득되지 않은 ESO의 희석화효과는 DCF 평가시 무시되는 경우도 있다, 그러나 가장 적절한 방법은 발행주식수를 증가시키는 방법이 아닌, Option Value를 주주지분에서 차감하는 방법을 사용하는 것이다. 이 경우 분모는 발행주식수를 사용한다.

​

**● 사례**

**​**

- **최초 DCF 총 주주지분가치 : 1,000**
- **발행된 Stock option 총 가치 : 100**
- **조정 총 주주지분가치 : 900**
- **현재 발행총주식수 : 90**
- **옵션행사시 증가할 주식수 : 10**
- **완전희석화 주식수 : 100**
- **조정 주당가치 : (1000-100) / 90 = 10 per share**

**​**

**왜 분모에 옵션 수를 포함하지 않는가?**

> 이미 옵션의 희석 가치는 분자에서 금액적으로 반영되었기 때문입니다.
> 
> → 다시 주식 수를 늘리면 희석 효과를 중복 반영하게 됨 (double counting dilution)

**♣ 다모다란(NYU Professor Aswath Damodaran) 접근법**

**​**

**Step 1: 미행사 스톡옵션의 가치 산정**

미행사 스톡옵션의 가치는 Black-Scholes 옵션 가치 평가모형을 사용하여 계산.

예: 행사가격, 잔존 만기, 주가 변동성, 무위험이자율, 배당률 등을 투입하여 옵션 가치를 산정.

​

Step 2: 산정된 옵션 가치만큼 자본가치 차감

위 1단계에서 산정한 옵션 가치를 DCF로 산출된 자본가치에서 차감.

이는 향후 옵션이 행사되면 주식수가 증가하여, 기존 주주가 보유한 지분의 내재가치가 희석되기 때문.

​

📌 중요:

이때, 주당 가치는 조정된 자본가치를 \*\*현재 유통 주식수(보통주 기준)\*\*로 나누어 산출.

옵션을 포함한 fully diluted shares 수로 나누지 않음.

​

실무 적용 예시

DCF로 산정된 자본가치: $1,000M

미행사 스톡옵션의 Black-Scholes 가치: $50M

현재 발행된 보통주 수: 100M주

> 💡 조정된 자본가치 = $1,000M - $50M = $950M
> 
> 💡 주당 가치 = $950M / 100M = $9.50

옵션으로 인한 희석 효과를 별도 가치 차감으로 반영하되, 주식수 희석은 고려하지 않음.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 27.59%; height: 10.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">항목</span></p></div></td><td colspan="1" rowspan="1" style="width: 36.2%; height: 10.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">Damodaran 접근법</span></p></div></td><td colspan="1" rowspan="1" style="width: 36.2%; height: 10.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">전통적 접근법</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 27.59%; height: 10.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">SBC 비용</span></p></div></td><td colspan="1" rowspan="1" style="width: 36.2%; height: 10.0px;  "><div><p style=""><span style="">비용으로 유지</span><span style=""> (add-back X)</span></p></div></td><td colspan="1" rowspan="1" style="width: 36.2%; height: 10.0px;  "><div><p style=""><span style="">비현금성 비용으로 간주 → </span><span style="">add-back</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 27.59%; height: 10.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">주당 가치 계산 방식</span></p></div></td><td colspan="1" rowspan="1" style="width: 36.2%; height: 10.0px;  "><div><p style=""><span style="">미행사 옵션 가치를 자본가치에서 차감</span><span style=""> 후, 유통 주식수로 나눔</span></p></div></td><td colspan="1" rowspan="1" style="width: 36.2%; height: 10.0px;  "><div><p style=""><span style="">Fully diluted shares 기준 주당가치 산출</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 27.59%; height: 10.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">옵션 평가 방법</span></p></div></td><td colspan="1" rowspan="1" style="width: 36.2%; height: 10.0px;  "><div><p style=""><span style="">Black-Scholes 모형 사용</span></p></div></td><td colspan="1" rowspan="1" style="width: 36.2%; height: 10.0px;  "><div><p style=""><span style="">보통 Treasury Stock 방식 또는 단순 주식수 증가 고려</span></p></div></td></tr></tbody></table>

**● View & Opinion**

**​**

기존주주 외 제3자에게 Share option을 발행하면 주가가 행사가격보다 높은 경우(in-the-money) 행사되면 제3자는 그만큼의 이익을 얻게 되는 반면 기존주주는 손해를 입는다. Option Value를 이항모형(Binomial method)으로 평가하는 경우, 평가로직에는 기초자산인 주식의 가격, 변동성과 행사가격이 기간별로 계산되고 확률가중평균값이 현재가치화 되므로 DCF 추정기간 내의 Cashflow에 반영되는 효과가 있다.

​

위 조정을 하기 전 기존주주 지분의 총 가치를 DCF로 산출한 값에는 위 Option Value가 포함되어 있다. 이는 종업원이 열심히 일한 결과가 매출과 이익으로 현금흐름에 녹아있다고 표현할 수도 있다. 이에 대한 원가(cost)의 의미로 위에서 언급한 Option value는 차감해 주는 것이다.

​

종업원 스톡옵션의 근거규정인 IFRS2(KIFRS1102)와 전환사채 전환권 회계처리 근거규정인 IFRS9은 별개이다. 즉, Option pricing model을 사용한다는 점에서 다를 바 없지만 종업원 스톡옵션의 가치평가 방법과 회계처리는 IFRS9의 전환증권에 내재된 내재파생인 Call, Put의 가치평가 및 회계처리와 연관할 필요는 없다.

​

위에서 ESO의 가치를 DCF Value에서 "차감"해 주는 논리는 IFRS9 하의 전환증권 전환권이 "Fixed-for-Fixed"를 불충족하여 부채와 손실로 계상됨으로써 기존주주의 지분을 잠식하는 효과와 일맥상통한다. 이는 Fixed-for-Fixed라는 조건을 불충족 하는 경우에 한하고 충족시에는 자본(Equity)으로 계상된다. 그러나 ESO에서는 이러한 Fixed-for-Fixed 요건을 적용할 필요가 없다.