---
title: "[IFRS Issue Paper 411]KIFRS1109, Backsolve모형에 의한 비상장주식 공정가치 산출①"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250228144141132jn"
---
![](https://n2.news.naver.com/l.gif?type=content)**411**

**● 개요**

**​**

IFRS에 의한 비상장주식 공정가치 평가를 깊이있게 접해 본 분들은 Backsolve mothod에 대해 들어보았을 수가 있다. Backsolve모형은 보통주 가치를 DCF와 같은 방법으로 직접 계산하지 않고 우선주, 전환우선주, 상환우선주 등 우선주 금융상품의 거래가액에서 보통주 가치를 거꾸로 역산해 내는 방법이다.

​

이 방법을 사용하는 경우는 벤처기업, Start-up 기업등 매출이 본격화 되지 않은 기업의 주식가치를 평가할 때, DCF방법들이 유효하지 않기 때문이다. 그러나 이런 기업들은 대부분 전환권이 포함된 우선주로 자금을 조달하므로 우선주 관련 금융상품에 대한 거래가액(Transaction Price) 정보를 보유한다.

​

Backsolve모형의 핵심은 산출하고자 하는 목표값이 보통주 가치는 기업가치를 기초자산으로, 우선주를 행사가격으로 하는 옵션(Option)의 가치라는 점이다. 또 한가지 우선주 거래가액이 곧 공정가액이라고 가정한다는 점이다. Backsolve 모형을 적용하는 과정은 블랙숄즈모형, 이항모형, 몬테카를로 시뮬레이션의 적용이다. 보통주 가격이 옵션이기 때문이다. 이 경우 우선주 가치는 행사가격이 되며 전환권, 상환권이 부여된 우선주는 이항트리에서 노드별로 행사가격이 계속 변동하는 옵션이라 할 수 있다.

​

금번 Issue paper에서는 Backsolve모형의 개념에 대해서 알아보기로 한다.

**● Backsolve Method의 핵심 개념**

**​**

\*\*Backsolve Method (역산법, 역추적법)\*\*을 사용하여 비상장기업의 주식가치를 평가한다는 것은, 해당 기업이 최근에 진행한 우선주 투자(펀딩) 라운드(classe)의 가격을 기반으로 \*\*보통주의 내재 가치(Common Share Value)\*\*를 도출하는 방법을 의미한다.

​

비상장기업은 공모시장이 없기 때문에 시장에서의 주가 형성이 어렵다. 그러나, 스타트업이나 비상장기업은 종종 우선주(Preferred Stock) 투자 유치를 진행하며, 이때 투자자들이 지불한 가격이 존재한다. Backsolve 방법은 이 우선주의 거래 가격을 단서로 삼아, 회사의 전체 가치를 역산하여 보통주 가치를 추정하는 방식이다.

​

(1) 옵션 가격 모델 (OPM, Option Pricing Model) 사용

​

비상장기업은 보통 여러 클래스(Class)의 주식을 보유하고 있다. (예: 시리즈 A, 시리즈 B, 보통주 등). 우선주에는 청산우선권(Liquidation Preference), 전환권(Convertibility) 등의 조항이 붙어 있기 때문에, 우선주의 가격이 보통주의 가치를 직접 반영하지 않는다. 따라서, 옵션 가격 모델(OPM)을 적용하여 우선주가 어떤 시나리오에서 보통주로 변환되는지 분석하고, 이를 기반으로 보통주의 내재가치를 도출한다.

​

1\. Backsolve Method 적용 과정

​

- 우선주의 최근 거래 가격 확인 : 예를 들어, 스타트업이 최근 투자 라운드에서 시리즈 C 우선주를 주당 $10에 발행했다고 가정한다.
- 기업의 전체 가치 추정 : 이 우선주의 가격을 활용하여 기업의 \*\*암묵적인(Implied) 기업가치(Enterprise Value)\*\*를 도출한다.
- 옵션 가격 모델(OPM) 적용 : 기업의 예상 기업가치 범위에서 우선주와 보통주의 지분 가치를 배분합니다. 우선주의 청산우선권 등 계약 조건을 반영하여 보통주의 내재 가치를 역산한다.
- 보통주 주당 가치 산출 : OPM을 통해 계산된 기업의 총 가치를 기반으로 보통주 한 주당 가치를 추정한다.

​

2\. Backsolve Method의 활용 사례

​

- 스타트업 및 유니콘 기업의 공정가치 평가 : 벤처캐피털(VC) 투자 기업이 보유한 스타트업 지분의 공정가치를 평가할 때 때 사용
- 주식보상(Stock-based compensation) 회계처리 : 비상장기업이 직원들에게 부여하는 주식보상의 공정가치를 측정할 때 활용
- IPO(기업공개) 준비 과정 : IPO 전 단계에서 내부적으로 기업의 공정가치를 평가하는 데 사용

​

3\. 한계점 및 유의사항

​

- 우선주 계약 조건에 따라 결과가 달라질 수 있음.
- 청산우선권, 전환권 등 계약 조건이 많을수록 보통주 가치 추정이 복잡해짐.
- 시장의 변동성이 반영되지 않음
- 최근 투자 라운드 가격이 시장의 실제 가치보다 고평가되었거나 저평가되었을 가능성이 있음.
- 기업 내부의 재무 정보 필요
- 옵션 가격 모델을 적용하기 위해 변동성(Volatility), 예상 상장 시기(Timing of Exit) 등의 가정이 필요함.

​

**● Backsolve Method는 거래가액이 공정가액임을 전제로 한다.**

**​**

Backsolve Method를 적용할 때 기본적으로 "거래 가격이 공정가치(Fair Value)와 일치한다"는 전제가 포함된다. 하지만, 이 전제는 현실적으로 완전한 시장에서는 성립할 가능성이 높지만, 비상장기업의 경우 여러 제한 요인이 있어 반드시 참이라고 보기는 어렵다.

​

1\. Backsolve Method에서의 공정가액 전제

​

Backsolve Method는 최근 투자 라운드에서 결정된 우선주(Preferred Stock)의 거래 가격이 해당 시점에서의 기업 가치(Enterprise Value)를 반영하고 있다는 가정하에 보통주의 가치를 역산하는 방식이다. 따라서, 만약 해당 우선주의 가격이 시장에서 합리적인 투자자들 간의 공정한 거래를 통해 결정되었다면, 이 가격을 기반으로 계산된 보통주의 가치는 \*\*공정가치(Fair Value)\*\*로 간주할 수 있다.

​

2\. 하지만 실제로 공정가치와 다를 수 있는 이유

​

비상장기업에서는 다음과 같은 요인 때문에 최근 투자 라운드에서 형성된 거래 가격이 반드시 공정가치를 반영한다고 보기는 어렵다.

​

(1) 시장의 비효율성 (Illiquidity)

​

비상장기업의 주식은 거래소에서 자유롭게 거래되지 않으므로 유동성이 낮다. 투자자 간 협상력, 내부 정보 비대칭 등에 따라 가격이 왜곡될 가능성이 크다.

​

(2) 우선주와 보통주의 계약 구조 차이

​

우선주는 일반적으로 청산우선권(Liquidation Preference), 배당 우선권, 전환권 등의 조항을 포함하고 있으며, 이는 보통주보다 우선주의 가치를 높이는 요소이다. 따라서, 우선주의 거래 가격을 직접 공정가치로 가정하면 보통주의 가치를 과소평가할 위험이 있다.

​

(3) 투자자 간 비대칭 정보 (Information Asymmetry)

​

신규 투자자(VC, PE 등)는 기존 투자자보다 기업 내부 정보를 덜 알고 있을 가능성이 있음. 반대로, 기업 내부자는 투자 유치를 위해 기업 가치를 다소 높이거나 낮추는 전략적 조정을 할 수도 있음.

​

(4) 전략적 투자와 프리미엄

​

투자자들은 단순 재무적 투자자가 아닐 수도 있음. 예를 들어, 전략적 투자자(Strategic Investor)나 기존 투자자가 추가 투자하는 경우, \*\*비재무적 목적(지분 유지, 경영권 보호 등)\*\*으로 인해 거래 가격이 조정될 수 있음.

​

(5) 시장 환경 및 거시 경제 요인

​

투자 유치 시점에서 경제 상황, 업계 트렌드, 금리 변화 등이 기업 가치 평가에 영향을 미칠 수 있음. 예를 들어, 시장이 과열되었을 때(버블) 높은 밸류에이션을 받았다면, 이는 공정가치보다 높은 가격일 가능성이 있음.

​

3\. 그래서 어떻게 신뢰도를 높일 수 있을까?

​

Backsolve Method를 신뢰할 수 있는 방법으로 만들기 위해 다음과 같은 보완 절차가 필요하다.

​

✅ (1) 최근 거래 가격의 신뢰성 평가

​

- 해당 거래가 독립적 투자자(Arm’s Length) 간의 거래인지 확인
- 투자 계약서 및 조건 검토 (우선주 조건이 특별한 혜택을 포함하는지 체크)

​

✅ (2) 여러 밸류에이션 방법과 비교

​

DCF(Discounted Cash Flow), 비교회사법(Comparable Company Analysis, CCA) 등 다른 가치평가 방법과 비교하여 일관성이 있는지 확인.

​

✅ (3) 옵션 가격 모델(OPM) 적용 시 가정 검토

​

기업의 예상 IPO 시점, 변동성(Volatility), 할인율 등을 신중하게 설정.

​

✅ (4) 외부 전문가 검토

​

공정 가치 평가의 객관성을 확보하기 위해 회계사(FASB 409A), 가치평가 전문가(Valuation Specialist) 등의 검토를 받는 것이 일반적이다. 결론적으로 Backsolve Method는 기본적으로 "우선주의 거래 가격이 공정가액을 반영한다"는 전제를 깔고 진행되지만, 비상장기업에서는 이 가정이 항상 성립하지 않을 수 있습니다.

​

**● 사례 1: 스타트업 A사의 기업가치 평가**

​

🔹 배경

​

스타트업 A사는 인공지능(AI) 기반 SaaS 플랫폼을 운영하는 비상장 기업이다. 최근 Series C 투자 라운드에서 벤처캐피털(VC)로부터 시리즈 C 우선주 100만 주를 주당 $15에 발행하여 총 \*\*$1.5억(150M)\*\*을 유치했으며 A사의 기존 발행 주식 구조는 다음과 같다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 34.56%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>주식 유형</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 65.44%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>발행 주식 수</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 34.56%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>보통주(Common Stock)</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 65.44%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">5,000,000</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 34.56%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>시리즈 A 우선주</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 65.44%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">2,000,000</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 34.56%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>시리즈 B 우선주</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 65.44%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">3,000,000</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 34.56%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>시리즈 C 우선주 (신규)</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 65.44%; height: 40.0px;  background-color: #bdfbfa;"><div><p style="line-height:2.0;"><span style="">1,000,000</span></p></div></td></tr></tbody></table>

🔹 Step 1: 시리즈 C의 공정 시장 가치 가정

​

Backsolve Method는 최근 투자 라운드(시리즈 C)의 거래 가격($15)이 해당 시점에서의 기업 공정가치(Fair Value)를 반영한다는 전제에서 출발한다. 하지만, 우선주에는 청산우선권(Liquidation Preference), 우선 배당, 전환권 등 특별한 권리가 있기 때문에, 시리즈 C 가격을 그대로 보통주 가치로 적용할 수는 없다.

​

🔹 Step 2: 옵션 가격 모델(OPM) 적용

​

기업의 전체 가치는 주주 간의 "잔여 가치 배분(Rights Allocation)" 방식으로 산출된다. 주식을 옵션으로 간주하고, \*\*블랙-숄즈 옵션 모델(Black-Scholes Model)\*\*을 활용하여 시리즈 A, B, C 우선주의 기대 가치를 고려한 후, 기업의 전체 가치를 역산한다. 시리즈 C 투자자가 지불한 $15는 시리즈 C 우선주의 가치이므로, 보통주(Common Stock)의 가치는 이를 고려한 조정이 필요하다.

​

🔹 Step 3: 기업가치 도출

​

시리즈 C 우선주 투자 유치 후, A사의 전체 기업 가치는 \*\*$900M (9억 달러)\*\*로 평가되었다. 옵션 가격 모델(OPM)을 적용한 결과, A사의 보통주 가치(Common Share Value)는 $7.50으로 계산되었다.

​

**● 사례 2: 사모펀드(PE) 투자 기업의 가치 평가**

**​**

🔹 배경

사모펀드(Private Equity, PE) 회사 B는 핀테크 기업 C에 투자한 상태이다. 최근 C사는 시리즈 D 투자 라운드에서 우선주를 주당 $20에 발행하여 총 $2억(200M) 투자 유치에 성공했다. 기존 주식 구조는 다음과 같다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 38.97%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>주식 유형</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 61.03%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>발행 주식 수</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 38.97%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>보통주(Common Stock)</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 61.03%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">8,000,000</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 38.97%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>시리즈 A 우선주</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 61.03%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">2,000,000</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 38.97%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>시리즈 B 우선주</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 61.03%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">3,000,000</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 38.97%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>시리즈 C 우선주</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 61.03%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">2,000,000</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 38.97%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>시리즈 D 우선주 (신규)</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 61.03%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">1,500,000</span></p></div></td></tr></tbody></table>

🔹 Step 1: 우선주 계약 검토

​

시리즈 D 우선주는 \*\*2배 청산우선권(2X Liquidation Preference)\*\*이 포함되어 있다. 즉, 회사가 매각되거나 상장될 경우, 시리즈 D 투자자는 다른 주주보다 먼저 2배의 배당금을 받을 수 있다. 따라서, $20의 거래 가격이 곧 보통주의 공정가치를 의미하지 않으며, 이를 반영하여 계산해야 한다.

​

🔹 Step 2: Backsolve Method 적용

​

시리즈 D 투자자의 가격을 기준으로 옵션 가격 모델(OPM) 분석을 수행한다. 분석결과, \*\*C사의 전체 기업 가치는 $1.5B (15억 달러)\*\*로 역산되었다. 조정된 후 보통주의 가치는 주당 $10로 산출되었다.

​

📌 결론 및 시사점

​

Backsolve Method는 최근 투자 라운드의 가격을 활용하여 비상장기업의 보통주 가치를 평가하는 데 유용하다. 하지만, 우선주의 특수한 계약 조항(청산우선권, 배당, 전환권 등)을 반드시 반영해야 하며, 단순히 우선주의 가격을 보통주의 가치로 가정하면 왜곡된 결과가 나올 수 있다. 옵션 가격 모델(OPM)을 적용하여 기업의 실제 가치를 역산하고, 보통주의 적정 가격을 추정하는 것이 핵심이다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMjhfMjEz/MDAxNzQwNzIxNTI1NzM1.7vpdEYLDhapZtO-3-jOs7b34qxgK-HNoYOmRYnfA1Ewg.2y4DOfxzSi_X2nLd29iPGycADeAoNPnOUC9D0Sbz2-sg.PNG/image.png?type=w800)

