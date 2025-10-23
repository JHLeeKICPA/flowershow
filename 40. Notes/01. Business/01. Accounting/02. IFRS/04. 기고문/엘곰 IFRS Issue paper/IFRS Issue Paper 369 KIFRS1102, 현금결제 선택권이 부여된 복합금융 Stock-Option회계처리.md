---
title: "[IFRS Issue Paper 369] KIFRS1102, 현금결제 선택권이 부여된 복합금융 Stock-Option회계처리"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250209162143009ub"
---
![](https://n2.news.naver.com/l.gif?type=content)**● 주식결제와 현금결제 중 선택할 수 있는 권리가 부여된 주식기준보상계약의 회계처리**

​

IFRS2에서는 상대방(ex; 종업원)이 주식 기반 보상에서 결제 방식을 선택할 수 있는 경우, 회사입장에서 이는 일반적으로 복합 금융 상품으로 분류된다. 이러한 분류는 결제방식(현금 또는 주식)의 선택으로 인해 부채(결제가 현금인 경우)와 자본요소(결제가 주식인 경우)를 모두 포함하는 금융상품이 생성되기 때문이다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMDlfMTcx/MDAxNzM5MDgxODA2MDA1.ipaXvfElb0Z1ogbZk5VTT_MJS5xWnfpU8YBPFLhJYaQg.5rm3zfq9ipHHbMfXaGBqNn_hQuIeYfIdAp5qFXBp4akg.PNG/image.png?type=w800)

부채요소와 지분요소의 합으로 표시되어 있지만 가장 먼저 산출되어야 하는 값은 Total Fair Value이다. 자본요소는 잔여가치(residual value)로 총 가치에서 부채요소 가치를 차감하여 계산되기 때문이다. 전환사채와 같은 복합금융상품의 총 가치를 T-F Model로 평가한 뒤, 상환권부 채권의 가치를 산출하고 여기에서 일반채권의 가치를 차감하여 파생상품(상환권+전환권, 전환권이 부채라고 가정) 가치를 산출한다. 만약 전환권이 자본인 경우에는 상환권부 채권의 가치를 산출한 다음 복합금융상품 전체 가치에서 이를 차감한 잔여가액으로 전환권가치를 확정한다. 여기서 T-F모델을 이용한 전체가치는 투자자 관점에서 상환, 보유, 전환 3가지 행동 중 가장 유리한 것을 선택한다는 전제 하에 노드(주가 이동 구간)별 주가를 이항모형으로 추정하고 각 노드별 채권가치를 선도이자율로 할인하여 채권가치를 추정하여 산출하게 된다.

​

마찬가지로 종업원에게 부여한 현금결제형 선택권부 Stock Option 역시 종업원 입장에서는 주식결제형과 현금결제형 중 본인에게 유리한 것을 선택하는 행동을 한다는 가정이 적용될 수 있을 것이다. 이는 전체 가치가 Max\[주식결제형, 현금결제형\]으로 결정됨을 의미한다.

그러나 현금결제형 역시 주식가격과 전환가격의 차이에 해당하는 금액을 지급하는 것이므로 주식결제형과 가치가 동일하다. 따라서 전체가치란 Stock option의 가치가 되는 것이다.

​

**1step** : 첫번째 단계는 해당 거래 전체의 공정가치인 Stock Option의 가치를 산출한다. 산출방법은 Black-Scholes Model (if simple conditions apply), Monte Carlo Simulation (for complex vesting and settlement conditions),Binomial Lattice Model (for iterative probability-based decisions) 등이 있다. 회사가 3년 근무조건 하에 1000주의 Stock-Option(주식결제형)과 행사시점의 1000주의 Fair-value상당액의 현금결제형 중 선택할 수 있는 조건이 부여된 Stock-Option을 부여했다고 가정해 보자.

​

먼저 가치평가를 위한 입력변수(input)를 결정한다.

- 부여시점의 주식가격 : 50
- 행사가격 : 50 (at-the-money)
- 기대변동성 : 30%
- 무위험이자율 : 3%
- 기대배당율 : 2%
- 가득기간 : 3년
- 기대 옵션수명 : 5년
- 현금결제형을 선택할 확률 : 40% (주식결제형 선택확률 = 60%)

​

**2step** : 아래 블랙숄즈 모형 산식을 이용하여 공정가치를 계산한 결과(option value)는 12이다. 따라서 총 공정가치는 12,000(1,000주 x 12)가 된다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMjAw/MDAxNzM5MTUyNzg5MTI5.6aKlibSFNGWVdt1nMHX268MJC80JilHUj--xnX3sQqwg.MYsPz2wl5qmC5dxZwqtgkVO8FLWSw4KjtJam4eYA7R4g.PNG/image.png?type=w800)

**3​**step : 부채의 공정가치를 산출한다. 부채의 공정가치는 현행 주가 50으로 추정된다. 그러나 이 가치는 가득기간동안 계속 변동할 것이다. 현금결제형 선택가능 스톡옵션의 공정가치를 50,000(50x1,000)으로 가정한다.

