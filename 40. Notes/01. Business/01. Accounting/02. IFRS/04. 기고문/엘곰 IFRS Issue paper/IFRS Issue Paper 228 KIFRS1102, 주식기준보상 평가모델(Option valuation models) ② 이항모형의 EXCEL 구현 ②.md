---
title: "[IFRS Issue Paper 228] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ② 이항모형의 EXCEL 구현 ②"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240920232754799ys"
---
![](https://n2.news.naver.com/l.gif?type=content)228

\[IFRS Issue Paper 225\] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ② 이항모형의 EXCEL 구현 ①에서는 Stock-Option Valuation Technique으로 가장 많이 사용되는 이항모형(lattice model)을 excel로 구현하는 방법에 대해 알아보았다. 금번 article에서는 저명한 회계 저널지인 "Journal of Accountancy([www.journalofaccountancy.com](http://www.journalofaccountancy.com/))"에서 이항모형을 excel에서 구현하는 방법을 설명하고 있어 금번 issue paper에서 소개하고자 한다. 이 두 article을 통해 막연히 수학통계의 영역으로만 생각해 왔던 이항모형에 보다 친숙해 질 수 있을 것이다.

​

[\[IFRS Issue Paper 225\] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ② 이항모형의 EXCEL 구현 ① (naver.com)](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240919172448548im)

[![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fscs-phinf.pstatic.net%2FMjAyNDA5MTlfMTI2%2FMDAxNzI2NzM0MzEyODI0.hf4aOpfn8hRVNubYMPol8Zc5kODylylIkaxx9zAG1hwg.LCvwsWq3hFp1lrBh4D1Uc5fp8AhYbCuyJ2eBJha_gGQg.JPEG%2F20240918_165448.jpg%3Ftype%3Dw800%22&type=ff500_300)](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240919172448548im)[

**\[IFRS Issue Paper 225\] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ② 이항모형의 EXCEL 구현 ①**

\[IFRS Issue Paper 220\] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ① (naver.com)에서는 Stock Option valation model로 Black-Scholes-Merton model, Latti

contents.premium.naver.com

](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240919172448548im)

**● BSM vs. Lattice**

**​**

실무에서는 복잡한 조건이 부여되지 않은 Plain-vanilla european option Style의 종업원스톡옵션(ESO)이 아닌 경우에는 이항모형(Lattice model)을 적용한다. BSM은 우리가 잘 아는 옵션가격결정모형인 Black-Scholes 모형과 동일하며 통계적으로 사전정의된 공식에 단일화된 변수를 적용하는 방식인 반면, Lattice model은 이항 Tree simulation을 이용한다. 따라서 경직되지 않고 flexible한 적용은 Lattice모델에 가능한 것이다. Lattice모형은 금번 Issue의 내용처럼 4년 만기의 4번의 구간을 가지는 이항트리를 엑셀에 구현하여 옵션가격을 산출 하듯이 다기간, 복잡한 조건의 옵션도 Tree를 확장시키고 각 Tree에 조건식을 부여하여 조건을 반영하는 등 유연하게 적용할 수 있는 것이다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">Black-Scholes-Merton</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">Binomial (Lattice)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  "><div><ul><li><p style="line-height:2.1;"><span style="">시장에서 거래되는 옵션평가를 위해 개발</span></p></li><li><p style="line-height:2.1;"><span style="">폐쇄형 가치평가 모델에 가장 많이 사용됨</span></p></li><li><p style="line-height:2.1;"><span style="">적은 수량의 Stock-Option부여 회사에 적합</span></p></li><li><p style="line-height:2.1;"><span style="">타 회사와의 비교가능성 용이</span></p></li><li><p style="line-height:2.1;"><span style="">사전정의된 공식으로 lattice에 비해 적용간편</span></p></li><li><p style="line-height:2.1;"><span style="">특이한 조건을 반영하기 어려움</span></p></li><li><p style="line-height:2.1;"><span style="">시간에 따라 변동되는 가정을 적용이 불가</span></p></li><li><p style="line-height:2.1;"><span style="">옵션이 만기에만 행사됨을 가정함</span></p></li><li><p style="line-height:2.1;"><span style="">만기까지 가중평균 변동성, 배당율, 무위험이자율이 일정하게 유지된다는 가정을 함</span></p></li><li><p style="line-height:2.1;"><span style="">위 변수들은 기업의 과거 경험에 기초한 경험율로, 경험율 산출이 어려운 경우 적용불가</span></p></li><li><p style="line-height:2.1;"><span style="">조기행사조건시 명시적인 기간구조를 적용하지 못하고 추정가중평균 만기를 사용해야 함</span></p></li></ul></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  "><div><ul><li><p style="line-height:2.1;"><span style="">Black-Scholes model보다 복잡함</span></p></li><li><p style="line-height:2.1;"><span style="">많은 수의 Stock option에 적용가능성 높음</span></p></li><li><p style="line-height:2.1;"><span style="">기술적인 전문성을 보유한 평가자가 필요</span></p></li><li><p style="line-height:2.1;"><span style="">독특한 특성, 조건이 부여된 옵션에 적용가능</span></p></li><li><p style="line-height:2.1;"><span style="">기간에 걸쳐 변동되는 조건, 가정 적용 가능</span></p></li><li><p style="line-height:2.1;"><span style="">추정의 정확성을 높일 수 있음.</span></p></li><li><p style="line-height:2.1;"><span style="">변동성, 무위험이자율, 배당율, 기대조기행사시점 등의 변동효과를 유연하게 반영가능함</span></p></li><li><p style="line-height:2.1;"><span style="">가정을 개발하기 위한 data분석이 필요</span></p></li><li><p style="line-height:2.1;"><span style="">사내 IT 프로그램 또는 외부소프트웨어 사용</span></p></li><li><p style="line-height:2.1;"><span style="">옵션이 주식가격이 특정수준에 이르는 시점에 행사되는 등, 특정요건에서는 유일한 방법</span></p></li></ul><p style="line-height:2.1;"><span style="">​</span></p><p style="line-height:2.1;"><span style="">​</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">European Option</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 43.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">American Option</span></p></div></td></tr></tbody></table>

**​**

**● Lattice model : Simple한 가정**

​

단순한 형태의 옵션을 Excel에 이항모형을 구현해 보자. 현재 주가는 30, 행사가격 30, 무위험이자율 3%, 주가변동성 30%, 4기간 조건의 옵션이다. 이항모형의 주가 행보(path)는 상승, 하락 2가지 방향으로만 전진하며 전진의 정도는 무위험이자율과 변동성에 영향을 받는다. 즉, 매 구간 주가수익율은 무위험이자율인 것이다. 그러나 변동성을 추가적용함으로써 마치 CAPM 공식에서 "무위험이자율+MRP X 베타"로 자기자본수익율을 산출하는 것과 유사한 형태이다. 다음기의 주가는 직전기의 주가에 (1+risk free rate)x (1+volatility)를 곱한 값이다.

​

즉, 주가상승시는 직전 주가 x (1+risk free rate) x (1+volatility)가 될 것이며 하락시 직전 주가 x (1+risk free rate) x (1-volatility)가 될 것이다. 또한 이러한 행보(path)에 의해 만기까지 Tree를 확장한 결과를 충족시켜 주는 확률이 필요하다. 이는 곧 위험중립확률(p)이라 할 수 있다.

아래 그림은 주어진 조건을 충족시키는 이항 Tree를 엑셀로 구현한 모습이다. 엑셀에서 구현한 이항 Tree를 이해하기 위해 Year1의 상승시 주가 40.17에 대해 수식을 표시해 놓았다. 앞서 설명한 바와 같이 상승시 주가는 직전주가x(1+risk free rate)x(1+volatility) = 30 x (1+0.03) x (1+30%) = 40.17로 계산된다. 반면, 하락시 주가는 직전주가x(1+risk free rate)x(1-volatility) = 30 x (1+0.03) x (1-30%) = 21.63이 된다. 상승 확률과 하락확률은 0.5(50%)로 가정되었다. 그러나 실제 lattice model을 적용할 때는 자연로그 함수(EXP, excel)를 통해 간단히 산출된다. 대부분 이 확률은 50%를 초과한다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MjBfMjQw/MDAxNzI2ODQwMDU1Mzcw.kQbx85cbR3W7atTbzgc2uXGx84fMjjYOcuIcNUlHXfwg.7LDqxFLF19fJU31s2ywzPL8P6CsDURZRfgejGLhmM2Ag.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MjBfMjI3/MDAxNzI2ODQwNzg4MDEx.7PvDG0iUt181TANG4ngImlacOcaLoPa50ACzv2WWuiUg.zv4dLetaJ2vO25I4oEjY2Ab-o6aUhxJoVu3414wcjX8g.PNG/image.png?type=w800)