백솔브모형은 보통주 가치가 기업가치를 기초자산으로, 우선주가치를 행사가격으로 보는 옵션이라는 점이 핵심이다.

**● 좀 더 구체적인 사례분석**

**​**

🔹 계산 과정 요약

​

- 기업 전체 가치 (Total Enterprise Value, TEV) 가정 : 최근 시리즈 D 투자 라운드 가격을 기준으로 기업 가치를 \*\*$1.5B (15억 달러)\*\*로 설정. 우선주의 청산우선권 적용

​

- 시리즈 D 우선주는 $200M (2억 달러) 청산우선권을 가지므로, 보통주는 이 금액 이후의 잔여 가치에 의존. 옵션 가격 모델 (Black-Scholes) 적용

​

- 보통주 가치를 구하기 위해, 기업 전체 가치($1.5B)와 청산우선권($200M)의 차이를 옵션으로 모델링. 보통주 주주는 우선주보다 나중에 배분받는 특성이 있으므로, 이를 유럽형 콜옵션(Call Option)으로 간주.

​

- 무위험 이자율 5%, 변동성 40%, 예상 IPO 시점 3년을 가정.
- 주당 보통주 가치 산출:
- 옵션 가격 모델(Black-Scholes) 적용 결과, 보통주의 총 가치가 $1.328B로 추정됨.
- 발행된 보통주(8M)로 나누어 보통주의 공정 주당 가치 = 약 $166로 계산됨.

