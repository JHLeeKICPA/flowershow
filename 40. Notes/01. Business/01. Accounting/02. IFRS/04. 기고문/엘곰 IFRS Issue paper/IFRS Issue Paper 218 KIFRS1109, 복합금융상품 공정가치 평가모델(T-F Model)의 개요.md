---
title: "[IFRS Issue Paper 218] KIFRS1109, 복합금융상품 공정가치 평가모델(T-F Model)의 개요"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240909162738097yz"
---
![](https://n2.news.naver.com/l.gif?type=content)**218**

**● 복합금융상품 발행자의 최초 인식**

**​**

복합금융상품의 공정가치 평가에 가장 빈번하게 사용되는 T-F Model은 투자자가 매기간 가장 유리한 선택을 한다는 가정 하에 선택된 가치의 현재가치를 소급계산하는 방법이다.

​

전환사채(CB) 발행자는 최초발행시점에 Put, Call 등 내재파생 공정가치(Liability)를 산출하고 발행가액에서 파생상품부채 가치를 차감한 가액을 사채의 장부가액에 반영한다. 이 경우 Put(redemption right)의 가치는 Put이 포함된 사채를 T-F모형의 로직에 의해 산출한 후 여기에 일반사채의 공정가치를 차감하여 산출하고 Call(conversion right)의 가치는 T-F Model에 의한 CB 전체 가치에서 일반사채, Put의 공정가치를 차감하여 산출한다. 그 결과 발행가액과 CB 공정가치가 다른 경우 동 차이를 이연(defer)하고 후속기간에 상각(amortisation)하는 것이 CB 회계처리의 골자다.

​

물론 위 내용은 투자자 Call(conversion right)이 Refixing 조건으로 인해 부채로 분류되는 경우이다. 만약 Fixed-for-Fixed 조건을 충족하여 자본으로 분류되는 경우, 자본은 발행가액과 "Put+일반사채"의 차액, 즉 잔여가치(residula value)로 결정된다.

​

한편, 발행자는 복합금융상품에 대해 공정가치선택권(FVO ; Fair Value Option)을 적용하여 CB 전체를 공정가치로 인식, 측정하고 후속기간에 공정가치 평가할 수 있다. 이러한 FVO은 위에서 언급한 일반사채를 상각후원가(Amortisation cost)로 계상하는 것에 비해 손익변동성(volatility)이 훨씬 커지는 단점이 있는 반면, 복잡한 분리회계처리를 고민할 필요가 없는 장점이 있다.

​

위와 같이 복합금융상품을 하나의 공정가치 단위로 보는 경우 가장 많이 사용되는 평가모델이 T-F모델이다.

​

**● T-F(Tsiveriotis-Fernandes) 모형의 개요**

​

아래 그림은 필자가 T-F Model의 기본로직을 요약해 본 것이다. T-F Model의 바탕은 이항모형(binomial regression)이며 이항 Tree의 전개는 미래의 주가와 이자율의 변동을 우선적으로 결정해 준다. 아래에서 우측에서 좌측으로 이동하는 형태로 표현한 것은 이항모형의 출발점인 CB의 최초시점 공정가치는 만기에서 현재로 소급하여 측정(Rolled-back value)되기 때문이다.

​

![](https://scs-phinf.pstatic.net/MjAyNDA5MDlfMTk5/MDAxNzI1ODYxODg4MTY2.qMOyLen-I2NUEmWciOAut389-gyX3nAnYY3iv36yMssg.lH1qZpVaOQgpan_FMKLvPd7Z-ffqdUYQJ49pN7CaP6cg.PNG/image.png?type=w800)

**① 만기가치 ; 지분가치 + 부채가치**

**​**

투자자는 만기에 주식으로 전환하여 주식을 보유하거나 전환을 하지 않고 채권의 원리금을 보유하는 2가지 안 중 하나를 선택할 것이다. 즉 만기가치는 지분가치와 부채가치의 합이다. 이 때, 지분가치는 무위험이자율(risk-free rate)에 의해, 부채가치는 위험이자율(risk-adjusted rate)에 의해 할인된다. Black–Scholes model에서 익히 보았듯이 상승계수(u)와 하락계수(d)가 적용되어 지분가치, 부채가치 모두 상승, 하락 2가지 상황이 될 수 있다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MDlfMjE3/MDAxNzI1ODYzNjE4NDc5.g8ldy5b2hd9j7MlPL0pMMSXZCWJuwJjnhckdpNBFnbwg.NR2OsfktDWmyATRu51Uv6x5wAFAgiIm-ZFNVGhwmgAkg.PNG/image.png?type=w800)

이항모형에 의한 주식 및 채권 가격의 행보(상승계수 u /하락계수 d)

​

**② 만기 이전 가치 ; Max\[Min\[보유가치, 발행자 Call\], 전환가치, 상환가치\]**

**​**

만기 이전 투자자는 보유, 전환, 상환 중 한가지를 선택할 것이다. 즉, 각 기간별 가치는 Max\[보유, 전환, 상환\]이다. 이 중 보유가치는 위 그림에서 맨 오른쪽 4가지 상황별 지분가치 또는 부채가치의 합이다. 즉, 투자자가 CB를 보유하면 다음 기에 주식가격 또는 채권 만기가액을 보유할 수 있으므로 직전 기 가치는 이의 현재가치가 된다. 위에서 언급한 바와 같이 주식가치는 무위험이자율로, 채권가치는 위험조정할인율로 할인한다.

​

**③ 발행자 Call의 고려**

**​**

발행자는 수의상환권(Issuer's Call)을 보유할 수 있다. 주식가치가 상승하는 경우, 투자자의 전환을 방지하거나 이자율이 하락하여 채권가격이 상환가액보다 커지는 경우, 발행자는 Call을 행사하여 상환을 요구한다. 그러나 이 경우 투자자는 전환권 행사가 가능하므로 전환가치와 상환가치를 비교하여 전환 또는 상환을 선택할 것이다. 이런 상황을 강제전환 및 강제상환이라고 부른다. 따라서 발행자 수의상환권(Issuer's Call)이 존재하는 경우, 투자자는 발행자의 수의상환가치를 전환가치와 먼저 비교한다.

​

복잡해 보이는 아래 산식의 의미는 사실 간단한 것이다. 먼저 아래 red box는 주식가치의 상승, 하락 상황을 확률가중평균 한 것이다. 부채가치는 0이므로 coupon 이자율만 남는다. 이 가치와 blue box로 표시된 Call(발행자 수의상환권) 중 더 낮은 가액이 먼저 결정된다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MDlfMjk2/MDAxNzI1ODY0NzQxOTQ5.EMohvVDUBPFZUjl6S5xqFsf4kxCF6PYiMncna8f6e9Ig.2-HZ2f5IddxcACvMc_gM5oxsAIpky_sV2rY9PQFCMVYg.PNG/image.png?type=w800)

