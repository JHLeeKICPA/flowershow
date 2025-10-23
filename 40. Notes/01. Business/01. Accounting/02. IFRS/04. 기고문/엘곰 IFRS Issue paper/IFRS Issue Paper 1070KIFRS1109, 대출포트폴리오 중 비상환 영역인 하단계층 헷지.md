---
title: "[IFRS Issue Paper 1070]KIFRS1109, 대출포트폴리오 중 비상환 영역인 하단계층 헷지"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250826201839563fl"
---
![](https://n2.news.naver.com/l.gif?type=content)**1070**

**● 대출포트폴리오 중 비상환 영역인 하단계층 헷지(Hedging a bottom layer (no prepayment risk) of a loan portfolio)**

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 89.0px;  background-color: #003960;"><div><p style="line-height:1.8;"><span style="color:#ffffff;">이 사례는 **"bottom layer 지정"**이라는 기법을 설명한다. 즉, 대출 포트폴리오에서 일부는 조기상환될 수 있지만, 반드시 남는 부분(bottom layer)은 헷지 대상으로 안전하게 잡을 수 있다는 것이다. IFRS 9은 이런 경우 허용하지만, 전액 조기상환 가능 포트폴리오는 아직 해결책이 없어 IAS 39 규정을 계속 적용하도록 하고 있다.</span></p></div></td></tr></tbody></table>

한 은행이 총 명목금액 CU100m의 고정금리 대출 포트폴리오를 보유하고 있다. 차입자들은 만기 중 언제든지 액면가로 (원래 대출금액의) **20%를 조기상환**할 수 있다.

​

리스크 관리 목적상, 대출은 CU100m의 변동금리 차입금과 함께 고려된다. 그 결과, 은행은 고정→변동 금리로 인한 마진 리스크에 노출된다. 은행은 **CU20m이 조기상환될 것으로 예상**한다.

​

리스크 관리 전략의 일환으로 은행은 일부 마진 위험을 헷지하기 위해 고정수취/변동지급 이자스왑(IRS)에 진입하기로 한다. 목적은 **상환 불가능(non-prepayable)한 대출 CU80m 중 95%를 커버하는 것이다(즉 CU76m).**

​

헷지 레이어에는 조기상환옵션이 포함되지 않는다. IRS는 총 대출포트폴리오 CU100m 중 하단 CU76m(bottom layer)에 대한 금리위험을 공정가치헤지로 지정한다.

![](https://scs-phinf.pstatic.net/MjAyNTA4MjZfNzQg/MDAxNzU2MjA2NzU0NTY3.I8iTA5uOzaJG06VyGOjB-SnOUr10F4_ir4WEpUZ-Nzkg.KjaCXjCSa9SvcdWvj2AUrhZmkGrfkEJLRKl1sijUWz4g.PNG/image.png?type=w800)

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 129.0px;  background-color: #bdfbfa;"><div><p style="line-height:1.8;"><span style="">위 그래프는 사례를 층(layer) 구조로 표현한 그림이다.</span></p><ul><li><p style="line-height:1.8;"><span style="">위쪽 빨간색 20m → 차입자가 언제든 조기상환할 수 있는 부분</span></p></li><li><p style="line-height:1.8;"><span style="">중간 파란색 4m → 상환불가능(non-prepayable)이지만 헷지대상에 포함되지 않은 부분</span></p></li><li><p style="line-height:1.8;"><span style="">아래 초록색 76m → 은행이 헷지대상으로 지정한 안정적인 bottom layer</span></p></li></ul><p style="line-height:1.8;"><span style="">즉, 은행은 전체 포트폴리오 중 맨 아래 76m은 반드시 남는다고 보고, 이 부분을 IRS로 공정가치헷지한다는 구조이다.</span></p></div></td></tr></tbody></table>

그 결과, 하단 레이어는 헷지된 위험(기준금리 위험)의 공정가치 변동만큼 조정된다. **차입자의 조기상환 옵션 행사(원래 대출금액의 최대 20%까지)는 헷지관계에 영향을 주지 않는다.** 또한 은행이 다른 이유로 대출을 제거해야 한다면, 먼저 상환 불가능한 CU40m이 제거된다. 그러나 명목금액이 CU76m 미만으로 떨어질 경우, 이는 헷지관계에 영향을 주기 시작한다.

​

따라서 IFRS 9은 상환 불가능한 bottom layer 포트폴리오에는 효과적인 솔루션을 제공하지만, 원금이 공정가치 이외의 금액으로 언제든지 상환될 수 있는 포트폴리오(예: 주택담보대출 포트폴리오)에 대해서는 답을 주지 못한다. 이러한 포트폴리오 헷지는 IASB의 별도 macro hedging 프로젝트에서 다루기로 하였으며, 그 전까지는 IAS 39의 포트폴리오 공정가치헷지 지침을 적용할 수 있다. \[IFRS 9.6.1.3\]

​

현재 IFRS 9에 유효한 회계 솔루션이 없기 때문에, 종종 기업은 대체 ‘proxy’ 헷지를 고려한다. 예를 들어, 특정 그룹 내 개별 항목을 헷지대상으로 지정하거나, 총액의 일정 비율을 지정할 수 있다. 그러나 이런 접근은 비효과성을 초래할 가능성이 높다. 특정 항목들이 조기상환된다면, 지정된 헷지 항목이 더 이상 존재하지 않게 되며, ‘비지정(non-designated)’ 항목만 남더라도 헷지금액을 채우지 못할 수 있다. 따라서 이런 경우는 비율지정 예시(illustration 2-12)로 설명하는 것이 적절하다.

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 129.0px;  background-color: #b0f1ff;"><div><p style="line-height:1.8;"><span style="">[보충설명]</span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style=""><b>1. 상황</b></span><span style=""><b>​</b></span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style="">은행은 CU100m 고정금리 대출을 가지고 있고, 고객은 언제든지 20%까지 조기상환 가능하다. 동시에 은행은 변동금리 차입도 CU100m 있어서, 고정 vs 변동 금리 차이(스프레드 위험)에 노출된다.</span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style=""><b>2. 리스크 관리 전략</b></span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style="">은행은 "어느 정도는 반드시 남을 것"이라고 예상되는 부분만 헷지 대상으로 삼는다. 예를 들어 CU100m 중에서 최대 CU20m은 조기상환될 수 있으므로, 남는 CU80m은 안전하다. 그 중 95%인 CU76m을 헷지 대상으로 정하고, 이 부분을 금리스왑으로 커버한다. 즉, "총 포트폴리오 중 맨 아래 76m은 반드시 남는다"라는 논리이다.</span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style=""><b>3. 회계적 효과</b></span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style="">공정가치변동은 헷지된 위험(금리위험)만 반영한다. </span><span style=""><b>차입자가 실제로 20%를 조기상환해도, 하단 CU76m은 영향을 받지 않으므로 헷지관계는 안정적이다.</b></span><span style=""> 다만, </span><span style=""><b>대출 명목금액이 CU76m 미만으로 떨어지면(즉, 예상보다 더 많이 상환되면) 헷지관계에 문제가 생긴다.</b></span></p></div><div><p style="line-height:1.8;"><span style=""><b>​</b></span></p></div><div><p style="line-height:1.8;"><span style=""><b>4. IFRS 9의 한계</b></span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style="">이런 "조기상환이 일부만 가능한 경우"는 IFRS 9에서 헷지가 가능하다. 그러나 "언제든지 전액 조기상환 가능한 포트폴리오"(예: 주택담보대출)에는 IFRS 9이 답을 주지 못한다. 그래서 IASB가 별도의 macro hedging 프로젝트에서 해결하려 하고, 그 전까지는 IAS 39 지침을 계속 적용할 수 있다.</span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style=""><b>5. 실무에서의 대체 접근(proxy hedge)</b></span></p></div><div><p style="line-height:1.8;"><span style="">​</span></p></div><div><p style="line-height:1.8;"><span style="">기업은 특정 개별 대출만 골라 헷지하거나, 전체 중 일정 비율을 헷지 대상으로 삼는 방식도 고려할 수 있다. 하지만 조기상환이 실제로 발생하면 지정된 항목이 사라질 수 있어서 비효과성(ineffectiveness) 위험이 크다.</span></p></div></td></tr></tbody></table>