**● Option의 특성**

**​**

시장에서 거래되는 Stock Option과 달리 종업원 스톡옵션(ESO)은 다음과 같은 특성이 있다.

​

- 행사될 수는 있으나 매각 또는 이전될 수는 없다.
- Blackout 기간동안에는 행사가 불가능하다. Blackout은 기업이 이익실적을 공시하기 직전에 또는 종업원의회사의 주식 또는 옵션의 매매를 금지하는 다른 시점(합병, 인수시, 자금조달시, 중요한 제품의 출시 등)에 선언하는 것이 일반적이다. Blackout 기간을 두는 목적은 시장가격에 영향을 주지 않기 위함이다.
- n은 통상 10년의 구간을 가지는데 시장에서 거래되는 대부분의 옵션만기가 1년인 것과 대비된다. n은 4년에 이르는 가득기간(vesting period, 이 기간동안에는 Stock Option은 행사될 수 없고 종업원이 퇴사하는 경우 Stock option이 취소되는 기간이다)에 의해 결정되는 것이다.
- n은 종종 특정 사유에 의해 조기행사(early exercise)된다.

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 129.0px;  background-color: #bdfbfa;"><div><p style=""><span style=""><b>옵션의 조기행사(Early Exercise)</b></span></p><p style=""><span style=""><b>​</b></span></p><ul><li><p style=""><span style="">회사가 허용하는 경우 : 조기행사는 스톡옵션 계약에 조기행사 가능한 경우를 명시하는 경우에만 가능하다. 이사회는 Stock option부여시점과 계약조건 변경시에 조기행사 조항에 대해 승인한다.</span></p></li></ul><p style=""><span style="">​</span></p><ul><li><p style=""><span style="">가득기간 완료전 : 조기행사는 가득기간이 완료되기 전이라도 언제든지 행사할 수 있다. 이러한 점은 가득기간이 종료되어야만 권리가 부여되는 일반적인 옵션과 차이나는 점이다.</span></p></li></ul><p style=""><span style="">​</span></p><ul><li><p style=""><span style="">세절감 효과 : 조기행사는 잠재적인 세효과를 기대할 수 있다. 특히 만약 주식의 시장가격이 유의적으로 상승하지 못할 때 부여된 경우 부여시점 직후에 행사하는 경우이다. 이 경우 행사시 부담할 부채를 최소화 할 수 있고 장기 자본이득 측면에서 잠재적으로 보다 유리하다.</span></p></li></ul><p style=""><span style="">​</span></p><ul><li><p style=""><span style="">종업원의 재정적 문제 : 조기행사는 종업원에게 조기에 행사가격을 지불하게 함으로써 회사로 하여금 적시에 필요한 자금을 조달할 수 있는 효과가 있다.</span></p></li></ul><p style=""><span style="">​</span></p><ul><li><p style=""><span style="">성장이 예상되는 시점 : 기업가치가 유의적으로 증가함으로써 미래에 더 큰 이익과 절세효과를 얻을 수 있을 것으로 판단되는 시점에 종업원은 조기행사를 선택한다.</span></p></li></ul><p style=""><span style="">​</span></p><ul><li><p style=""><span style="">퇴사시 : Post-termination exercise period(PTEP) 즉, 퇴사한 이후 가득된 옵션을 행사할 수 있도록 하는 기간이 촉박한 경우에 일부 종업원은 퇴사 전에 가득된 옵션의 조기행사를 선택한다.</span></p></li></ul></div></td></tr></tbody></table>