​

전환상환우선주(Redeemable Convertible Preferred Stock, RCPS)와 전환우선주(Convertible Preferred Stock, CPS) 같은 복합금융상품이 포함된 경우, Backsolve Method를 적용할 때 추가적인 고려가 필요하다.

이러한 금융상품은 \*\*청산 우선권(Liquidation Preference)\*\*과 \*\*전환 옵션(Convertibility)\*\*을 동시에 가지므로, 옵션 가격 모델(OPM)을 보다 정교하게 적용해야 한다.

​

📌 Step-by-Step 접근 방법

​

복합금융상품이 있는 경우, 기업가치를 평가하는 과정에서 다층적 옵션 모델링이 필요한데 일반적으로 아래의 단계를 따른다.

​

1\. Step 1: 우선주의 계약 조건 분석

​

우선주가 어떤 조건을 가지는지 파악하는 것이 필수적이다. 일반적으로 아래 두 가지 요소를 고려한다.

​

- 청산 우선권 (Liquidation Preference)
- 일정 금액을 먼저 받을 권리. (예: "2배 청산우선권" = 투자금의 2배를 회수 가능)
- 전환권 (Convertibility)
- IPO 또는 M&A 시 보통주로 전환할 수 있는 권리.
- 특정 기업가치 이상이면 보통주로 전환하는 것이 유리함.

