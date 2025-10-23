---
title: "[IFRS Issue Paper 201] KIFRS1113, KIFRS1109, Back-Solve method를 이용한 주식의 공정가치 추정 방법"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240821152825792gq"
---
![](https://n2.news.naver.com/l.gif?type=content)**● Back-Solve method의 기본 컨셉**

​

Back-Solve method의 기본컨셉은 지분의 공정가치를 추정하기 위해서 최근의 다른 지분 발행거래의 거래가액(transaction price), Black-Scholes option pricing model, 그리고 자본구조에서 이끌어 낼 수 있는 다른 정보들을 이용하는 것을 의미한다. Back-Solve method는 다음의 단계를 통해 수행된다.

​

- Step 1 - 최근 유상증자 거래의 가격결정 조건의 식별
- Step 2 - 주주별 배당(분배) 권리와 관련한 분깃점("breakpoint")의 식별
- Step 3 - 지분 공정가치 방정식의 결정
- Step 4 - Option pricing model의 적용을 위한 입력변수(무위험이자율, 예상기간, 변동성)의 추정
- Step 5 - 시행착오법("trial and error approach")을 사용하여 지분의 공정가치 추정치를 계산

​

위 Step3에서 FV 방정식은 지분의 공정가치와 Call Option의 공정가치라는 두가지 미지수를 포함한다. 정형화된 Black-Scholes equation 또한 위 두 변수와 다른 3가지 변수(무위험이자율, 기대변동성, 옵션기간)를 포함한다. 3가지 다른 변수는 경영자의 추정과 시장정보에서 이끌어 낼 것이다.

​

Black-Scholes 방정식과 2가지 미지수(지분의 공정가치와 Call option의 공정가치)를 가진 지분 방정식(equity-equation)은 주식과 call option의 공정가치가 미지수를 결정하기 위해 사용된다. 미지수를 찾아내기 위해 일반적으로 사용되는 방법은 시행착오법("trial and error approach")이다.

​

만약 A사가 Series A(preferred stock)와 보통주(common stock) 2가지 종류의 자금조달 원천을 가지고 있는 경우 지분 방정식(equity formula)는 다음과 같다.

![](https://scs-phinf.pstatic.net/MjAyNDA4MjBfMTE5/MDAxNzI0MTQyMzUxNTM4.Zs5gv5LCtBYVHIwvoLeb7SPNgdTVczDlx2lTQdIu1cQg.6y9J4XtFfNUcxnq_L6NkdkICA5VdrdGWGzRSJnmBkYog.PNG/image.png?type=w800)

equity formula

모든 자본구조 하에서 Back-solve method의 적용이 가능한 일반화된 공식으로 표현하면 아래와 같다.

![](https://scs-phinf.pstatic.net/MjAyNDA4MjBfMjA4/MDAxNzI0MTQyNTkyMTcw.44gSKB5Jy538aDwpbvG90_88dPs2ogt0iRdHpo4YG4cg.bSLoY1ONVllWY1MXvawOgr2UK9pWKXnocCgajWNxuzcg.PNG/image.png?type=w800)

​

**● 사례**

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 129.0px;  background-color: #bdfbfa;"><div><ul><li><p style="line-height:1.9;"><span style="">A사는 2024.12.31 즈음 Series A 우선주를 투자자에게 1,000,000에 발행하였다. 우선주 외에 2024년 12.31. 이전에 발행된 보통주가 존재한다.</span></p></li><li><p style="line-height:1.9;"><span style="">Series A 투자자는 청산(Liquidity ; IPO, 회사의 매각, 배당)시 1,000,000에 200,000(20%)을 더한 금액을 보통주 주주에 우선하여 배분받을 것이다.</span></p></li><li><p style="line-height:1.9;"><span style="">Series A 투자자가 위 1,200,000을 배분받은 후 다른 배분, 예를 들어 보통주 주주는 1,200,000을 초과하지 않는 한도 내에서 배분을 받는다.</span></p></li><li><p style="line-height:1.9;"><span style="">위 배분 이후에도 잔여액이 있는 경우 Series A 투자자는 잔여 배분대상액의 10%를 , 보통주주주는 90%를 배분받는다.</span></p></li></ul></div></td></tr></tbody></table>

2024.12.31. 근접한 시점에 지분의 추정공정가치를 결정하는 과정은 다음과 같다.

​

- **Step 1 - 최근 유상증자 거래의 가격결정 조건의 식별 : A사는 Series A 우선주를 1,000,000에 발행하였다.**
- **Step 2 - 배당 및 분배 권리와 관련 분기점(breakpoints)의 식별 :**

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 21.5px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">Dividend(Distribution)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">1st</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">2nd</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">3rd</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 21.5px;  "><div><p style=""><span style="">Series A Preferred holders</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 21.5px;  "><div><p style=""><span style="">Common shareholders</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 21.5px;  "><div><p style=""><span style="">Series A Preferred holders</span></p></div><div><p style=""><span style="">Common shareholders</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">1,200,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">1,200,000</span></p></div></td><td colspan="1" rowspan="2" style="width: 33.33%; height: 21.5px;  "><div><p style=""><span style="">split 90/10 between common and preferred shareholders</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">breakpoint 1</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 10.75px;  "><div><p style=""><span style="">breakpoint 2</span></p></div></td></tr></tbody></table>

**​**

- **Step 3- 지분의 공정가치 방정식 Set-up**

​

***Equity FV*** ***at 12/31/2024*** ***= FV of Series A Preferred+ FV of Common***

***FV of Series A equals to 1,000,000.***

***FV of common share is call option on common shares***

​

총 지분의 공정가치는 우선주 공정가치와 보통주 공정가치의 합이다. 우선주 공정가치는 최근 발행가액 1,000,000으로 확인된다. 보통주 공정가치는 call option 모형을 사용하여 산출될 것이다.

​

여기서 보통주가 call option이라는 의미는 만약 A사가 breakpoint 1 지점에서 1,200,000을 초과하여 배당(분배)할 경우 초과분은 보통주에게 분배되고 만약 A사가 초과배당을 하지 않는 경우 A사의 지분가치는 0(zero)가 되므로 이는 기초자산 총 지분(FV)이고 행사가격 1,200,000인 Call option의 가치와 동일하기 때문이다.

​

한편, 만약 A사가 breakpoint 2에서 2,400,000을 초과하여 분배할 경우 초과분배액의 10%는 우선주, 90%는 보통주 주주에게 배분한다. 따라서 보통주 지분의 총 가치는 다음과 같이 계산된다.

​

***FV of Common*** ***at 12/31/2024*** ***= Call Option on Common at break 1 -***

***10% of Call Option on Preferred at break 2***

​

따라서 2024년 말 현재 지분의 공정가치 추정액은 다음과 같이 표현할 수 있다.

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 129.0px;  background-color: #bdfbfa;"><div><p style=""><span style="color:#004e82;background-color:#bdfbfa;"><i><b>Equity FV </b></i></span><span style="color:#004e82;background-color:#bdfbfa;"><i><b>at 12/31/2024</b></i></span><span style="color:#004e82;background-color:#bdfbfa;"><i><b> =</b></i></span></p></div><div><p style="line-height:2.1;"><span style="color:#004e82;background-color:#bdfbfa;"><i><b>1,000,000 (recent transaction price)</b></i></span></p></div><div><p style="line-height:2.1;"><span style="color:#004e82;background-color:#bdfbfa;"><i><b>+ FV of Call Option on Common at break 1</b></i></span></p></div><div><p style=""><span style="color:#004e82;background-color:#bdfbfa;"><i><b>- 10% of Call Option on Series A at break 2</b></i></span></p></div></td></tr></tbody></table>

- **Step 4 - OPM에 적용할 변수의 결정 :**

​

무위험이자율(risk-free rate) 4%, 추정기간(expected term) 6년, 변동성(volatility) 80% 가정

​

- **Step 5 - 시행착오법(trial and error method)에 의한 지분가치의 계산**

​

Breakpoint 1과 Breakpoint 2를 모두 만족시키는 FV of Equity를 시행착오법으로 계산해 낸다. 예를 들면 아래와 같이 5,022,875라는 값은 Breakpoint1과 2의 Call option 산식 2개 모두를 만족시키는 값이다.

![](https://scs-phinf.pstatic.net/MjAyNDA4MjFfMjA4/MDAxNzI0MjE5NTM5MDI1.3q1ykk3CTV_2S_0zDhyZYMTx9O2Zrg8JGRLd7SS1xecg.RljS3i5z1-Ei_hvR8KpBKnKimWTSh14gyhDr1K-c5Nsg.PNG/image.png?type=w800)

***Under Equation, Equity FV*** ***at 12/31/2024*** ***\= FV of Series A + FV of Call Option on Common at break 1 - 10% of Call Option on Common at break 2***

***​***

***$ 5,022,875 = $ 1,000,000 + $ 4,430,673 - 0.1 \* 4,077,981***

***​***

***Overall, estimated FV of equity at 12/31/20X3 is $ 5,022,875.***

***​***

**출처 ; FinAcco (Complex Made Simple)**

**​**

**● View & Opinion**

**​**

Back-Solve method는 본격적인 매출과 이익이 실현되지 않는 초기 Bio기업의 지분의 공정가치를 최근 지분거래가액(transaction price)을 이용하여 추출해 내는 방법이다. Back-Solve method의 핵심은 납입된 자본으로 형성되는 순자산 공정가치의 배분로직(distribution logic)이다. 위 사례에서 우선주는 채권과 유사하게 납입원금에서 이자상당액을 합한 금액을 보통주보다 우선적으로 받는 반면, 보통주는 우선주 주주에게 배분되고 남은 금액이 있는 경우 우선주 주주와 동등한 배분을 받고 다시 남은 금액은 보통주와 우선주가 9:1로 나누어 받는 것으로 계약되었다고 가정하였다.

​

우선주 원리금을 1,200,000으로 본 경우 주주간 배분이 달라지는 분깃점(breakpoint)은 2개가 식별되는데, 첫번째 분기점은 우선주에게 귀속될 1,200,000, 2번째 분기점은 보통주에게 우선주와 동일한 1.200.000을 지급하는 2.400.000이다. 1,200,000~2,400,000 사이 구간에서 보통주는 기초자산이 지분의 공정가치이고 행사가격이 1,200,000인 Call Option의 가치를 가진다. 2,400,000 ~ 구간에서 보통주는기초자산이 지분의 공정가치이고 행사가격이 2,400,000인 Call option의 90%의 가치를 가진다.

​

즉, Call option 1에서 Call option 2의 10%를 차감한 가액에 최근 우선주 발행가액을 합치면 총 지분의 공정가치와 동일하게 될 것이다. 여기서 미지수 x에 해당하는 총지분 공정가치를 시행착오법으로 산출해 낸다.

![](https://scs-phinf.pstatic.net/MjAyNDA4MjFfMTc0/MDAxNzI0MjIwMzI5MjU4.MtNiHj_37kVgL7DqxASHmI1WQz-wJRu91BEh2wGsLW4g.E5k0RRSeaziCHFHGKw8A51KIBSr7v50x1-6IHfLcexMg.PNG/image.png?type=w800)

우선주주와 보통주 배분되는 **지분가치의** 분기점(source ; EQVISTA)

​