투자자는 아래와 같이 Max\[위 가치, 전환가치, 상환가치\]를 선택할 것이다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MDlfMjI0/MDAxNzI1ODY0ODA0Mjg0.gKHTRkaddjzTwDtaHyhN1LJ84M27vDm-P28nHUDsCs4g.Xa5dNN5y3Jf2GUVyU0jvTrqqCJBt_LNFrsDTxtk8Z5Mg.PNG/image.png?type=w800)

따라서 각 기간별 가치는 아래와 같은 산식으로 표현된다. 이 가치는 각 기간별 노드 한개에 해당한다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MDlfMjcw/MDAxNzI1ODYxODE2MDA1.6ieJ-JFzXYtidwHv3y9b3iHltMMpPPvakbATAhYBE50g.V1_24O9d7Mkk3u63R0a98fXIOl2p-MntPiUIVzGy5vsg.PNG/image.png?type=w800)

위 방식을 Tree에 따라 소급하여 계속 산출해 나가면 발행시점의 전환증권의 최초 공정가치가 산출된다.

​

​

**● View & Opinion**

**​**

실무에서 회사의 전문가의 활용으로 T-F model 평가보고서가 많이 발행되고 외부감사인은 감사인측 전문가를 활용하여 모델을 검증하는 경우가 많다. Technical한 Excel sheet상 산식의 올바른 적용을 검증하는 것 외, 발행된 전환증권의 조건과 상황에 맞게 로직이 구현되었는지를 검토하는 것이 중요하다.

​

**● Global article reference**

**​**

T-F Model을 이용한 복합금융상품의 평가가치는 구성요소간의 상관관계를 고려하므로 구성요소 각각의 공정가치를 단순합한 결과와는 (당연히) 다르게 된다.(아래 article 참조)

![](https://scs-phinf.pstatic.net/MjAyNDA5MDlfMjI3/MDAxNzI1ODY3NDkzNzg5.xV_t3V7WDGXuaQfDx-353MDfJf_7RISebCSTMDWniT0g.3j56x41lPgGmQiDgi6kxglM6L83eGuM7lkqrtWO8d60g.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MDlfMjIg/MDAxNzI1ODY3NjgyMzE4.pEUUyggUtPiGX3Gt6jz49iet7pI-ct6eQWU0QaIVpgIg.xms8kSdOgoT6TJMvtA87XJxC4Hp2-dUdY2KYl0Ngk38g.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MDlfMjM5/MDAxNzI1ODY3NzQxNjQ4.co6nSF_okN00Korwfyvy1Ybrj8rMiPyDSSpgCdswHt0g.bndt7gYGn_kYO2Bi8rTrs720wYqasdhW9VS5qyvhyMcg.PNG/image.png?type=w800)

**​**