​

**4step** : 확률 가중평균 공정가치를 산출한다. 주식결제형 선택확률은 60%, 현금결제형 선택확률은 40%이므로 총 공정가치는 다음과 같이 계산된다.

​

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfOCAg/MDAxNzM5MTUzMzA3MDM2.Iaj9GBxpx7AvvDUtdpvyVVmZy6elpq1yTonHX9lJhAcg.Ao5qos4joiNK1_eVfXikTCiiJwiZI1Ve8xLLXt6Xb0Ag.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMTkw/MDAxNzM5MTUzNTM1NDc1.ag7K1KKe9j3zWuDAr4zkThK5YJ0S2jEUBo5f2Y5HOyUg.fMz1HrBGXjEbKPNJthVGasgd2vCCb3HoBq3mQb2L13og.PNG/image.png?type=w800)

**5step** : 회계처리, 부여일 시점의 보상비용 27,200은 3년에 걸쳐 인식된다. 지분요소 12,000은 항상 고정되며 재측정되지 않는다. 부채요소 50,000은 매기간 주가에 연동하여 재측정된다.

​

만약 주가가 상승하는 추세를 보인다면 부채요소(현금결제형)가 증가할 것이며 종업원이 주식결제형을 선택하게 되면 부채요소는 환원(reverse)되고 최종비용은 주식공정가치에 근거하여 결정되게 된다.

​

● 후속회계처리

​

(1) 1차연도에 주가가 55로 상승하면 현금결제형 가치가 55.000으로 상승하면서 가중평균 총가치 역시 증가하게 될 것이다. 1차연도 비용은 증가한 가치의 1/3이 될 것이다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMTYy/MDAxNzM5MTUzNTkyMjkz.aJTJoutcTTKY-5A2Pv9IiT58-vhHr6PvipQOY8ebf3Eg.dKk65ND0utnEgR86-g5WWBwDp_Zw8H9WqHXljLKpgoEg.PNG/image.png?type=w800)

​

(2) 2차연도에 주가가 65로 더 상승하게 되면 현금결제형 가치가 65.000으로 상승하면서 가중평균 총가치 역시 증가하게 될 것이다. 2차연도 비용은 증가한 가치의 2/3에서 1차연도 인식한 금액을 차감한 가액이 된다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfNjkg/MDAxNzM5MTUzNzEwMTE1.jRWV14g-7LTKHwwgwaRPPYTS5VRHAe6b8aQbviAL3Dwg.Pr38F2SEsvmne995-5INeWJQC7Q_tdAwBtw6ocG9gUgg.PNG/image.png?type=w800)

(3) 3차연도에 주가가 70로 더 상승하게 되면 현금결제형 가치가 70.000으로 상승하면서 가중평균 총가치 역시 증가하게 될 것이다. 3차연도 비용은 70기준 총가치에서 2차연도까지 누적 인식한 금액을 차감한가액이다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfNDQg/MDAxNzM5MTUzNzc4Mjc4.GMJQY9AHgi5n19kienoDfLU_jOmpHWP-jEe2JNcouHQg.4li7fm3EtXxM4o5skZ9AL2hqUKqgWn2iG18ZVOR5_Fcg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMjYy/MDAxNzM5MTUzOTg5ODE0.hRkhAAcMnlkuQ3Wxwp9OzsBC59tcJ3-yBcGR2fe2vGgg.osRCnKJv8dJ7oitSUTFfQkA6Ii1DT9TPkGgG_mVYDY4g.PNG/image.png?type=w800)

(3) 3차연도말에 주식결제형(Case1) 또는 현금결제형(Case2)으로 결제되는 경우 각 회계처리는 아래와 같다. 즉, 주식결제형을 선택한 경우, **부채요소는 환원(reverse)되고 최종 비용은 12,000으로 자본에 잔존한다.** 반면 현금결제형을 선택한 경우, **최종 평가가액인 70,000이 상환되면서 총 비용인식액은 70,000이 된다.**

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMTIx/MDAxNzM5MTUzODQ0MzM4.7vWSGvbItitKOwY0YnNADZ-8-rCnZcBuk2sDco8h2nog.1UVHiYFV0XG0GsFfJbxtjyLNAP7uSdVPYvSlbCmTpsYg.PNG/image.png?type=w800)

**​**

**● 확률이 변동되는 경우**

**​**

위에서 최초 부여시점의 확률(주식결제형 선택확률, 현금결제형 선택확률)은 후속적으로 추정의 변경이 발생할 수 있다. 주식결제형 : 현금결제형은 60%: 40%를 기본base로 아래와 같은 4가지 시나리오를 가정하자. 다른 조건은 위 사례와 동일하다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfNTEg/MDAxNzM5MTU0OTg3NzEy.gsA21eK5rUZwqHzIARvWOUz1MskwWJqjLaykkrssGNAg.EJpGuDtk1OixTLhw-ZbwL_mD7TnbFnyELhN22uxTTSEg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMjI4/MDAxNzM5MTU1MDE2NDAx.TXOykE-u1d5A5irqpmYOnc1iuS0LW8cuTAW2TNYrzuYg.HAvqCTgLhohxhfVReXv4ja59DBqBtpXPE-j5cvn7ozYg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMjkw/MDAxNzM5MTU1MTYxNDk1.8GwZPoZi4h9RyXYuK9v8BYjdCo12flGk2sF_LgtsKJ4g.OYiVEPbIbL6artC75O5tYYBjV-x8jHXV9lOhZCrRvIQg.PNG/image.png?type=w800)

