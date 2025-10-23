---
title: "[IFRS Issue Paper 730]KIFRS1113, KIFRS1036, 자기자본비용 산출시 적용할 베타(Bloomberg vs. KICPA)"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250522223137722kl"
---
![](https://n2.news.naver.com/l.gif?type=content)730

● 블룸버그(Bloomberg)는 조정베타(Adjusted Beta)를 기본적으로 제공하며, Yahoo Finance는 공식적으로 조정 여부를 명시하지 않지만, 조정베타를 제공하는 것으로 알려져 있다.

​

**Adjusted Beta = 0.67 × Raw Beta + 0.33 × 1.0**

​

이 식의 의미는 다음과 같다.

​

Raw Beta는 통계적으로 추정된 실측 베타(과거 수익률 기반 회귀 분석 결과)이고, 1.0은 시장 전체의 베타(시장과 동일한 변동성 가정), 따라서 조정베타는 장기적으로 기업의 베타가 시장 평균(1.0)으로 수렴한다는 가정에 기반하여 보정된 값이다. 블룸버그에서는 원자료로부터 추정된 Raw Beta도 조회 가능하다.

​

Yahoo Finance는 자체적으로 계산된 베타 값을 제공하나, 명확히 조정 여부에 대한 공식 설명은 없다. 그러나 실무적으로 관찰된 수치들과 비교해보면, Yahoo Finance에서 제공하는 베타도 대부분 조정베타인 것으로 여겨진다. 즉, Yahoo Finance에서 제공되는 베타 값은 블룸버그와 비슷하게 2/3 × 실질베타 + 1/3 × 1.0 공식을 적용한 것으로 보인다. 이는 특히 S&P 500 기준의 5년 월간 수익률로 추정된 raw beta와 비교했을 때, YahooFinance의 값이 그보다 다소 1.0에 가까운 값으로 조정되어 있는 경우가 많기 때문이다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 22.89%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;"><b>항목</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;"><b>블룸버그 (Bloomberg)</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;"><b>Yahoo Finance</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 22.89%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;"><b>기본 제공 베타</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">조정베타 (Adjusted Beta)</span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">조정베타로 추정되나, 공식 명시는 없음</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 22.89%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;"><b>계산 방식</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">2/3 × Raw Beta + 1/3 × 1.0</span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">유사한 방식 추정</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 22.89%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;"><b>Raw Beta 제공</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">제공됨 (BETA_RAW)</span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">제공 안 됨</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 22.89%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;"><b>주가/지수 기준</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">S&amp;P 500 등, 사용자 선택 가능</span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">S&amp;P 500로 추정 (미국 기업 기준)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 22.89%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;"><b>수익률 기간</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">2년 주간 수익률 등 옵션 선택 가능</span></p></div></td><td colspan="1" rowspan="1" style="width: 38.55%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">보통 5년 월간 수익률 기반 (추정)</span></p></div></td></tr></tbody></table>

아래는 Yahoofinance에서 제공하는 삼성전자의 베타인데, 0.74로 조회된다.

![](https://scs-phinf.pstatic.net/MjAyNTA1MjJfMzMg/MDAxNzQ3OTE5MjMxMzU2.Mq7IbBglVn58LJhZsfzfQzGeE2EqGc_inWCMaMhTBvIg.lwtMfcIRJbYE5oxwnERhSQvKUj1sKy_ENA2KqEtuq8Qg.PNG/image.png?type=w800)

​

■ 한공회 베타조회 서비스

​

한공회(KICPA)는 최근 베타계수 조회서비스를 개편하였으며 실질베타 외에도 조정베타(Bloomberg)도 제공하기 시작했다. 대표지수는 국내주식은 KOSPI, 미국주식은 S&P이고, 실질베타와 조정베타의 정의와 베타계수 산출기간을 아래와 같이 설명해 주고 있다.

![](https://scs-phinf.pstatic.net/MjAyNTA1MjJfMjQy/MDAxNzQ3OTIwMDM5NTA0.QqoDcNX3qM9f-vO_KcoHdw13NKCxshQZedQv6dDKJhMg.ahw_mfugJlpIXrmwZopTTokxA5kWio_vDbKeuQSmwIcg.PNG/image.png?type=w800)

삼성전자의 베타를 조회해 보자. 실질베타는 1.034, 조정베타는 1.023으로 조회되므로 Yahoofiance에서 조회된 값과는 다르다. 사용된 데이터와 적용기간이 다르다는 의미이다.

![](https://scs-phinf.pstatic.net/MjAyNTA1MjJfMjE2/MDAxNzQ3OTE5NjY5ODgx.33t1Msuh_Vybdn_0-SrXlXcf8Ljf_JO8j6pXfti3_58g.81L3x9kA04C53zaGUFfc3v7rNZUhr1SFiJkmD3_Zxhwg.PNG/image.png?type=w800)

​

● View & Opinion

​

왜 조정하는가?

​

조정베타는 장기적으로 베타가 1에 수렴한다는 경험적 연구(Blume Adjustment 등)에 기반하며, 순수한 회귀분석에 따른 raw beta는 미래 예측력이 떨어질 수 있다는 문제를 보완하려는 것이다.

​

DCF 평가 시 할인율(WACC 또는 자본비용)을 추정할 때 사용하는 베타(beta) 값은 매우 중요한 입력치이며, 베타의 종류(실질베타 vs 조정베타), 적용기간(예: 2년 vs 5년), 시장지수 기준(S&P 500 vs KOSPI 등)은 할인율의 적정성에 중대한 영향을 미친다. 다음은 실무에서 고려해야 할 선택 기준이다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 16.41%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">구분</span></p></div></td><td colspan="1" rowspan="1" style="width: 39.67%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">실질베타 (Raw Beta)</span></p></div></td><td colspan="1" rowspan="1" style="width: 43.92%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">조정베타 (Adjusted Beta)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 16.41%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">정의</span></p></div></td><td colspan="1" rowspan="1" style="width: 39.67%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">과거 수익률 회귀분석에 기반한 통계적 산출치</span></p></div></td><td colspan="1" rowspan="1" style="width: 43.92%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">Raw Beta를 기반으로 1.0에 수렴하도록 보정한 값</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 16.41%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">계산식</span></p></div></td><td colspan="1" rowspan="1" style="width: 39.67%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">회귀 분석 결과값 (변수 없음)</span></p></div></td><td colspan="1" rowspan="1" style="width: 43.92%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">0.67 x Raw Beta + 0.33 x 1.0</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 16.41%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">장점</span></p></div></td><td colspan="1" rowspan="1" style="width: 39.67%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">실측 데이터 기반의 ‘있는 그대로’</span></p></div></td><td colspan="1" rowspan="1" style="width: 43.92%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">미래의 평균회귀(mean reversion)를 반영</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 16.41%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">단점</span></p></div></td><td colspan="1" rowspan="1" style="width: 39.67%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">노이즈, 과적합 가능성</span></p></div></td><td colspan="1" rowspan="1" style="width: 43.92%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">추정이 보수적이며 덜 민감할 수 있음</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 16.41%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">사용 목적</span></p></div></td><td colspan="1" rowspan="1" style="width: 39.67%; height: 40.0px;  background-color: #bdfbfa;"><div><p style="line-height:2.1;"><span style="">현재의 위험수준 정확 반영</span></p></div></td><td colspan="1" rowspan="1" style="width: 43.92%; height: 40.0px;  background-color: #bdfbfa;"><div><p style="line-height:2.1;"><span style="">장기평가용, 보수적 시나리오</span></p></div></td></tr></tbody></table>

실무 추천

​

- Raw Beta: 변동성이 크거나 기업 구조가 최근 바뀐 경우 (예: 구조조정, 업종 변경, M&A)
- Adjusted Beta: 장기 안정적인 비즈니스 모델 또는 보수적인 평가를 원할 때
- 실제 적용: 둘을 모두 산출해 비교한 후, 중간값이나 상황에 따라 선택

​

적용 기간 (Estimation Window)

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 22.75%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">기간</span></p></div></td><td colspan="1" rowspan="1" style="width: 32.01%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">특징</span></p></div></td><td colspan="1" rowspan="1" style="width: 45.24%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">추천 상황</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 22.75%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">2년 (weekly)</span></p></div></td><td colspan="1" rowspan="1" style="width: 32.01%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">최신 시장 민감도를 반영</span></p></div></td><td colspan="1" rowspan="1" style="width: 45.24%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">주가 변동성이 최근 커졌거나 구조변화가 있었던 기업</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 22.75%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">5년 (monthly)</span></p></div></td><td colspan="1" rowspan="1" style="width: 32.01%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">장기 평균적 특성 반영</span></p></div></td><td colspan="1" rowspan="1" style="width: 45.24%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">안정적 업종 (예: 유틸리티, 소비재)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 22.75%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">3년 (주간/월간)</span></p></div></td><td colspan="1" rowspan="1" style="width: 32.01%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">중간적 균형</span></p></div></td><td colspan="1" rowspan="1" style="width: 45.24%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">대부분의 일반기업에 적절</span></p></div></td></tr></tbody></table>

실무 팁:

​

- 최근 2년 주간 수익률은 단기적 민감도를 잘 반영하지만, 데이터 노이즈가 많을 수 있음.
- 5년 월간 수익률은 장기적인 성향을 반영하지만, 최근 환경 변화를 포착하지 못할 수 있음.
- 따라서 3년 주간 수익률 기반 Raw Beta + 조정베타 확인 → 비교 후 보정값 사용 방식이 일반적이다.

​

실무에서는 대부분 베타는 Bloomberg를, MRP(Market Risk Premium)을 사용하는 경우가 많은데 Factor간 일관성이 저해되는 측면이 있다. 위에서 언급한 바와 같이 베타는 Bloomberg vs. KICPA 가 아니라 평가대상의 특성을 고려해서 결정할 문제이다.