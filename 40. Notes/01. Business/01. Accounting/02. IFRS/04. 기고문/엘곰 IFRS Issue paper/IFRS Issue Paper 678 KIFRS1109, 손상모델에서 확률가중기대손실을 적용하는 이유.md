---
title: "[IFRS Issue Paper 678] KIFRS1109, 손상모델에서 확률가중기대손실을 적용하는 이유"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250512113840453dr"
---
![](https://n2.news.naver.com/l.gif?type=content)**677**

**● 손상모델에서 확률가중기대손실(Probability Weighted Expected Loss)을 적용하는 이유**

**​**

**​**

사건의 발생은 발생확률(Possibility)과 크기(Gratitude)에 의해 분포를 만들어 낸다. 아래와 같이 시나리오가 A, B, C 3가지인 경우, 모든 상황을 고려한 확률가중평균치가 바로 IFRS9의 기대손실 개념이다. 여기서 가장 발생가능성이 높은 (50%) B를 결과로 선정할 수 없다.

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>시나리오</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>미래 실업율</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>발생확률</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>기대신용손실</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 43.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>A</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 43.0px;  "><div><p style=""><span style="">4%</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 43.0px;  "><div><p style=""><span style="">20%</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 43.0px;  "><div><p style=""><span style="">CU30</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 21.5px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>B</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 21.5px;  "><div><p style=""><span style="">5%</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 21.5px;  "><div><p style=""><span style="">50%</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 21.5px;  "><div><p style=""><span style="">CU70</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 21.5px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>C</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 21.5px;  "><div><p style=""><span style="">6%</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 21.5px;  "><div><p style=""><span style="">30%</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 21.5px;  "><div><p style=""><span style="">CU170</span></p></div></td></tr></tbody></table>

- 확률가중 기대신용손실 = 0.2×30+0.5×70+0.3×170=CU92​
- 단일 시나리오 사용 시 = 시나리오 (b) 사용 → ECL = CU 70

​

IFRS 금융상품 손상에 대한 전환자문그룹(IFRS Transition Resource Group for Impairment of Financial Instruments)은 가능한 손실의 분포가 종종 '비선형적(non-linear)'이라는 점, 즉 중심 예측(central forecast)보다 **더 나쁜 경제 시나리오와 관련된 손실 증가폭이 더 온화한 시나리오에서의 손실 감소폭보다 크다**는 점에 대해 우려를 표했다. 통계학 용어를 사용하면, 이러한 분포는 왜도(skewed)를 가진다. 산출 방식에 따라 단일 시나리오는 이 분포의 최빈값(mode)(즉, 가장 가능성이 높은 결과) 또는 중앙값(median)(즉, 중심 예측값)을 제공할 수 있다. 반면, **IFRS 9은 평균값(mean)(즉, 확률가중 추정)의 사용을 요구한다.**

**​**

![](https://scs-phinf.pstatic.net/MjAyNTA1MTJfODAg/MDAxNzQ3MDE3MDI1MzQ3.jc9nJDTSb_6KoEUHWqHDPVc0HkptkOeKN2_bSK112-cg.ZkSD7eqzn58qTKZLpzL_rRH1jFDLsgI9DSkWH7dMbbMg.PNG/image.png?type=w800)

출처 : International GAAP 2025, EY

**▶ 발생가능성과 발생금액간의 비대칭 문제**

**​**

**문제의 핵심은 단일 시나리오와 평균값의 차이**에 있다. 단일 시나리오(single scenario)는 가장 가능성이 높은 결과(= mode) 또는 가장 중앙에 있는 결과(= median)를 대표한다. 하지만 **경제 시나리오별 손실 분포는 대체로 대칭적이지 않고, 비대칭(skewed)인 경우가 많다.** 예를 들어 경제가 급격히 악화되는 경우 손실이 급증할 수 있지만, 상황이 개선되어도 손실 감소폭은 그리 크지 않는 경우이다. 통계 용어로 풀어보면 다음과 같다.

​

- Mode (최빈값): 가장 자주 발생하는 손실 수준.
- Median (중앙값): 손실 분포를 중간에서 나누는 값.
- Mean (평균값): 각 시나리오의 손실 예상치를 확률로 가중평균한 값.

​

**IFRS 9은 손실을 추정할 때 모든 가능한 시나리오의 손실을 확률 가중하여 평균(mean)을 산출해야 한다고 규정한다. 이는 손실 분포의 왜도(skewness)를 반영하기 위해서이다.**

**​**

**▶ 왜 평균(mean)을 사용해야 하는가?**

**​**

**IFRS 9에서는 신용손실을 "expected", 즉 예상되는 손실로 측정한다. 따라서 특정 시나리오 하나(중앙값/최빈값)를 기준으로 판단하는 것은 적절치 않다.** 평균값은 가장 온화한 시나리오부터 최악의 시나리오까지 모두 고려하여 기대손실을 측정하는 방식이다. 금융기관이나 기업이 신용손실을 측정할 때, 단일한 베이스라인 시나리오만 사용하는 것은 부적절하다. 반드시 복수의 시나리오(예: 기본, 낙관, 비관)를 구성하고, 각각의 확률과 손실 수준을 가중평균하여 ECL을 측정해야 한다. 이는 **손실분포의 비대칭성으로 인해, 단일 시나리오 기반의 ECL이 체계적으로 과소 혹은 과대평가될 수 있는 위험을 방지한다.**

**​**

**■ 복수의 경제 시나리오를 통합하는 데 사용할 수 있는 접근방법**

​

IFRS 금융상품 손상에 대한 전환자문그룹 회의에서, 복수의 경제 시나리오를 통합하는 데 사용할 수 있는 여러 가지 접근방법이 존재함이 언급되었다. IFRS 9는 기대신용손실을 측정하기 위한 특정 방법을 규정하지 않으며, 측정은 기업의 고유한 견해를 반영해야 한다. 그러나 IFRS 9는 다음과 같은 요구사항을 명시하고 있다.

​

• **가능한 다양한 결과를 사용하여 결정된 편향되지 않고(probability-weighted), 확률가중된 금액**

• 보고일 현재 이용가능하고, **과도한 비용이나 노력없이 확보가능한** 합리적이고 지원가능한 정보

​

합리적이고 지원가능한 정보와 관련하여, IFRS 전환자문그룹은 다음과 같은 견해를 제시하였다.

​

• IFRS 9가 외부정보의 고려를 명시적으로 요구하지는 않지만, **다양한 출처의 정보를 고려**함으로써 사용되는 정보가 합리적이고 지원가능한 것인지 확인해야 한다.

• 고려되는 정보는 기업의 정황에 따라 달라질 수 있으며, 예를 들어 기업의 복잡성 수준, 지리적 위치, 포트폴리오의 특성 등을 포함한다.

• 기업이 모든 가능한 시나리오를 고려할 필요는 없지만, 고려된 시나리오들은 가능한 결과들의 \*\*대표적 샘플(representative sample)을 반영해야 한다.

​

IFRS 전환자문그룹은 중요성(materiality) 고려가 필요함을 인식하였다.

<table style=""><tbody><tr><td colspan="4" rowspan="1" style="width: 100.0%; height: 32.25px;  background-color: #b0f1ff;"><div><p style=""><span style="">해설 (Explanation)</span></p></div><div><p style=""><span style="">​</span></p></div><div><p style=""><span style=""><b>1. 복수 시나리오를 반드시 정량적으로 모델링해야 하는가?</b></span></p></div><div><p style=""><span style=""><b>​</b></span></p></div><div><p style=""><span style="">아니오. IFRS 9는 구체적인 수량화 방법을 규정하지 않지만, </span><span style="">​</span><span style=""><b>확률가중 기대값(mean)을 구하기 위해 복수 시나리오를 '고려'할 것을 요구한다.</b></span><span style=""> 즉, 단일 시나리오만을 기계적으로 적용하는 것은 기준서의 취지와 맞지 않으며, 통계적으로 의미 있는 샘플링 또는 시나리오 가중평균 접근법이 필요하다.</span></p></div><div><p style=""><span style="">​</span></p></div><div><p style=""><span style=""><b>2. Reasonable and supportable information 요건</b></span></p></div><div><p style=""><span style="">​</span></p></div><div><p style=""><span style="">내부 정보(예: 내부 신용등급, 내부 PD모형) 뿐 아니라, 외부 정보(예: 정부 전망, 신용평가사 전망, 중앙은행 시나리오 등)도 종합적으로 고려해야 한다. 단, 이 정보는 '비용과 노력이 과도하지 않은 범위 내에서' 획득 가능한 것이어야 한다.</span></p></div><div><p style=""><span style="">​</span></p></div><div><p style=""><span style=""><b>3. 적절한 시나리오의 범위 및 수준</b></span></p></div><div><p style=""><span style=""><b>​</b></span></p></div><div><p style=""><span style="">모든 시나리오를 다 포함할 필요는 없으며, 대표성 있는 시나리오 셋(예: 낙관, 기준, 비관)만으로도 충분하다. 다만 이 셋이 결과의 왜도(skewness)나 tail risk를 반영할 수 있어야 한다.</span></p></div><div><p style=""><span style="">​</span></p></div><div><p style=""><span style=""><b>4. 중요성(materiality)의 고려</b></span></p></div><div><p style=""><span style=""><b>​</b></span></p></div><div><p style=""><span style="">일부 포트폴리오나 상품에 대해서는 시나리오 간 손실 차이가 미미할 수 있으며, 이 경우 정교한 분석이 요구되지 않을 수도 있다.</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 32.25px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">시나리오</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 32.25px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">손실 예상치(CU)</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 32.25px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">확률</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 32.25px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;">가중손실</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 32.25px;  background-color: #b0f1ff;"><div><p style=""><span style="">Baseline</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 32.25px;  background-color: #b0f1ff;"><div><p style=""><span style="">100</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 32.25px;  background-color: #b0f1ff;"><div><p style=""><span style="">60%</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 32.25px;  background-color: #b0f1ff;"><div><p style=""><span style="">60</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 16.13px;  background-color: #b0f1ff;"><div><p style=""><span style="">Downside</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 16.13px;  background-color: #b0f1ff;"><div><p style=""><span style="">250</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 16.13px;  background-color: #b0f1ff;"><div><p style=""><span style="">30%</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 16.13px;  background-color: #b0f1ff;"><div><p style=""><span style="">75</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 25.0%; height: 8.06px;  background-color: #b0f1ff;"><div><p style=""><span style="">Upside</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 8.06px;  background-color: #b0f1ff;"><div><p style=""><span style="">20</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 8.06px;  background-color: #b0f1ff;"><div><p style=""><span style="">10%</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 8.06px;  background-color: #b0f1ff;"><div><p style=""><span style="">2</span></p></div></td></tr><tr><td colspan="3" rowspan="1" style="width: 75.0%; height: 8.06px;  background-color: #b0f1ff;"><div><p style=""><span style="">Probability Weighted Average</span></p></div></td><td colspan="1" rowspan="1" style="width: 25.0%; height: 8.06px;  background-color: #b0f1ff;"><div><p style=""><span style="">137</span></p></div></td></tr></tbody></table>

이때 ECL은 137 CU (확률가중 평균)이다. 단일 중앙값 시나리오(100)만을 사용하면 위험을 과소평가 한다. 아래 그래프는 세 가지 경제 시나리오(낙관, 기준, 비관)에 따른 손실 예상치와 각 시나리오의 확률을 반영한 가중손실(ECL)을 시각화한 것이다.

​

- 연한 색 막대: 각 시나리오에서의 손실 예상치
- 짙은 색 막대: 각 시나리오의 확률을 반영한 가중 손실
- 보라색 점선: IFRS 9에 따라 산출된 전체 기대신용손실(ECL = 137 CU)

​

이는 단일 시나리오의 단순 손실(예: 100 CU)보다 ECL이 커질 수 있음을 보여주며, IFRS 9에서 복수 시나리오 고려와 확률가중(mean) 사용을 요구하는 이유를 명확히 시각화한다.

![](https://scs-phinf.pstatic.net/MjAyNTA1MTJfMTY0/MDAxNzQ3MDE2NjE5OTgy.tWRbnw3HXVoKFrUezBy33ArjxPfP2oimAfXDKqBM828g.GA20qfgCLuwNkRW5_eb0Vsg54RAAlgoQjTVbw9C_gMIg.PNG/image.png?type=w800)

**● View & Opinion**

**​**

**1\. 복수 시나리오 "고려" vs "적용"의 차이**

​

IFRS 9은 항상 복수 시나리오를 고려해야 한다고 요구하지만, 이를 반드시 수치적으로 계산하거나 모델링해야 한다고는 하지 않는다. 아래 3가지 요건을 충족하는 경우, 단일 시나리오 접근도 허용 가능하다.

​

- 비선형성의 효과가 중요하지 않음: 손실분포가 대칭적이거나, 낙관/비관 시나리오에서도 손실 차이가 작음.
- 복수 시나리오를 위한 근거가 부족함: 특히 비금융기업이나 소규모 포트폴리오 등에서 정량모형 미비.
- 과도한 비용/노력이 소요되는 경우: 모델 도입이 실질적 혜택보다 비용이 크면 생략 가능.

​

➡ 그러나 ‘실제 사용하지 않더라도 고려는 필수적’이다. 단순화된 모델을 사용하는 경우에도 해당 판단의 정당한 근거와 문서화(documentation)가 있어야 한다.

​

**2\. 미래예측정보의 조직 내 일관성**

**​**

내부 예산/사업계획/손익예측에 사용된 경제 전망과, 기대신용손실 계산에 사용된 전망이 다를 경우 문제 발

생한다. IFRS 9은 일관성을 요구하지는 않지만, 불일치가 있다면 그 차이를 설명할 수 있어야 한다고 요구한다. 예를 들어, 회계적으로는 보다 보수적 추정 사용하였다면 설명 가능해야 함

​

**3\. IFRS 7 공시요건의 중요성**

**​**

IFRS 7에서는 금융상품의 기대신용손실 측정 시 미래정보가 어떻게 반영되었는지, 어떤 판단(judgement)이 사용되었는지에 대한 공시를 요구하며, 구체적으로는 다음 내용이 필요하다.

​

- 사용된 시나리오 수, 내용, 확률
- 경제지표와 그 경로
- PD/LGD 추정에 반영된 외생적 변수
- 시나리오 간 손실 민감도 등

**​**

**4\. 요약**

<table style=""><tbody><tr><td colspan="1" rowspan="1" style="width: 26.47%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>항목</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 73.53%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>내용</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 26.47%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>복수 시나리오 고려</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 73.53%; height: 40.0px;  "><div><p style=""><span style="">항상 필요함, 단 </span><span style=""><b>반드시 정량모델로 계산할 필요는 없음</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 26.47%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>단일 시나리오 사용 허용 조건</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 73.53%; height: 40.0px;  "><div><p style=""><span style=""><b>비선형성 효과 없음, 합리적 근거 없음, 과도한 비용 발생</b></span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 26.47%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>미래정보 일관성</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 73.53%; height: 40.0px;  "><div><p style=""><span style=""><b>조직 내 예산/예측 정보와 일관성</b></span><span style=""><b>​</b></span><span style=""> 유지 필요 (불일치는 설명 가능해야 함)</span></p></div></td></tr><tr><td colspan="1" rowspan="1" style="width: 26.47%; height: 40.0px;  background-color: #003960;"><div><p style=""><span style="color:#ffffff;"><b>IFRS 7 공시요구</b></span></p></div></td><td colspan="1" rowspan="1" style="width: 73.53%; height: 40.0px;  "><div><p style=""><span style="">미래정보의 출처, 판단근거, 시나리오 구성 및 민감도 분석 </span><span style="">공시 필수</span></p></div></td></tr></tbody></table>

​

​