최초 현금결제형가치가 크기 때문에 현금결제형이 행사될 확률이 높을수록 기업이 인식할 비용은 커진다. 반대로 주식결제형 행사확률이 높을수록 총 비용은 작아진다. 기업은 주식결제형을 행사를 유도하는 incentive를 부여함으로써 총 비용의 크기를 줄일 수 있다.

​

**● 가격변동과 행사확률변동이 mix되는 경우**

**​**

실무에서는 가격변동과 행사확률 변동이 동시에 발생하는 경우가 있을 것이다. 두가지 변수가 교차적용되는 경우 Stock option 총 가치의 Matrix는 아래와 같다. 주식가격이 높아질수록, 현금결제형 행사 확률이 높아질수록 Stock option의 총가치는 커짐을 알 수 있다. 만약 기업이 손익변동성(earnings volatility)을 줄이고자 한다면 현금결제형 행사가능 수량에 한도(cap)를 설정하여 일정부분은 주식결제형을 행사하도록 유도할 수 있다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMjY4/MDAxNzM5MTU1NDI2MDM5.YdT4x7LQgnvFKESHEsQq5_jtSpP5jTAs8NdXbfJBmdYg.J8mrNMwj_wf34aL8hbNuMRm-r3SHNmswWzl-01f9xtUg.PNG/image.png?type=w800)

​

**● Monte Carlo Simulation을 적용한 결과**

**​**

몬테카를로 시뮬레이션 모델로 약 1,000회의 시뮬레이션 적용결과 3년 후 예상 주가는 63.39로 산출된다. 아래표를 보면 예상주가는 40에서 90까지의 range를 가지면 가장 높은 확률에 해당하는 주가는 63.39이다. 긴 꼬리(long tail)를 가지지 않음은 주가가 더 높아질 수록 현금결제형 원가가 더 커짐을 의미한다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMTUg/MDAxNzM5MTU1OTg0MjM2.VEpYFjdYL8_IMR89bGuqUIU0m3_t0t8sls39sOjz728g.UtGbDjT4U1j7QpiEVTwj0mzzAxcvKMBAKf66cd8lUmIg.PNG/image.png?type=w800)

이 주가를 전제로 위 4가지 시나리오별 총 가치는 다음과 같다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfNzMg/MDAxNzM5MTU1ODQ4ODg5.lu8pQThgbMOk-RWCUGO78-gC4sre3XMnynBgIdD-idUg.kzKf9yKuxmjXSLAQZ4WjFTnDpX6AHSj-2SuS8vjgFfQg.PNG/image.png?type=w800)

예상주가가 50에서 63.39로 증가함에 따라 현금결제형 원가는 약 26.8% 증가하게 된다. 따라서 총 비용을 통제하기를 원하거나 변동성을 낮추려 주식결제형에 incentive를 부여해야 할 것이다. 아래 표를 보면 변동성이 커질수록 주가는 증가하는 경향을 보이고 넓은 분포값을 가질수록 더 높은 주가를 형성함을 알 수 있다. 40% 변동성 하에 주가는 더욱 퍼져 보이는데 이는 높은 위험, 잠재적으로 더 큰 비용인식(현금결제형) 가능성을 의미한다.

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMTMy/MDAxNzM5MTU2MjA3OTM5.kg-U0SLf4UXxYk7gSrH6Jw5NyxubOo3TuYJZYS2EtDAg.7QcgCr2QqZq-awWkc1PTUMeOzPpz3F0q-tUxvn71Tt4g.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNTAyMTBfMTU2/MDAxNzM5MTU2MjQyMzc3._kaH11QnVTfFZPpKIa_sQeHFv2hhTPIlyGTMIOEo9jYg.NCIMa0WtTaPBouemDJaxNaV92zBQCJehWCVW0879COwg.PNG/image.png?type=w800)

**● View & Opinion**

​

최초인식시점에 자본요소와 부채요소로 나누기 전에 두 요소의 상업적실질(commercial substance)을 고려해야 한다. 이 때, 상업적실질이 없다는 것은 가령 과거 경험상 현금결제형 또는 주식결제형을 선택한 적이 없는 경우가 한 예가 될 수 있다. 하나의 결제방식이 상업적실질이 없다고 판단되면 해당 결제방식과 관련한 요소(부채 or 자본)는 무시하고 현금결제형 주식기준보상 또는 주식결제형 주식기준보상 둘 중 하나만 적용하면 된다.

​