**● Option Value의 계산**

**​**

아래 표는 위에서 조건화 한 이항모형에 따라 각 구간(node)별로 계산된 주가를 무위험이자율로 할인하는 동시에 확률을 곱하여 현재가치를 산출한 노드별 결과값을 모두 합쳐 Option value를 산출하는 과정을 보여준다. Box에 표시된 적용산식을 보면 계산방식은 쉽게 이해될 것이다. 단순한 조건의 stock-option은 이와 같이 엑셀로 설계할 수 있다. 복잡한 조건이 부여되는 경우는 엑셀작업에 많은 시간이 소요되고 오류를 유발할 수 있으므로 Software를 사용할 수도 있지만 그 때 역시 기본로직은 동일한 것이다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MjBfMTkz/MDAxNzI2ODQxNDk3MDMy.C4CKe8PD-s1TujSSeHiQ8DrmVS45abqOqstgQHukP54g.21Y0Cd9o-YKoPIVniSMQ9RypV9zkEc0TxPkJc7deXF0g.PNG/image.png?type=w800)

**​**

**● 조기행사(early exercise) 반영**

**​**

주가가 행사가격의 2배(multiple ; early exercise factor)가 되면 Stock Option을 조기행사 하는 것으로 실증적으로 back-up되는 경우 위에서 설명한 이항 Tree의 각 node별 주가가 행사가격 30의 2배인 60을 초과하는 경우에만 Option value에 반영된다. 다른 node의 주가는 설령 내가격(in-the-money)상태라 하더라도 조기행사 조건을 충족하지 못하므로 가치는 0이 되어 Option value에 반영되지 못한다. 조기행사 조건이 부여된 옵션가치는 그렇지 않은 옵션가치에 비해 낮을 것이다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MjBfMjAx/MDAxNzI2ODQxNzU0Mzgy.IoQcV8Fw18pGntYUGV0cAb-Mka84FbV2IrQwadLYyV0g.1Ndzb7guTbENqpMCUtFeRuDc1nApWXs47e1utCkW0BMg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MjBfMTcw/MDAxNzI2ODQxNzkzMjk3.WrWEIWa77TAoXqzh03bpjT8BKtll-nEUJeZgL-oqAy4g.Qk2551s66WUKRT7z6oExv3X9IYrQeCIpRaDkX-yIJsUg.PNG/image.png?type=w800)

