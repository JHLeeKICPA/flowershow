---
title: "[IFRS Issue Paper 227] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ② 이항모형의 EXCEL 구현 ①"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240919172448548im"
---
![](https://n2.news.naver.com/l.gif?type=content)[\[IFRS Issue Paper 220\] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ① (naver.com)](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240912152302571hg)에서는 Stock Option valation model로 Black-Scholes-Merton model, Lattice(Binomial) model, Monte-Carlo-Simulation model 3가지의 장단점을 논의했다.

​

[\[IFRS Issue Paper 220\] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ① (naver.com)](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240912152302571hg)

[![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fscs-phinf.pstatic.net%2FMjAyNDA5MTJfMjE3%2FMDAxNzI2MTE3NjYyOTQ3.QvbRAWnAQ-q9-TRmSvkYNK49svMa_7KMDf3nkrwer-sg.iberR6z-v0BAfpp6C9VXQ8g6QdXgkkpEg0AOfb6uYcUg.JPEG%2F20240903_103624.jpg%3Ftype%3Dw800%22&type=ff500_300)](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240912152302571hg)[

**\[IFRS Issue Paper 220\] KIFRS1102, 주식기준보상 평가모델(Option valuation models) ①**

220 ● Option valuation models 이항모형은 전환금융상품과 Stock-Option(share-based compensation under IFRS2)의 공정가치에 적용되는 공통모형이다. 이항모형의 가장 큰 장점은 적용의 편리성이다. 이 장점은 기초자

contents.premium.naver.com

](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240912152302571hg)

금번 Issue Paper에서는 KPMG IFRS2 Handbook에 소개된 흔히 이항모형이라 부르는 Lattice 모델의 장점과 엑셀구현 방법을 소개한다.

​

- 이항모형(이하 "lattice model")은 옵션구간(option term)별로 주식가격의 행보를 보여주므로 조기행사조건(early exercise parameters)이 모델이 반영될 수 있다. 가령, 만약 과거 경험에 근거할 때 주가가 행사가격의 2배 이상이 되는 경우 행사를 하는 사실에 근거, 각 노드(monitoring point)별로 주가가 행사가격의 2배인지 여부를 식별해야 한다.

​

- 보다 복잡한 결제유형도 측정 가능하다. 예를 들어 만약 옵션행사로 얻는 이익의 상한이 설정되어 있는 경우 각 노드(monitoring point)별로 주가가 행사가격의 2배이며 차액이 상한을 초과하는 경우 상한을 한도로 Cut하는 로직이 추가될 것이다.

​

- lattice model은 시장조건이 행사시점에 측정가능할 경우에는 시장조건이 부여된 보상에도 적용가능하다. 이 경우 각 노드(monitoring point)별 주가가 시장조건을 충족하는지 여부가 check되어야 할 것이다. 시장조건을 충족하는 시점에 시장가격과 행사가격의 차이인 내재가치를 가져오고 나머지는 버리는(value=0)로직이 설정되어야 한다. 그러나, 시장조건이 행사시점과 다른 경우가 대부분인데, 이 경우는 Monte Carlos mode을 적용하는 것이 적절하다. 그 이유는 lattice model 하에서는 시장조건이 충족되는 경우의 수가 너무 많아진다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfMTU2/MDAxNzI2NzI5NDQ5MDUz.cWR8s3OhKgQZV6NfPOrpHBM0zIkTZ6UWeF4udLwabtEg.hCRg2DWbhYU37MTyfatMA3jcQ8BKuvdYwOOEsJ5cXIQg.PNG/image.png?type=w800)

source ; KPMG

왼쪽 그림에서 시장조건이 없는 스톡옵션의 결제(Pay-off)는 주식가격의 진행(path)과 각 노드 지점과 일치하는 경우와 동일하게 측정되지만, 만약 시장조건이 부여된 경우 동 시장조건이 기대기간(expected term) 이전에 측정될 경우, 주가의 행보(path)와 노드 지점이 중요해 진다. 가령, 주가가 3년 후에 12를 초과해야만 행사가능한 조건을 가정할 때, 시장조건이 없다면 행사시점의 내재가치는 아래 그림에서 Path A와 B 두 Tree의 합이 되지만, 시장조건으로 인하여 Path B가 내가격(in-the-money)에 있더라도 동 가치는 0이므로 버려지고 옵션가치에는 Path A만 반영된다.

​

lattice model은 주가의 행보(Path)와 행사시점과의 대응(mapping)이 이렵기 때문에 시장조건은 Monte-Carlos simulation이 보다 유용하다.

​

● lattice model(이항모형)에 의한 Stock-Option valution 예시 (sourch ; KPMG)

​

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfODUg/MDAxNzI2NzMwOTgxMTk4.Bh2M2UvxkLzU-8K1fIBT81Gukp8uePkH9ff5yUWIi9Qg.POsf-7GVjRoi2gjxrMo52Z7uhGGFsmPDZljoq57H2kog.PNG/image.png?type=w800)

이항모형은 주가가 특정 확률(p)로 상승(up) 아니면 하락(dn, 1-p)하는 단순 2분화 행보를 가정한다. 이 경우 상승지수(u)는 로그함수를 따르며 하락지수(d)는 u의 역수이다. 그리고 확률 p는 좌측 그림의 수식에 의해 결정된다. 이 모델은 excel로 구현 가능하다.

​