**​**

2\. Step 2: 우선주를 ‘옵션’으로 모델링

​

복합금융상품은 콜 옵션(Call Option)과 풋 옵션(Put Option)의 조합으로 해석할 수 있다.

​

전환우선주 (CPS, Convertible Preferred Stock)

​

투자자는 "청산 우선권을 행사할지", "보통주로 전환할지"를 결정할 수 있다. 이는 "맥스(MAX)" 연산을 활용한 옵션으로 모델링 가능한 것이다.

​

예: 전환우선주의 가치=max⁡(청산가치,전환된 보통주 가치)

​

전환상환우선주 (RCPS, Redeemable Convertible Preferred Stock)

​

투자자는 "기업이 상장하지 않으면 일정 기간 후 상환을 요구할 수 있음". 즉, 풋 옵션(Put Option) 성격을 가진다. 따라서, 이 경우 블랙-숄즈 모델과 이항모형(Binomial Model) 등을 혼합하여 평가해야 함.

​

3\. Step 3: 옵션 가격 모델(OPM) 적용

​

이제 복합금융상품을 고려한 Black-Scholes 모델 또는 \*\*이항 옵션 모델(Binomial Model)\*\*을 적용하여 가치 평가를 수행한다. 예를 들면 다음과 같다.

​

가정 조건:

​

- 기업 전체 가치(TEV): $1.5B
- 시리즈 C 전환상환우선주(RCPS): $300M 투자
- 시리즈 B 전환우선주(CPS): $200M 투자
- 보통주(Common Stock): 10M 주 발행
- 예상 IPO 시점: 3년 후
- 기업 변동성(σ): 40%
- 무위험이자율(r): 5%
- 전환비율 (Conversion Ratio): 1:1
- 청산 우선권 (Liquidation Preference): 1.5배

​

우선주의 구조는 다음과 같습니다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>주식 유형</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>발행량</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>투자 금액</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>청산우선권</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>전환권</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>보통주 (CS)</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">10M</span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">NA</span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">NA</span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">NA</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>시리즈 B CPS</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">3M</span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">$200M</span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">1.5x</span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">1:1</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>시리즈 C RCPS</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">5M</span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">$300M</span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">1.5x</span></p></div></td><td colspan="1" rowspan="1" style="width: 20.0%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">1:1 + 상환권</span></p></div></td></tr></tbody></table>

**1️⃣ 우선주가 청산 시 받을 수 있는 금액**

​

- 시리즈 C (RCPS): $300M × 1.5 = $450M
- 시리즈 B (CPS): $200M × 1.5 = $300M

​

💡 즉, 기업가치가 $750M 이하일 경우, 우선주가 보통주로 전환하지 않고 청산 우선권을 행사하는 것이 유리

​

**2️⃣ 우선주가 보통주로 전환할 경우 가정**

​

시리즈 C: 5M 주 × IPO 예상가

시리즈 B: 3M 주 × IPO 예상가

​

💡 즉, 기업가치가 일정 수준 이상 (예: $1.5B 초과)이면, 우선주가 보통주로 전환하는 것이 유리하다.

​

**3️⃣ 옵션 가격 모델 적용 (Black-Scholes & Binomial Model)**

​