**​**

**● 다기간 주가변동성(volatility)의 반영**

**​**

**Lattice 모형이 Black-Scholes-Merton 모형에 비해 활용성이 높은 이유는 다양한 조건을 반영할 수 있기 때문이다. BSM은 European Option, 즉 폐쇄형 옵션을 전제한 통계적 산식(fomula)으로 Lattice모형과 같이 이항 Tree에 여러가지 조건을 반영할 수 있는 기능이 없다. 가령 이항 Tree 각 node별로 변동성이 다를 것으로 판단되는 경우 아래와 같이 구간별로 다른 상승지수 ((1+risk free rate)\*(1+****volatility****))를 적용할 수 있다.**

![](https://scs-phinf.pstatic.net/MjAyNDA5MjBfMjEg/MDAxNzI2ODQxODMxMDQ4.Qk1__1cxA_qdTh2xgrx6D59_g9GdvbyC2mEJz7PsM8Mg.iA7NhYobOFJVbU1YXU-wZ4gZJVR2qMaUMAT4fdB5YLQg.PNG/image.png?type=w800)

**● View & Opinion**

**​**

이항모형을 엑셀에서 구현해 봄으로써 어렵고 복잡한 산식에 가려져 있는 듯한 옵션가치평가를 좀 더 쉽게 이해할 수 있다. 이항모형은 모형을 단순화 하기 위한 핵심 가정이 개입되는데, 주가가 상승, 하락을 반복한다는 점, 상승시 주가와 하락시 주가는 무위험이자율과 변동성에 의해 결정된다는 점이다. 즉, 이항모형에서 주가수익율은 무위험이자율인 것이다. 그러나 변동성이 가미됨으로써 위험수익율과 유사한 형태를 가지고 있다.

​

이항 Tree가 확장되어 만들어진 수많은 주가가 확률가중되어 현재의 옵션가격에 이르게 하는 상승확률(p)는 구간과 변동성 변수를 로그함수식에 입력하여 간단히 산출 가능하다. 위 사례에서 부여시점의 주식가격(30)과 행사가격(30)은 동일하여 내재가치(intrinsic value)는 0이지만 변동성에 의해 option value는 8.46으로 산출되었다. 주가 변동성이 커질 수록 상승여지는 많아지는 반면 일정수준 이상의 하락은 미행사를 통해 가치를 0으로 만들기 때문에 옵션가치는 상승한다.

​

이러한 옵션평가모형은 Stock Option 뿐 아니라 금융상품인 전환증권의 전환권 평가시에도 동일하게 사용된다.

현재 이익이 창출되지 않지만 잠재력이 높은 신약개발 회사의 주가는 향후 큰 변동성을 보일 가능성이 높다. 이러한 회사가 발행한 전환증권에 내재된 전환권의 가치는 전체 가치에서 상당히 높은 비중을 차지한다. 만약 전환사채 발행가액의 80%가 전환권 가치라면 나머지 20%인 사채가치(상환권은 없다고 가정)는 상당히 할인발행 된 것이다. 현금유동성이 풍부하지 않은 벤처회사의 사채의 기대수익율은 매우 크고 조달금액은 작아질 것이다.