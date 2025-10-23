---
title: "[IFRS Issue Paper 212] KIFRS1032, KIFRS1109, 이자율 상한(cap)/하한(floor) 조건의 내재파생분리여부"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/240905095817664lh"
---
![](https://n2.news.naver.com/l.gif?type=content)**212**

**● 이자율 상한(Cap)과 하한(Floor)의 의미**

​

변동이자율 조건의 채무상품 이라 하더라도 상한(cap)과 하한(floor)을 둚으로써 투자자가 과도한 이자율변동 리스크에서 보호받도록 하는 금융상품이 있다. 투자자는 과도하게 높거나 낮지 않은 적정수준의 시장이자율을 적용받는다. 예를 들어, 금리하락기에 시장이자율이 3%까지 하락한 시점에 이자율 하한을 4%로 설정했다면, 투자자는 1%만큼의 추가손실로부터 보호되는데 이를 내가격(in-the-money)상태라고 한다. 상호 약정하에 시장금리의 변동을 일정수준 제한하므로 옵션과 같은 레버리지 효과가 발생한다. 위 이자율 하한은 4%금리를 수령하고 3%금리와 교환하는 이자율스왑(interest swap)과 유사하다. 반면 금리상승기에 6%의 cap을 적용받는 경우 시장이자율이 7%가 되더라도 상한에 막히므로 발행자는 1%의 이익을 보게 되는데 이 역시 "Leverage"된 상황이다. 이처럼 시장금리의 변동성(volatility)이 큰 시기에 투자자와 발행자 모두 급격한 이자율 변동에서 보호받도록 이자율 적용 상하한을 정한 것을 "interest cap/floor"라고 한다.

​

이자율 Cap은 직관적으로 파생의 성격을 가지는 것으로 느껴진다. 파생상품의 정의를 다시한번 리마인드 하면,

​

① 기초변수 (Underlying Variable) : 이자율이 CAP을 초과하거나 Floor를 하회하는 경우 기초변수인 이자율의 변동에 따라 가치가 변동된다.

​

② 적은 순투자 : 이자율 변동의 효과를 보기 위해서는 채권(bond) 등을 발행하거나 매입해야 하지만 interest cap / floor 자체에 별도의 투자비용이 들지 않는다. 이는 주계약(host)에 내재되어 있기 때문이다.

​

③ 미래결재 : 이자율이 CAP을 초과하거나 Floor를 하회하는 경우, cap/floor 이자율을 적용받으므로 미래결제 되는 개념이다.

​

따라서 interest cap/floor는 파생상품이다. 또한 주계약의 이자율에 영향을 미치므로 내재파생이다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MDVfMzIg/MDAxNzI1NDk4MzkxMzEw.rc6TEnZOcKo25I8GDjkY6P8TX6k_thtooNv_9J8h830g.hQGdPljKCssQAvxJORhrQB179PruT-31dyUGQvy0lTQg.PNG/image.png?type=w800)

Source ; kaplan Financial Knowledge Bank

**● interest cap/floor의 분리여부**

**​**

내재파생이라면 항상 따라오는 이슈가 분리(bifurcation) 여부이다. KIFRS1109 B4.3.8(b)에서는 복합금융상품 발행시점의 이자율이 floor 이상, cap 이하라면 레버리지 되지 않았으므로 주계약과 밀접하게 관련되어 있다(close related)고 설명한다. 즉 하한과 상한 중간에 있는 경우 레버리지 되지 않았으므로 분리하지 않는다는 의미이다.

> 3.8.(b) 복합상품을 발행할 때 이자율 상한(cap)이 시장이자율 이상이고 이자율 하한(floor)이 시장이자율 이하이며, 이자율 상한이나 하한이 주계약에 관하여 레버리지되지 않았다면, 채무상품이나 보험계약에 내재된 금리캡이나 금리플로어는 주계약과 밀접하게 관련되어 있다.
> 
> ​
> 
> 마찬가지로, 일반상품과 같은 자산을 매입하거나 매도하는 계약에 포함된 조항으로서 그 자산에 대하여 지급하거나 수취할 가격에 대한 상한이나 하한이 설정된 경우에는 가격에 대한 캡이나 플로어가 계약시점에 외가격 상태이며 레버리지되지 않았다면, 가격에 대한 해당 캡이나 플로어는 주계약과 밀접하게 관련되어 있다.
> 
> KIFRS1109 B4.3.8(b)

**내재파생 분리여부의 판단기준은 다음 두가지이다.**

**​**

**① 경제적특성(economic characteristic)**