우선주가 청산될 확률과 전환될 확률을 계산한다. 전환 우선주(CPS)는 콜 옵션 성격, 전환상환우선주(RCPS)는 풋 옵션 성격을 가진다. 각각의 옵션 가치를 계산하여 보통주 가치를 추정한다. 위의 가정에 따라 Black-Scholes 옵션 모델을 적용하여 보통주의 가치를 계산하면 보통주 가치: 주당 약 $95~$120로 평가된다. 이 값은 기업가치의 변동성(σ), 예상 IPO 시점(T), 청산 우선권 수준에 따라 변동된다.

​

🔹 결론

요약하면, 전환우선주(CPS)와 전환상환우선주(RCPS)는 단순 우선주보다 평가가 복잡하다. Backsolve Method를 적용할 때, 청산 우선권과 전환 옵션을 반영해야 한다. 그리고 우선주의 청산과 전환을 비교하여 가장 유리한 전략을 선택하는 옵션 모델(OPM)을 활용해야 한다. 즉, 복합금융상품이 포함된 경우, 옵션 가격 모델을 혼합 적용하여 가치 평가를 수행하는 것이 필수적이다.

​

**● Backsolve method는 노드별 행사가격이 변동하는 옵션의 특징을 가진다.**

**​**

우선주의 두 가지 선택지

(1) 청산 우선권 행사 (정해진 비율로 투자금 회수)

(2) 보통주로 전환 (기업가치가 충분히 높을 때 유리)

​

각 시점(노드)에서 더 유리한 전략을 선택한다. 즉,

- 기업가치(Exit Value)가 낮다면 청산 우선권이 유리 → 옵션 행사 X
- 기업가치(Exit Value)가 높다면 보통주 전환이 유리 → 옵션 행사 O

​

결과적으로, "우선주의 행사 가격(Strike Price)"가 기업가치에 따라 변동되는 구조로 행사가격이 고정된 일반적인 옵션과 다르다. 즉, 노드(미래 시점)마다 행사 조건이 달라지므로 이항모형(Binomial Model) 또는 몬테카를로 시뮬레이션을 활용해야 함

​

**● 노드별 변동 행사가격을 적용한 전환상환우선주(RCPS) 평가**

**​**

1\. Step 1: 기업가치와 우선주의 구조

​

현재 기업가치(TEV): $1.5B

​

시리즈 C 우선주(RCPS)

- 투자금액: $300M
- 1.5배 청산우선권: 기업이 매각(Exit) 시 최소 $450M 보장
- 보통주로 전환 가능 (전환비율 1:1)

​

시리즈 B 우선주(CPS):

- 투자금액: $200M
- 1.5배 청산우선권: 최소 $300M 보장
- 보통주로 전환 가능 (전환비율 1:1)
- 보통주 발행량: 10M 주
- 변동성(σ): 40%
- 무위험 이자율(r): 5%
- 예상 IPO 시점: 3년 후

​

2\. Step 2: 노드별 변동 행사가격 모델링

​

각 시점에서 투자자가 선택할 수 있는 전략을 고려하여 이항 트리(Binomial Tree)를 구성한다.

​

① Exit 기업가치(매각/IPO 시점)가 낮을 경우 (예: $1B)

​

- 시리즈 C, B 우선주는 청산 우선권 행사가 유리
- 시리즈 C는 $450M 수령 (투자금 $300M × 1.5배)
- 시리즈 B는 $300M 수령 (투자금 $200M × 1.5배)
- 남은 금액이 거의 없으므로 보통주는 가치가 거의 없음

​

✅ 이 경우, 시리즈 C와 B 우선주의 "행사가격"은 각각 $450M, $300M이다.

​

② Exit 기업가치가 중간 수준 (예: $1.5B)

​

시리즈 C, B 우선주는 보통주 전환 vs 청산우선권 중 선택해야 한다.

- 보통주 주당 가치 = $1.5B ÷ (보통주 + 전환된 우선주)
- 총 발행 주식 = 10M(보통주) + 3M(시리즈 B) + 5M(시리즈 C) = 18M
- 주당 가치 = $1.5B ÷ 18M = 약 $83

​

✅ 이 경우, 시리즈 C의 행사가격은 $450M vs 보통주 5M × $83 → $415M → 청산 우선권 행사

✅ 이 경우, 시리즈 B의 행사가격은 $300M vs 보통주 3M × $83 → $249M → 청산 우선권 행사

​

​

③ Exit 기업가치가 높을 경우 (예: $3B)

​

보통주 가치가 높아지면 우선주도 보통주로 전환하는 것이 유리