아래는 이항모형에 적용될 변수와 이항모형 적용 결과를 요약한 것이다. 연간 변동성은 40%, 총 기간은 2년, 기간단위는 0.5년, 즉 6개월이므로 기간의 갯수는 4(2/0.5)가 될 것이다. 즉, Tree는 4번 진행한다. 이 기간단위 0.5년의 제곱근 값은 0.71이다. 이는 위 그림에서 로그함수를 따르는 상승지수(u)를 산출하기 위한 값이다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfMjYx/MDAxNzI2NzMxMTY3MTEz.RFj1AbymyLxGXaYF0BybYkPrZXgFsyDihXEOAEbk09gg.Nm-q4KeP7fnxluayI1aC5VEpyXZHDXGYgMGUlQ62rO8g.PNG/image.png?type=w800)

상승지수는 Excel의 EXP함수로 간단히 구할 수 있다. EXP 함수에 적용할 Factor는 변동성(Volatility) x node단위(위에서 6개월, 즉 0.5)의 제곱근)이다. 결과값은 1.32690임을 알 수 있다. 따라서 하락지수는 u의 역수이므로 0.75364(1/1.32690)로 계산된다. 또한 상승확률 역시 EXP함수에 적용할 Factor로 위 Return(수익율)을 적용하여 아래와 같이 산출가능하다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfNjUg/MDAxNzI2NzMyNjE2MTQz.1bQDqFqutURA9mdUYEvy3kFptww7Y0syXgyXUZqWRccg.yKWYuXmn71rC7tEAdE1JMz8klA3PwSMO5vOG4fgxTDEg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfMTA5/MDAxNzI2NzMzMzk3NjQz.SycmookoMS3-a_OhFCun7oY22bqjZAJyEDxUvofzVI4g.bh_ucRpmQ82QmlFe-OkkU7QFZoAQ6f8YhYnwzLeilQMg.PNG/image.png?type=w800)

​

즉, 상승계수(u), 하락계수(d), 상승확률(p)이 산출되었으므로 엑셀에서 주가의 행보(path)를 보여주는 Tree를 아래와 같이 그릴 수 있다. Grant date의 주가(opening price)인 10에서 상승, 하락을 4구간 반복(2년)하면서 아래와 같은 Tree를 만든다. 그리고 이들의 확률 Tree역시 p를 이용하여 생성가능하다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfNyAg/MDAxNzI2NzMzNTgwODE0.f3zDqyaDermQLe0MO1q3mcyAel1SsPnVjDCtpz3Lv7Qg.hCDS3pSbfPJ_zYN1XFRiDxp87pczxxvMw9gh6gx0fMIg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfMTIx/MDAxNzI2NzMzNjc4MzY5.YCzV8htMvoyTLe_yEvotzXvZe5m9aPZjKAhlhhO0KS0g.ReMl1MfDLgaoRBm1miorvKAFZy_fZWy4Wf5rbnQODH4g.PNG/image.png?type=w800)

그러면 각 노드별로 주가, 행사가격(10), 내재가치(intrinsic value, S-X), 옵션가격(Max\[(S-X),0\])이 다음과 같이 정리될 수 있다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfNDYg/MDAxNzI2NzMzNzg1MzQ5.7BZH7GmvIHKHlk__MmH9Pe03wznkog-PVAyIjYuFPWQg.zWFZYc_QMmv0REoT4OXWUo5XSIZ_rOWma5olF61cSIYg.PNG/image.png?type=w800)

Node별 옵션 내재가치 산출

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfMjc0/MDAxNzI2NzMzODA4Njkw.unBOenjai9YrpepyQnGafKCrBxs_hi-6WVz_3BwlvZ8g.1OYi2OLOI8YeDtJHiXls0Wn00YOppJh5AV4Nb7rSxj8g.PNG/image.png?type=w800)

확률가중평균 적용 옵션가치의 산출

위 사례는 period term이 4회로 매우 단순한 상황을 가정한 것이다. 실제 사례에서는 이 보다 훨씬 많은 period term이 적용될 것이다. 위 표에서 BSM(Balck-Scholes-Merton)에 의한 값과 5.6%의 오차가 발생하는데 만약 노드의 갯수가 증가하면 BSM과 Lattice의 값은 합일치 된다. 더 복잡한 lattice 모델은 계약기간 만료 전에 조기행사(early exercise)를 가정하는 것이다. 즉, lattice model은 경우의 수를 식별하므로 BSM보다 복잡한 상황을 가정할 수 있는 장점이 있다.

​

● Global IFRS Reference

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfMjU4/MDAxNzI2NzM0NTA4MDM2.K1G58n0HLUP6nsSxh-sgC-Nvcrmxpu6tYBJw_BDrvlog.Qkd-6cHaB89K9GPLzmxd18Sfh0vuVVTW7246jWcni1og.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfMTc0/MDAxNzI2NzM0NTY0MTAx.QFcd_K_se7E5F9e_9b7NtV7rHcSZlbPpBIHPbXQI6Q8g.PLYE5iEIQStIWmB_PjaSyWpbIQsVBx05V4waSh_gKysg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MTlfMSAg/MDAxNzI2NzM0NjAxOTUw.8uyQtcT7MjW6dfBZVxbjPQnJLb1HBUk6DBMp1yBjDesg.vBBEcpuA1W7wlgMp2ur8VptM8_Eb8O5XFQgJLct3Kgwg.PNG/image.png?type=w800)

[![](https://storep-phinf.pstatic.net/cafe_004/original_7.png?type=p50_50)](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/#)

​