**② 동일한 위험에 노출(exposed to the same risk)**

**​**

KIFRS1109에서는 위 대원칙 하에 채무상품에 내재된 Put, Call의 분리여부에 대해서는 밀접한 관련성(closely related) 개념이 추가하고 있다. 구체적으로 채무의 상각후원가가 Put(투자자 상환권), Call(발행자 상환권)의 행사가액과 거의 일치(approximately equal)하는 경우 밀접하게 관련되어 있으므로 분리하지 않는다고 설명하고 있다. 위 조건은 결국 Put, cALL이 "Leverage"되지 않았다는 표현과 동일하다. 이는 Put, Call의 실질적 기능이 없다는 의미이다. 다시말해 put, call이 내재되지 않은 경우의 순수채권의 현금흐름과 유사하다는 뜻이다.

​

다른 조건은 Put, call 행사로 상실하게 되는 이자차액을 보상하는 조건이 부여된 경우 역시 밀접한 관련성이 있는 경우로 설명하고 있다. 투자자 관점에서는 이자율이 상승하여 채권가격이 하락하는 경우 상환권을 행사한 후 시장에서 동일한 채권을 재매입하면 상환가액과 채권의 공정가액의 차이만큼 차액을 실현할 수 있게 되는데, 그 차이를 발행자가 보상(reimburse)해 준다면 상환권 행사 유인이 사라질 것이다. 이 역시 put, call이 제 기능을 발휘하지 못하는 경우가 되므로 주계약과 밀접하게 관련되어 분리할 필요가 없다.

​

위 put, call의 밀접한 관련성은 interest cap/floor에도 똑같이 적용된다. 시장이자율이 floor와 cap의 범위 내에 있는 상황에서 발행되었다면 발행시점에 cap/floor derivative가 식별되지 않는 상황이다. 따라서 밀접하게 관련되어 있지 않으므로 분리하지 않는다. 반면, 드물지만, 발행시점의 시장이자율이 floor보다 낮거나 cap보다 높은 경우에는 발행즉시 차익이 식별되는 경우이므로 밀접하게 관련되어 있지 않다고 판단하고 분리한다.

**​**

**● IFRIC(IASB 해석위원회)의 검토결론**

​

IASB 해석위원회는 변동금리(floating rate) 조건의 주계약에 붙어 있는 이자율 상한(cap)/하한(floor) 내재파생의 분리여부에 대한 질문의 받고 검토한 결과 다음과 같은 판단을 하였다.

​

① 시장이자율과 cap/floor를 비교할 때 전체 이자율 개념(overall interest rate floor, 즉 기본이자율(LIBOR와 같은 benchmark interest)과 가산이자율(spread), 기타 premium, discount등 유효이자율에 적용된 모든 이자율 합)을 하한(floor)이 없는 일반채권이자율과 비교해야 한다.

​

*when applying paragraph AG33(b) of IAS 39, in a positive or negative interest rate environment, an entity should compare the overall interest rate floor (ie the benchmark interest rate referenced in the contract plus contractual spreads and if applicable any premiums, discounts or other elements that would be relevant to the calculation of the effective interest rate) for the hybrid contract to the market rate of interest for a similar contract without the interest rate floor (ie the host contract);*

​

② "시장이자율(market rate of interest)이라는 용어는 IFRS13에서 정의된 공정가치와 유사한 의미로 유사한 구조와 신용등급을 가진 금융상품에 대한 이자율이다

​

*the term ‘market rate of interest’ is linked to the concept of fair value as defined in IFRS 13 Fair Value Measurement and is described in paragraph AG64 of IAS 39 as the rate of interest ‘for a similar instrument (similar as to currency, term, type of interest rate and other factors) with a similar credit rating*

​

\* IFRIC Update, From the IFRS Interpretations Committee(january 2016)

​

이자율 스왑(interest SWAP) 시장은 시장금리에 대한 예측이 다른 사람들간의 이자율 교환거래이다. 고정금리부 채권을 보유하고 있는 투자자 중 금리상승을 기대하는 사람은 금리하락을 예측하는 변동금리부 채권을 보유하고 있는 사람과 고정금리를 주고 변동금리를 받는 이자율교환거래이므로 floor/cap을 가진 채권거래 시장도 이러한 이자율 스왑 시장과 성격이 유사하다.

​

**● 측정단위(Unit of Account)**

**​**