보통주 주당 가치 = $3B ÷ 18M = $167

​

전환 시:

- 시리즈 C = $167 × 5M = $835M
- 시리즈 B = $167 × 3M = $501M

​

청산 시:

시리즈 C = $450M

시리즈 B = $300M

​

✅ 이 경우, 시리즈 C, B 모두 보통주로 전환이 유리

✅ 즉, "행사가격"이 청산우선권 기준이 아니라 보통주 가치 기준으로 변동됨!

​

​

Step 3: 최종 옵션 가격 모델 적용

​

이제 이항모형(Binomial Model)을 적용, 각 노드별 최적 전략을 선택하는 방식으로 우선주의 가치를 평가한다.

​

- 각 노드에서 기업가치 변동을 시뮬레이션 (이항 트리 확률 계산)
- 각 노드에서 우선주가 "청산" vs "전환" 중 더 높은 가치를 선택
- 기대값을 계산하여 우선주의 현재 가치를 도출
- 이를 기반으로 보통주 가치를 계산

​

📌 결론

​

✅ 전환우선주(CPS)와 전환상환우선주(RCPS)는 옵션처럼 행동하지만, 행사가격이 노드별로 동적 변화함.

✅ 즉, "행사가격이 변동하는 옵션"으로 해석해야 하며, 일반적인 Black-Scholes 모델이 아닌 "이항모형(Binomial Model) 또는 몬테카를로 시뮬레이션"을 사용해야 보다 정확한 평가가 가능함.

✅ 각 노드에서 기업가치 변화에 따라 우선주가 보통주로 전환할지, 청산 우선권을 행사할지를 선택하는 "동적 최적화 모델"을 적용해야 함.

​

​

● View & Opinion

​

📌 IFRS와 Backsolve Method의 차이 및 상충 가능성

​

📌 IFRS에서 거래가액과 공정가액의 차이

​

IFRS에서는 \*\*거래가액(Transaction Price)\*\*과 \*\*공정가액(Fair Value, FV)\*\*을 구분하며, 특히 Level 3 입력값(Level 3 Inputs, 관측 불가능한 내부 가정)을 사용하여 평가한 경우, \*\*차액을 이연하여 상각(Deferred Recognition & Amortization)\*\*하도록 규정하고 있다.

​

🔹 IFRS 공정가치 평가 계층(Level 1 ~ 3)

​

Level 1: 활발한 시장에서 형성된 가격 (예: 상장 주식)

Level 2: 유사한 자산의 시장 데이터를 기반으로 한 평가 (예: 비상장채권의 시장금리 기반 평가)

Level 3: 관측할 수 없는 내부 정보(기업 예측, 모델링 등)를 사용하여 평가 (예: 스타트업 가치평가, 내부 할인율 적용)

​

즉, IFRS에서는 비상장 기업의 가치평가가 Level 3에 해당하는 경우, 거래가액과 공정가액이 다를 수 있다고 보고 차액을 이연하여 상각해야 한다.

​

📌 Backsolve Method의 가정과 IFRS와의 차이

​

Backsolve 모형의 핵심 가정은 \*\*"거래된 우선주의 가격이 공정가치(Fair Value)를 반영한다"\*\*는 것이다. 하지만 이는 IFRS와 몇 가지 주요 차이점을 가진다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 26.14%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>기준</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 35.9%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>IFRS</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 37.96%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>Backsolve Method</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 26.14%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>거래가액 vs 공정가액</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 35.9%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">거래가액과 공정가액이 다를 수 있음 (Level 3 평가 반영)</span></p></div></td><td colspan="1" rowspan="1" style="width: 37.96%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">거래가액이 공정가액과 동일하다고 가정</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 26.14%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>공정가치 평가 방법</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 35.9%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">관측 불가능한 데이터(Level 3) 반영 필요</span></p></div></td><td colspan="1" rowspan="1" style="width: 37.96%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">최근 투자 라운드 가격을 기준으로 역산</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 26.14%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.0;"><span style="color:#ffffff;"><b>이연 및 상각</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 35.9%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">Level 3 공정가액이 다르면 차액을 이연하여 상각</span></p></div></td><td colspan="1" rowspan="1" style="width: 37.96%; height: 40.0px;  "><div><p style="line-height:2.0;"><span style="">별도의 이연 없이 즉시 반영</span></p></div></td></tr></tbody></table>

