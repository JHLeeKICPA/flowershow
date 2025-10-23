---
title: "[IFRS Issue Paper 672]KIFRS1109, 부도확률 접근법에 따른 기대신용손실 측정(International GAAP 2025, EY Example)"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250511173511873lt"
---
![](https://n2.news.naver.com/l.gif?type=content)**672**

● **부도확률 접근법에 따른 기대신용손실 측정**

​

20X1년 12월 31일, Bank A는 총 장부금액 CU1,000,000의 10년 만기 일시상환(bullet) 대출을 실행하며, 매년 말 이자를 지급하고 원금은 만기일에 상환된다. IFRS 9에 따라 Bank A는 현재 및 미래예측 신용위험 정보를 고려하여 기대신용손실에 대한 손상충당금을 인식해야 한다.

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 129.0px;  background-color: #bdfbfa;"><div><p style="line-height:1.8;"><span style="">기대신용손실은 추정된 현금부족분(cash shortfalls)의 현재가치를 확률가중한 추정치이다. 이를 위해 다음과 같은 요소들을 추정한다.</span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style=""><b>① PD (Probability of Default, 부도확률)</b></span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style="">특정 기간 (예: t₁부터 tᵢ까지) 내에 부도가 발생할 가능성을 나타냄. 조기 상환(EEᵢ)이 발생할 수 있는 경우, 이 확률을 조정하여 PD에서 차감한 순(net) 부도율(PD)을 다음 산식을 이용하여 계산한다.</span></p></div><div><p style="line-height:1.8;"><span style="">PDₜᵢ × ∏_{j=t₁+1}^{i-1} (1 - EEⱼ)</span></p></div><div><p style="line-height:1.8;"><span style="">→ “지금까지 조기 상환이 없을 부도확률”을 누적곱으로 계산하여 PD를 조정</span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style=""><b>② LGD (Loss Given Default, 부도손실률) : </b></span><span style="">부도 발생 시 손실되는 금액의 비율. 부도이후 회수되는 현금흐름(회수가능한 담보)을 반영한 손실 추정</span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style=""><b>③ EAD (Exposure at Default, 부도시 노출금액) : </b></span><span style="">부도 시점에 회수불능 상태로 노출될 잔여원금 및 미수이자 등 포함한 가액으로 PD x LGD가 곱해질 Exposure</span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style=""><b>④ r (할인율) : </b></span><span style="">보고일 기준 현재가치로 환산하기 위한 할인율→ 유효이자율 또는 시장금리를 사용</span></p></div></td></tr></tbody></table>

**■ 기대신용손실(ECL) 산식**

![](https://scs-phinf.pstatic.net/MjAyNTA1MTFfMTA5/MDAxNzQ2OTQxMTgzNzQw.ml1nMUsWDNHpIdZRPIxRKNuluIHIvbaXIeMP0RW-sTEg.bXR6fY02aSix7FUrxMORlSOQ6Jfh1TuO3Shzsv2vdZYg.PNG/image.png?type=w800)

각 미래시점(i)별로 부도확률 × 조기상환(Early Exit) 미발생 누적확률 × 부도시손실률 × 부도시 노출금액을 곱한 후 이를 현재가치로 환산하여 전체 기간(t₁~tₙ)에 대해 합산한 것이 기대신용손실이다.

​

**▶ Stage 1**

**​**

- 연이자 지급 (annual)
- 일시상환 대출(bullet): 원금은 만기에 일괄 상환됨
- 12개월 부도확률(PD): 3%
- 회복(cure) 후 재부도 대상율 : 80%
- LGD: 25% (담보 및 보증 고려 후 손실률)
- EAD: 1,030,000
- ECL=\[1,030,000×0.17%×25%\] / (1+0.03) =CU425 (422)

![](https://scs-phinf.pstatic.net/MjAyNTA1MTFfMjA4/MDAxNzQ2OTQyMTk5ODY5.vdLhfQid_hhq9Ma6U4bkmljf7f4qBbUu9GRfaNKLBvAg.EH318IAKrV1QsV-LctRVwyuhf2wkeRfdRRJlSinyPtcg.PNG/image.png?type=w800)

출처 : International GAAP 2025, EY

Marginal PD(증분부도율)은 각 연도별 누적적으로 추가되는 부도율이다. 예를 들어 20X3년까지 누적 부도율은 0.49%에서 20X2년까지의 누적 부도율 0.17%를 차감한 0.32%는 "Only" 20X3년도에 발생할 부도율로 분자를 구성한다. 분모는 분자가 발생할 전제가 되는 상황으로 20x2년까지의 누적확률 0.17%을 제외한 잔여 확률로써 100%-0.17% = 99.83%이 되므로 증분부도율은 0.17%/99.83% = 0.17%가 된다.

​

이런 방식으로 20x4, 20x5....매년 산출한 PD값에 근거한 예상손실을 모두 합치면 아래에서 설명할 Stage2의 전체기간에 대한 기대손실액이 된다.

**▶ Stage 2**

​

Stage 2 진입 조건 : 20X4년 말에 차주의 신용위험이 유의하게 증가(SICR)하여 Stage 2로 분류하게 되었다. 이때부터는 전체 만기 기간 (t = 20X5 ~ 20Y1) 동안의 Lifetime ECL을 인식해야 한다. 이를 위해 먼저, Marginal ECL을 각 연도별로 계산 (20X5~20Y1)하는데, Marginal PD란 누적부도확률 간 차이로써 아래의 산식으로 계산된다.

![](https://scs-phinf.pstatic.net/MjAyNTA1MTFfMjQ0/MDAxNzQ2OTQyNDMyODA5.Ei1FkJmiqAdV4lbIozgujYKyfXyN_uzAmXfJmMsYW6Ug.PJjHpKdI0S5fSoCQK_O-NE24XmpWpBjJ8ayHYoitLJ4g.PNG/image.png?type=w800)

marginal PD 산식

\[20x5\]

- 20x5년 Cum PD = 1.40%, 전년 = 0%
- Marginal PD = (1.4% - 0%) / (1 - 0%) = 1.4%
- Expected Loss (20x2) = \[1,030,000 x 1.4% x 25%\] / (1+0.03) = 3,500

​

\[20x6\]

- 20x6년 Cum PD = 3.87%, 전년 = 1.4%
- Marginal PD = (3.87% - 1.4%) / (100% - 1.4%) = 2.51/98.6 =2.54%
- Expected Loss (20x6) = \[1,030,000 x 2.54% x 25%\] / (1+0.03)^2 = 6,017

​

**매년 동일 방식 적용. 각 연도별 ECL을 산출 후 할인하여 합산** → 총 ECL = CU50,285

![](https://scs-phinf.pstatic.net/MjAyNTA1MTFfNTgg/MDAxNzQ2OTQyNTc0MTAx.5abVwWRi6r-__E8mjtYfO7dbHuRJCpRkdcfUMDqQzugg.irooPnmnnrtZtGwLFcJfIva6lXMLHcdWAsudp3LHsL0g.PNG/image.png?type=w800)

출처 : International GAAP 2025, EY

**▶ Stage 3 : 손상자산 – 확정적 부도 인식**

​

Lifetime ECL = CU262,850

​

Stage 3 진입 사유 : 20X5년 말 차주가 채무를 불이행 → 부도(default)로 간주, Stage 3은 손상(impairment)이 확정되므로, 기대현금흐름 접근법을 사용, 세 가지 시나리오로 분기하여 각각의 ECL 추정한다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 17.66%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>시나리오</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 15.91%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>설명</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 13.55%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>EAD</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 13.12%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>CF(현금회수)</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 13.26%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>RC(회수비용)</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 12.23%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>할인율</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 14.29%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>기대손실</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 17.66%; height: 40.0px;  "><div><p style=""><span style="">1. Cure</span></p></div></td><td colspan="1" rowspan="1" style="width: 15.91%; height: 40.0px;  "><div><p style=""><span style="">채무자 상환 회복</span></p></div></td><td colspan="1" rowspan="1" style="width: 13.55%; height: 40.0px;  "><div><p style=""><span style="">1,030,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 13.12%; height: 40.0px;  "><div><p style=""><span style="">900,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 13.26%; height: 40.0px;  "><div><p style=""><span style="">0</span></p></div></td><td colspan="1" rowspan="1" style="width: 12.23%; height: 40.0px;  "><div><p style=""><span style="">3%</span></p></div></td><td colspan="1" rowspan="1" style="width: 14.29%; height: 40.0px;  "><div><p style=""><span style="">130,000</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 17.66%; height: 40.0px;  "><div><p style=""><span style="">2. Restructure</span></p></div></td><td colspan="1" rowspan="1" style="width: 15.91%; height: 40.0px;  "><div><p style=""><span style="">구조조정 후 회수</span></p></div></td><td colspan="1" rowspan="1" style="width: 13.55%; height: 40.0px;  "><div><p style=""><span style="">1,030,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 13.12%; height: 40.0px;  "><div><p style=""><span style="">800,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 13.26%; height: 40.0px;  "><div><p style=""><span style="">5,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 12.23%; height: 40.0px;  "><div><p style=""><span style="">3%</span></p></div></td><td colspan="1" rowspan="1" style="width: 14.29%; height: 40.0px;  "><div><p style=""><span style="">241,737</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 17.66%; height: 40.0px;  "><div><p style=""><span style="">3. Liquidation</span></p></div></td><td colspan="1" rowspan="1" style="width: 15.91%; height: 40.0px;  "><div><p style=""><span style="">담보 매각</span></p></div></td><td colspan="1" rowspan="1" style="width: 13.55%; height: 40.0px;  "><div><p style=""><span style="">1,030,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 13.12%; height: 40.0px;  "><div><p style=""><span style="">700,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 13.26%; height: 40.0px;  "><div><p style=""><span style="">10,000</span></p></div></td><td colspan="1" rowspan="1" style="width: 12.23%; height: 40.0px;  "><div><p style=""><span style="">3%</span></p></div></td><td colspan="1" rowspan="1" style="width: 14.29%; height: 40.0px;  "><div><p style=""><span style="">350,388</span></p></div></td></tr></tbody></table>

Stage 3에서는 부도 발생 후이므로 부도 후 회수 가능한 금액(현금흐름)을 확률 시나리오별로 할인해 계산한 후, 회수불가능한 금액을 충당금으로 결정한다. ECL은 각 시나리오별 회수불가능액에 확률을 곱한 금액이다.

![](https://scs-phinf.pstatic.net/MjAyNTA1MTFfNjMg/MDAxNzQ2OTQyNzUzNTU1.qGkLiqNvqX2aEueuNvdEfke8mgDBZpjESXaO22CXSJ4g.1av8Yjc-scsA31Cum_eMV_2ujAfXC0z26z9IFqyNeyAg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNTA1MTFfMTA1/MDAxNzQ2OTQyNzk4ODEy.MXJtw7xwQCyk9wDHov5MtaEmY9_YRse5qf2fbQ2MepAg.r8d1gXGGM51EpUEpgpp-U5xKS5iTQHELB1p1GLGGO30g.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNTA1MTFfMjc0/MDAxNzQ2OTQyNzAyNTUz.jutFe5SweSkrN1h-5Uxx--RAQyFUAmFtItgF3pYrZ14g.m4Vbtms03TOWuCc_bSIJpMSq-EVgX2rbQs6wxPKWQW4g.PNG/image.png?type=w800)

출처 : International GAAP 2025, EY

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">구분</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">적용 기준</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">계산 방식</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">결과</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">Stage 1</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">12개월 부도확률</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">Marginal ECL for 1 year</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">CU422</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">Stage 2</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">전체 수명기간</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">Marginal PD 기반 DCF</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">CU50,285</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">Stage 3</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">확정적 부도</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">CF/RC 시나리오별 가중평균</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 40.0px;  "><div><p style=""><span style="">CU262,850</span></p></div></td></tr></tbody></table>

​