시장이자율과 Cap / Floor와의 비교테스트시 일련의 cap과 floor를 각각 별개의 파생상품으로 보는 법과 cap과 floor를 하나의 금융상품으로 보는 법 2가지 중 한 방법을 선택하여 일관되게 적용할 수 있다는 것이 global firm의 view이다. 만약, cap과 floor를 묶어서 하나의 금융상품으로 보는 경우에는 각 cap 또는 floor가 비교되어야 할 시장이자율(market rate of interest)은 Swap rate에 신용프리미엄(credit spreads)을 가산한 이자율이다. 만약 Swap rate(예를 들어 특정시장에 의해 결정된 변동 benchmark 이자율과 교환되는 현행 고정 스왑이자율이 사용된다면, 해당 이자율의 기간(period)은 cap과 floor의 기간과 동일해야 하는데 이는 IFRS9에서 시장이자율과 관련된 Guidance에서 유사한 조건의 유사한 금융상품의 이자율을 고려할 것을 요구하기 때문이다. 따라서 첫번째 이자율 재설정 시점의 현물이자율(spot rate for the first reset period)을 cap / floor의 전체기간의 대용치로 사용되는 것은 적합하지 않다.

​

만약, 기업이 내재된 cap/floor가 주계약과 밀접하게 관련되어 있지 않다고 판단했다면 cap 또는 floor 각각이 아닌 "전체 cap / floor"가 주계약에서 분리되어야 한다. 이것이 회계단위별 측정 개념(unit of account assessment)에 부합한다.

​

만약 cap/floor 비교를 위한 측정단위(unit of account)가 cap과 floor 각각 분리된다면 시장이자율은 특정 cap 또는 floor의 기간에 상응하는 선도이자율(forward rate)에 신용리스크 등 기타프리미엄을 가산한 이자율이 되어야 한다. 만약 (꼭 둘다가 아니어도) cap 또는 floor가 주계약과 밀접하게 관련되어 있지 않다고 판단된 경우 cap 또는 floor 중 하나를 독립적으로 분리하는 것이 아니라 cap / floor를 모두를 주계약에서 분리해야 한다. 이것이 복수의 내재파생(multiple embedded derivatives)에 대한 지침과 일관성이 있다.

​

**● Global IFRS article reference**

​

interest cap/floor derivative의 분리여부 판단시 주의할 사항은 판단시점(Timing)이다. 시장이자율과 cap/floor를 비교하는 시점은 계약시점, 즉 발행시점이다. 그리고 계약의 변경이 있지 않는 한, 주계약인 채권의 만기까지 변동(재비교)하지 않는다. 그렇지 않는다면 지속적으로 분리, 미분리가 반복되는 상황이 발생할 수도 있기 때문이다. 시장이자율은 보통 Swarp 이자율을 사용한다. Swap이자율은 미래 이자율 변동에 대한 예상이 다른 거래당사자간의 이자율 교환거래이므로 interest cap/floor가 내재된 복합금융상품의 이자율과 개념상 유사하기 때문이다. 다른 방법으로는 선도이자율(forward interest rate)를 사용하기도 한다.

![](https://scs-phinf.pstatic.net/MjAyNDA5MDVfNDcg/MDAxNzI1NDk3MTA5MzI1.UKHDHENshUnLjFuD8K9jcLUCiowcp1B2JsWF3BKEJwQg.EjBSzQLsavqTCd9D3DsENI7GQ7KJI5k8yhw7auPwnjsg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MDVfMTYw/MDAxNzI1NDk3MjkzMjg4.a3JvyV0aIIvxeL8IYzDmwre8tbo6FHrpWxTmB9lUqZ8g.bbJ14bj1jNYk4gHXqQlDiDpS-SZG549ILvsKeK4hC3Ag.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MDVfMTUg/MDAxNzI1NDk3MzU2NzA3.8DlW1pC40VYRzt4w0xPIX4iZCok2RPwQ35_7u4Lgy7og.mpZR1BxjUfnc_aUVavg3ZCcKA-kdiukmSPy7MUfpnoQg.PNG/image.png?type=w800)

![](https://scs-phinf.pstatic.net/MjAyNDA5MDVfODQg/MDAxNzI1NDk3NDM2ODAy.hBznGwZQovzxm0bfY490yQLx2wIgfSh9blzUv-PnS1Yg.t8YxFpz-uJ_WCBpcsrXBrkXwtY6OT3cTDieTzH2OXvog.PNG/image.png?type=w800)

[![](https://dthumb-phinf.pstatic.net/dthumb?src=%22https://storep-phinf.pstatic.net/cafe_004/original_28.png?type=p100_100%22&service=scs&type=w800)](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/#)

​