즉, IFRS에서는 거래가액이 공정가치를 완전히 반영하지 않을 가능성을 고려하지만, Backsolve Method는 최근 거래된 우선주의 가격이 시장에서 결정된 공정가치라고 가정하는 차이가 있다.

​

📌 IFRS 규정과 Backsolve Method의 잠재적 상충 문제

​

거래가액이 시장 가격을 반영하지 않는 경우

​

IFRS에서는 거래가액이 시장 왜곡(예: 내부 투자자 주도 가격 조정 등)으로 인해 공정가액과 다를 가능성을 고려한다. 반면, Backsolve Method는 해당 거래 가격이 곧 공정가액이라는 가정하에 보통주 가치를 역산하므로, IFRS의 Level 3 평가 기준과 상충될 수 있다.

​

우선주의 특수 조건 (옵션, 청산우선권 등)이 반영되지 않은 경우 IFRS에서는 복합금융상품(예: 전환상환우선주, 전환우선주 등)의 경우 별도로 공정가치를 평가해야 한다고 요구한다. Backsolve Method는 우선주의 계약 조건을 완벽하게 반영하지 않는 한, 공정가치 평가의 신뢰성이 떨어질 수 있다.

​

이연 상각(Deferred Recognition & Amortization) 필요성

​

IFRS에서는 공정가치와 거래가액 간 차이를 즉시 인식하지 않고, 일정 기간 동안 이연하여 상각해야 할 수 있다.

Backsolve Method는 거래된 가격을 즉시 공정가치로 간주하여 차액을 조정하지 않기 때문에, IFRS 회계처리와 직접적으로 충돌할 수 있다.

​

📌 IFRS 기준을 준수하면서 Backsolve Method를 적용하려면?

​

백솔브 모형을 IFRS 회계 기준에 맞게 활용하려면 다음과 같은 보완이 필요하다.

​

✅ 1. Backsolve Method 적용 시 Level 3 검토 수행

IFRS 규정을 준수하려면, Backsolve Method를 사용할 때 거래 가격이 공정가치를 반영하는지 Level 3 평가 기준을 적용하여 검토해야 한다. 이를 위해 시장 조건, 계약 조건, 할인율 등을 조정하여 보정된 공정가치를 산출해야 한다.

​

✅ 2. 이연 상각(Deferred Recognition) 적용

IFRS에서는 거래가액과 공정가액 간 차이를 즉시 인식하지 않고, 일정 기간 동안 이연하여 상각해야 할 수 있다.

따라서, Backsolve Method로 평가한 보통주 가치와 IFRS 기준의 공정가치 간 차이가 존재하면, 이를 회계적으로 조정할 필요가 있다.

​

✅ 3. 비교 가치평가 방법과 함께 사용

​

IFRS에서는 DCF(Discounted Cash Flow), Comparable Company Analysis(비교기업평가), 옵션가격모델(OPM) 등과 함께 검토하여 거래 가격이 공정가치를 반영하는지 확인하는 것이 일반적이다. 즉, Backsolve Method를 단독으로 사용하기보다는, 다른 평가방법과 교차 검증하여 IFRS 적합성을 확보하는 것이 중요하다.

​

​

📌 결론

​

❌ Backsolve Method는 기본적으로 IFRS와 완전히 일치하지 않는다.

​

거래 가격이 공정가액과 동일하다는 가정을 하므로, IFRS의 Level 3 평가 기준과 다를 가능성이 있다.

IFRS에서는 거래 가격이 공정가치를 반영하지 않는 경우 차액을 이연하여 상각해야 하지만, Backsolve Method는 즉시 공정가치로 사용한다.

​

✅ IFRS를 준수하려면 보완이 필요하다.

​

- 거래 가격이 Level 3 기준에서 적정한지 추가 분석이 필요하다.
- DCF, 비교기업평가 등 다른 가치평가 방법과 함께 사용하여 검증해야 한다.
- 공정가치와 거래가액 차이를 이연하여 회계적으로 반영하는 조정이 필요하다.
- 즉, IFRS에서 요구하는 공정가치 평가 방법을 고려하지 않고 Backsolve Method를 그대로 적용하면 회계 규정과 충돌할 가능성이 있으므로, 추가적인 회계적 보완이 필요하다.