---
title: "[IFRS Issue Paper 731] KIFRS1113,1102 옵션가치 평가에서 변동성(Volatility)의 영향"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250523071540118wy"
---
![](https://n2.news.naver.com/l.gif?type=content)**731**

**● 옵션가치 평가모델 변수 : 변동성 (Expected future volatility)**

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 129.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">금번 Issue Paper는 기초주식의 예상 미래 변동성(Expected future volatility of the underlying share price)"의 추정방법과 변동성이 옵션가치에 미치는 영향에 대한 내용을 다룬다. 변동성(volatility)은 공정가치 옵션 평가모형(예: Black-Scholes)**에서 필수적으로 요구되는 입력값 중 하나로 옵션가치에 중대한 영향을 주는 요소 중 하나이다. 변동성은 투자 수익률의 분포 범위를 나타내며, 변동성이 0이면 수익률은 무위험 투자와 동일하다는 의미이며 변동성이 높을수록, 투자 수익률의 변동 가능성이 커지고, 이는 옵션의 가치가 증가한다.</span></p></div></td></tr></tbody></table>

**■ 스톡옵션 평가를 위한 Black-Scholes 모형 입력값 정리**

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 21.72%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">요소</span></p></div></td><td colspan="1" rowspan="1" style="width: 30.1%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">의미</span></p></div></td><td colspan="1" rowspan="1" style="width: 48.18%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">실무 적용 방식 (비상장 스타트업 기준)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 21.72%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">S (주식의 현재가치)</span></p></div></td><td colspan="1" rowspan="1" style="width: 30.1%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">기초자산 현재 가격</span></p></div></td><td colspan="1" rowspan="1" style="width: 48.18%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">최근 투자유치 시 기업가치를 기준으로 보통주 가치 환산</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 21.72%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">K (행사가격)</span></p></div></td><td colspan="1" rowspan="1" style="width: 30.1%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">옵션의 행사 가격</span></p></div></td><td colspan="1" rowspan="1" style="width: 48.18%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">부여계약서에 명시된 strike price</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 21.72%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">T (만기)</span></p></div></td><td colspan="1" rowspan="1" style="width: 30.1%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">옵션의 잔존기간(연 단위)</span></p></div></td><td colspan="1" rowspan="1" style="width: 48.18%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">가령 3년 베스팅 + 7년 행사 가능 시, 총 10년 적용</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 21.72%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">σ (변동성)</span></p></div></td><td colspan="1" rowspan="1" style="width: 30.1%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">연율화 기대 주가 변동성</span></p></div></td><td colspan="1" rowspan="1" style="width: 48.18%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">유사 상장기업 평균 3~5년 연율 변동성 사용</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 21.72%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">r (무위험이자율)</span></p></div></td><td colspan="1" rowspan="1" style="width: 30.1%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">무위험 할인율</span></p></div></td><td colspan="1" rowspan="1" style="width: 48.18%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">국채 수익률 등 사용 (예: KTB 3~5년 만기 수익률)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 21.72%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">q (배당수익률)</span></p></div></td><td colspan="1" rowspan="1" style="width: 30.1%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">연간 배당수익률</span></p></div></td><td colspan="1" rowspan="1" style="width: 48.18%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">대부분 0% (스타트업은 무배당 전제)</span></p></div></td></tr></tbody></table>

**■ Expected Volatility (σ) 추정 실무 프로세스 : 비상장 바이오 스타트업 (배당 없음, 설립 3년 차)**

​

**▶ 1단계: 유사 상장기업 식별**

​

다음 사항을 고려하여 동일 산업군 (예: 항암치료제 개발사) 중 상장된 국내외 기업 선정한다.

​

- 사업모델 (R&D 중심 vs. 매출 발생 기업)
- 기업 규모 (시가총액 또는 매출 기준)
- 상장 연한 (IPO 직후 초기 기업일수록 유사)

​

**▶ 2단계: 해당 기업들의 연율화 변동성 추출**

​

Bloomberg, Refinitiv, Yahoo Finance 등에서 과거 3년간 월별 종가 기준으로 연율화 변동성 계산한다.

​

- 연율화 방식: 표준편차 × √12
- 실무상 주요 기준 기업 예:

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">유사기업</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">최근 3년 연율화 변동성 (%)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">A바이오텍 (KOSDAQ)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">55.1</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">BPharma (NASDAQ)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">64.3</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">C바이오사이언스</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">59.7</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">D신약연구소</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">48.5</span></p></div></td></tr></tbody></table>

**▶ 3단계: 평균 또는 가중평균 산정**

​

- 단순 평균: (55.1 + 64.3 + 59.7 + 48.5) / 4 = 56.9%
- 또는, R&D 단계/시가총액 유사성 가중평균

​

**▶ 4단계: 시장요인 보정**

​

만약 최근 몇 개월간 해당 섹터 전반의 이례적 변동성(예: 팬데믹, 정책변화 등)이 존재했다면, 해당 기간 제외 또는 보정, 변동성 평균회귀 성향 고려하여 보수적 접근 시 5~10% 하향 조정 가능

​

**▶ 최종 적용 변동성**

​

적용 Expected Volatility: 55% (유사기업 평균 기준, 신약개발 전단계 기준)

​

실무 응용 예시 (Black-Scholes 계산 요약)

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">항목</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">수치</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">S (주식가치)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">10,000원</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">K (행사가)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">10,000원</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">T (만기)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">10년</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">σ (변동성)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">55%</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">r (무위험이율)</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">3.5%</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">배당수익률</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">0%</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">결과</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">Option FV ≈ 6803.44 (Black-Scholes 결과)</span></p></div></td></tr></tbody></table>

![](https://scs-phinf.pstatic.net/MjAyNTA1MjNfMjcw/MDAxNzQ3OTQ5NTYzODQ5.ArTuTuMqnhURlrQ_yVIrFD6E6Q_rZIoSUm9R1zF-bJYg.Xt92OI4buPD7SJGq2mGaEPcukxS6JS59XVLpch_TB_Mg.PNG/image.png?type=w800)

■ 예상변동성 산출방법

![](https://scs-phinf.pstatic.net/MjAyNTA1MjNfNTUg/MDAxNzQ3OTQ5Njg1MTUy.q9LXabtoRzDEPY2nBY_HGUdc5fzcz17ongh2EbM-wdog.yClcytbbmKbE6TkrtSDw_u2aG-c8AK5SWPiKNsCw13Yg.PNG/image.png?type=w800)

**​**

**■ 상장기업의 경우: 실무 절차**

​

**▶ Step 1: 주가 데이터 수집**

- 예: 최근 3년간 월별 종가
- 데이터 출처: Bloomberg, Yahoo Finance, Investing.com 등

​

**▶ Step 2: 수익률 계산**

- 수익률: ln(Pt−1​Pt​​) (로그수익률)

​

**▶ Step 3: 로그수익률의 표준편차 계산**

- 예: 36개월치 수익률의 표준편차 = σₘₒₙₜₕₗᵧ

​

**▶ Step 4: 연율화**

![](https://scs-phinf.pstatic.net/MjAyNTA1MjNfMjQx/MDAxNzQ3OTQ5ODQ2Mjg1.ZfESo7wS6MqKlH8KLLQ6P8xxSP4RrIJ3_Eh1GipUDm8g.RkvWoqkFe_tR3jGOpn2r07RGLGyoKAhZMwvTozuEmXYg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNTA1MjNfMjEz/MDAxNzQ3OTUwMTAwNDg1.DknK6Av3p3xcuK2N2KYheCPQsFQomj_ETOkLNp4yjZcg.LMP9PhyTzIqRnGnnuXYPLDg8d2IoI2JGZtTCrPHRIeIg.PNG/image.png?type=w800)

**■ 변동성 (Expected future volatility)의 속성**

**​**

**▶ 옵션 가치 평가에 있어 변동성(Volatility)이 왜 옵션 가치에 ‘정(+)의 영향’을 주는가?**

​

**① 옵션의 비대칭적 구조 (Asymmetry)**

​

**콜옵션(Call Option)의 구조: 콜옵션 보유자는 상승 시 무한한 이익 가능성, 하락 시 손실은 행사가까지만 제한된다. 다시 말해, 손실은 제한되고, 이익은 무한대인 구조이다.**

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">구간</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">보유자의 손익</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">주가 &lt; 행사가</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">0 (옵션 포기)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">주가 &gt; 행사가</span></p></div></td><td colspan="1" rowspan="1" style="width: 50.0%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">주가 – 행사가</span></p></div></td></tr></tbody></table>

이러한 구조 때문에 변동성이 클수록 손실은 여전히 0으로 제한되지만, 이익이 발생할 가능성과 크기가 커지기 때문에 옵션의 기대가치가 상승한다.

**​**

**② 확률분포의 이해: 로그정규분포와 ‘꼬리확률’**

​

> **옵션 평가모형(Black-Scholes 등)은 기초자산의 수익률이 정규분포를 따르고 기초자산의 가격은 따라서 로그정규분포를 따른다.**

**③ 변동성이 커지면?**

​

- **분포의 양쪽 꼬리(tail)가 더 두꺼워진다 → 극단적인 주가 변화 확률이 증가,**
- **특히 콜옵션의 경우, 우측 꼬리가 두꺼워지면, 주가가 크게 상승할 확률이 커짐 → 옵션 가치 상승**

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 86.0px;  background-color: #bdfbfa;"><div><p style="line-height:2.1;"><span style="">예를 들어, 현재 주가가 100이고 행사가가 100인 콜옵션이 있을 때:</span></p><ul><li><p style="line-height:2.1;"><span style="">변동성이 10%이면, 연말에 130까지 갈 확률은 매우 낮다.</span></p></li><li><p style="line-height:2.1;"><span style="">변동성이 50%이면, 연말에 130 또는 그 이상이 될 확률이 상당히 존재 → 옵션의 기대 수익 증가"</span></p></li></ul></div></td></tr></tbody></table>

**④ 반대 사례: 변동성이 줄어들면?**

**​**

- 기대되는 큰 이익 가능성이 줄어들어, 옵션 가치는 하락
- 특히 OTM(행사가격보다 낮거나 높은) 옵션의 경우, 변동성 감소는 옵션 가치를 거의 0으로 만들 수 있음

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 23.53%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">항목</span></p></div></td><td colspan="1" rowspan="1" style="width: 76.47%; height: 40.0px;  background-color: #003960;"><div><p style="line-height:2.1;"><span style="color:#ffffff;">영향</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 23.53%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">변동성 증가</span></p></div></td><td colspan="1" rowspan="1" style="width: 76.47%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">주가가 크게 상승할 확률 증가 → 옵션 가치 증가</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 23.53%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">변동성 감소</span></p></div></td><td colspan="1" rowspan="1" style="width: 76.47%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">주가가 행사가에 머무를 가능성 ↑ → 옵션 가치 감소</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 23.53%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">옵션구조</span></p></div></td><td colspan="1" rowspan="1" style="width: 76.47%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">손실은 제한, 이익은 무한대 → 비대칭 구조</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 23.53%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">베가(Vega)</span></p></div></td><td colspan="1" rowspan="1" style="width: 76.47%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">항상 양(+) → 변동성이 클수록 옵션 가치 ↑</span></p></div></td></tr></tbody></table>

**▶ 변동성(Volatility)이 옵션가치에 미치는 영향에 대해 좀 더 쉽게 설명해 보자**

**​**

**1\. 옵션은 ‘복권’과 비슷한 성격을 가진다**

​

- 콜옵션은 주가가 특정 가격(행사가격)을 넘기면 이익이 발생하고, 못 넘기면 손실은 제한된다.
- 예를 들어, 행사가격이 10,000원인 콜옵션을 보유하고 있을 때:
- 주가가 9,000원이라면? ➝ 포기하면 그만, 손실은 0원
- 주가가 15,000원이면? ➝ 무려 5,000원의 이익
- 즉, 잃을 건 없고, 따면 크게 딸 수 있는 구조이다.

​

**2\. 변동성이 커지면 ‘대박’ 확률이 커진다**

​

- 변동성이 작을 때: 주가는 대체로 10,000원 근처에서 오르락내리락, 옵션이 돈을 벌 가능성은 작다
- 변동성이 클 때: 주가는 8,000~15,000원처럼 큰 폭으로 요동, 옵션이 큰 이익을 낼 수 있는 확률이 올라간다
- 기대수익이 커지니까, 옵션 가격(가치)이 당연히 더 비싸게 평가된다.

​

**3\. 수익구조는 ‘위는 뚫려 있고, 아래는 막힌’ 구조**

​

- 주가가 많이 올라가면: 옵션 수익은 무한대로 증가 가능
- 주가가 떨어지면: 옵션 수익은 그냥 0원이 최대 손실
- 이런 구조를 ‘비대칭적 수익 구조’라고 부른다.

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 61.0px;  background-color: #bdfbfa;"><div><p style="line-height:2.1;"><span style="">비유로 이해해 보면, 콜옵션은 비 오는 날을 대비해 사 놓는 우산 보험 같은 것으로, 평소엔 필요 없지만, 큰 폭우(=큰 주가 상승)가 오면 큰 도움이 된다. 폭우가 자주 온다(=변동성이 크다)면 보험료(=옵션 가격)는 비싸지는 게 당연하다.</span></p></div><div><p style="line-height:2.1;"><span style="">​</span></p></div><div><p style="line-height:2.1;"><span style="">요약하면, "위로는 무한히 벌 수 있고, 밑으로는 0으로 막힌 구조이기 때문에 변동성이 클수록 콜옵션의 기대이익이 커지고, 따라서 공정가치도 높아진다"는 것이 핵심이다.</span></p></div></td></tr></tbody></table>

**▶ 옵션 평가모형(Black-Scholes 등)은 기초자산의 수익률이 정규분포를 따른다고 가정하고, 기초자산의 가격은 따라서 로그정규분포를 따르게 된다는 의미는 무엇인가?**

**​**

**1\. 정규분포란 무엇인가?**

​

- 정규분포는 우리가 익숙한 ‘종 모양’ 곡선
- 예: 시험 점수, 키, 몸무게 같은 것들이 대체로 정규분포를 따른다
- 평균 근처에 사람들이 많고, 양쪽 끝(아주 높은 점수, 아주 낮은 점수)은 드물다
- 예를 들어 100점을 만점으로 하는 시험에서 대부분이 60~80점 사이에 있고, 0점이나 100점은 아주 드물다

→ 이것이 바로 정규분포

​

**2\. 옵션모형에서 "수익률"은 정규분포를 따른다고 가정함**

​

- 주식의 수익률이란?

![](https://scs-phinf.pstatic.net/MjAyNTA1MjNfMTA4/MDAxNzQ3OTUwNzA1OTQ5.Lr7kY0mjG8RW9-y6YVJ6RAqS1F4prliRZOUr8rPN4TQg._wq1AwS2-945cSySSsbbmMj4c_wY8IaD7URMswsh9bAg.PNG/image.png?type=w800)

​

- Black-Scholes 모형은 이 ‘수익률’이 평균을 중심으로 좌우 대칭의 정규분포를 따른다고 가정한다.
- 즉, 큰 상승도 드물고, 큰 하락도 드물고, 대부분은 평균 근처의 수익률을 보인다.

​

**3\. 그런데 우리는 ‘주가 자체’를 보고 싶다 → ‘로그정규분포’ 등장**

​

- 우리가 알고자 하는 것은 수익율의 변동성이 아니라 주가의 변동성이다.
- 수익률이 정규분포를 따른다면, 주가는 어떻게 분포할까?
- 주가는 수익률을 누적해서 곱해나가는 값이다. 예를 들어,

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">일자</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">수익률</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">주가</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">1일차</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">+5%</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">100 × 1.05 = 105</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 33.33%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">2일차</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">–2%</span></p></div></td><td colspan="1" rowspan="1" style="width: 33.33%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">105 × 0.98 = 102.9</span></p></div></td></tr></tbody></table>

이런 식으로 수익률을 계속 곱해서 계산하니, 주가의 분포는 곱셈 구조이고, 이 결과, **주가는 정규분포가 아니라 로그정규분포(log-normal distribution)를 따르게 된다.**

**​**

**4\. 로그정규분포란?**

​

- 0 이하로는 절대 갈 수 없고 (주가는 음수가 될 수 없음)
- 오른쪽으로 꼬리가 길게 뻗은 비대칭 분포
- 현실의 주가 특성과 비슷함: 급락보다는 급등이 더 크게 벌어질 가능성이 존재

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 15.84%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">항목</span></p></div></td><td colspan="1" rowspan="1" style="width: 21.28%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">분포 가정</span></p></div></td><td colspan="1" rowspan="1" style="width: 62.88%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">이유</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 15.84%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">수익률</span></p></div></td><td colspan="1" rowspan="1" style="width: 21.28%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">정규분포</span></p></div></td><td colspan="1" rowspan="1" style="width: 62.88%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">평균 중심 대칭적인 변동 가정</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 15.84%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">주가</span></p></div></td><td colspan="1" rowspan="1" style="width: 21.28%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">로그정규분포</span></p></div></td><td colspan="1" rowspan="1" style="width: 62.88%; height: 40.0px;  "><div><p style="line-height:2.1;"><span style="">수익률을 곱해 누적 → 곱셈구조 → 음수 불가</span></p></div></td></tr></tbody></table>

**5\. 수익률이 정규분포를 따른다고 가정할 때의 주가 시뮬레이션 예시 그래프**

​

아래 그래프는 수익률이 정규분포를 따른다는 가정 하에 시뮬레이션한 주가 경로들이다. 초기 주가 10,000원에서 출발하며, **시간이 갈수록 경로가 우측으로 점점 퍼지고(=비대칭) 일부 경로는 크게 상승하는 특성이 보인다.**

이것이 바로 주가가 로그정규분포를 따른다는 개념의 시각적 표현이다. 즉, 하방은 제한되나, 상방은 무한히 열려 있는 옵션 구조와도 잘 부합하는 분포 형태이다.

![](https://scs-phinf.pstatic.net/MjAyNTA1MjNfMTc2/MDAxNzQ3OTUwOTM4NzEz.QM8o3oofY8f63VaIMYYh7a72D8MHVr9ZL75TNM0H03og.ThDr_TuM9vsC3C7jiNtChtcBMS_L_8Hx1yZf9WTubXog.PNG/image.png?type=w800)

아래 그래프는 콜옵션 가치가 왜 변동성이 커질수록 증가하는지를 ‘우측 꼬리 확률’ 관점에서 시각화한 것이다.

- 파란 선: 변동성 낮음 (σ = 0.5)
- 빨간 선: 변동성 높음 (σ = 1.0)
- 검은 점선: 행사가격을 넘는 구간 (옵션이 이익이 되는 영역)

![](https://scs-phinf.pstatic.net/MjAyNTA1MjNfMTE2/MDAxNzQ3OTUxMDEwMTQw.mip8cxw5G7scEyp084DMX6Bz5k4hZQFIT1owQSGXn8kg.uQEY0FThRtT2htAqWwvVtjlcLBls4ym_XTp7oOknm-kg.PNG/image.png?type=w800)

- **두 분포 모두 평균은 같지만, 변동성이 클수록 꼬리 부분이 더 두껍고 넓다.**
- **따라서 주가가 크게 상승하는 경우(=행사가격 초과)의 확률이 훨씬 커짐.**
- **이 확률의 차이가 곧 콜옵션의 기대이익 증가 → 가치 상승으로 이어진다.**

**​**

**● View & Company**

**​**

주가수익율은 완만하고 양 끝단이 두툼한 형태의 분포를 보인다. 이러한 특성은 변동성이 옵션가치(ex : 전환권, 주식매입선택권)에 중대한 영향을 미치는 원인이 된다. 변동성을 이해하는 핵심은 주가수익율의 변동성은 정규분포를, 주가의 변동성은 로그분포를 띈다는 사실이다. 따라서 daily, weekly, mothly 등 각 구간별 주가수익율의 로그함수값의 표준편차값의 연율값이 변동성이 된다.

​

이러한 변동성 산출방법은 자기자본비용에 적용할 베타값에도 적용된다. 베타는 주식의 수익율과 시장포트폴리오(KOSPI200)와의 공분산을 시장수익율의 분산으로 나눈 값이다. 여기서 표준편차는 분산의 제곱근이다.