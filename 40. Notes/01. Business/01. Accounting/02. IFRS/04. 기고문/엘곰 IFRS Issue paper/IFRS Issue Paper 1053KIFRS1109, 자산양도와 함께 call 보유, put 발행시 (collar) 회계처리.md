---
title: "[IFRS Issue Paper 1053]KIFRS1109, 자산양도와 함께 call 보유, put 발행시 (collar) 회계처리"
acounting_standard: "IFRS"
document_type: "기고문"
source: "엘곰"
url: "https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250822110225030lv"
---
![](https://n2.news.naver.com/l.gif?type=content)**1053**

**● 자산양도와 함께 call 보유, put 발행시 (collar) 회계처리**

**​**

자산은 수취인이 해당 자산에서 과도한 손실을 입지 않도록 보장하는 동시에, 자산에서 발생하는 상당한 이익은 양도인에게 다시 귀속되도록 설계된 방식으로 양도될 수 있다. 이러한 계약은 ‘콜라(collar)’라고 불리는데, 이는 자산 가치 변동의 일정 구간은 수취인에게 배분하고, 그 범위를 벗어난 변동은 양도인에게 귀속시키는 구조이기 때문이다. 간단한 예는 매수청구권(call option)을 매입하여(자산 가치가 일정 수준을 초과하면 양도인이 자산을 재매입할 수 있도록 함), 동시에 매도청구권(put option)을 발행하여(자산 가치가 일정 수준 이하로 하락하면 수취인이 양도인에게 자산 재매입을 강제할 수 있도록 함) 자산을 양도하는 경우이다.

​

콜라(collar)가 매수청구권과 매도청구권의 형태로 존재하여 공정가치로 측정되는 양도자산의 제거를 방해하는 경우, IFRS 9은 기업이 **자산을 계속 공정가치로 측정**할 것을 요구한다. 관련된 부채는 다음과 같이 측정된다.

​

- 콜옵션이 내가격(in the money) 또는 등가격(at the money)인 경우: 콜옵션 **행사가격**과 풋옵션의 공정가치를 합한 금액에서 콜옵션의 시간가치를 차감한 금액
- 콜옵션이 외가격(out of the money)인 경우: 자산의 **공정가치**와 풋옵션의 공정가치를 합한 금액에서 콜옵션의 시간가치를 차감한 금액

​

이러한 관련 부채의 조정은, 자산과 관련 부채의 순장부금액이 기업이 보유 및 발행한 옵션의 공정가치와 일치하도록 보장한다.\[IFRS 9.B3.2.13(e)\]

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 129.0px;  background-color: #b0f1ff;"><div><p style="line-height:1.8;"><span style=""><b>■ Collar 구조의 본질</b></span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">콜라(collar) 구조에서는 양도인이 자산에 대해 두 가지 옵션을 동시에 설정한다:</span></p><p style="line-height:1.8;"><span style="">​</span></p><ul><li><p style="line-height:1.8;"><span style="">수취인에 대한 written put (양도인이 put 매도) : 자산 가치가 일정 수준 밑으로 떨어지면, 수취인이 자산을 양도인에게 되팔 수 있다.</span></p></li><li><p style="line-height:1.8;"><span style="">양도인에 대한 purchased call (양도인이 call 매수) : 자산 가치가 일정 수준 이상 올라가면, 양도인이 자산을 다시 되살 수 있다.</span></p></li></ul><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">즉, 수취인은 자산의 가치가 특정 범위 안에 있을 때만 경제적 이익을 누리고, 그 범위를 벗어나면 양도인에게 위험(put)이나 이익(call)을 되돌려준다.</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style=""><b>■ 회계 논리: 자산과 부채의 분해</b></span></p><p style="line-height:1.8;"><span style="">​</span></p><ul><li><p style="line-height:1.8;"><span style="">자산은 계속 </span><span style="">공정가치(FV)</span><span style=""> 로 측정된다.</span></p></li><li><p style="line-height:1.8;"><span style="">부채는 옵션 계약의 경제적 가치(수취인에게 부여된 put + 양도인이 가진 call로 인한 제한)를 반영해야 한다.</span></p></li></ul><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">즉, IFRS 9은 부채를 “행사가격과 옵션의 가치들”로 표현함으로써 </span><span style=""><b>자산과 부채의 순장부금액이 콜라에서 발행·보유한 옵션의 공정가치와 일치</b></span><span style="">하도록 강제한다.</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style=""><b>■ 왜 “콜 행사가격 + 풋 가치 – 콜 시간가치” 인가?</b></span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">콜옵션이 내가격(in the money) 또는 등가격(at the money) 상태일 때: "콜옵션의 내재가치(intrinsic value) = 자산가치 – 콜 행사가격" , 자산은 이미 FV로 계속 잡히고 있으므로, 부채를 산정할 때는 콜옵션의 내재가치 효과는 반영하지 않고, 대신 콜 행사가격을 기준으로 고정한다. 다만, 수취인에게 여전히 풋옵션 권리(공정가치 전액)는 부채로 인식해야 한다. 동시에, 양도인이 보유한 콜옵션의 시간가치는 양도인에게 유리한 권리이므로 부채에서 차감한다. 따라서:</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style=""><i>"부채 = 콜 행사가격 + 풋옵션 공정가치 – 콜옵션 시간가치"</i></span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">■ 직관적 해석</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">콜 행사가격</span><span style="">: 양도인이 자산을 되사야 하는 잠재적 의무의 “기본 금액”</span></p><p style="line-height:1.8;"><span style="">+ 풋옵션 공정가치</span><span style="">: 수취인이 언제든 행사할 수 있는 풋옵션의 의무</span></p><p style="line-height:1.8;"><span style="">– 콜옵션 시간가치</span><span style="">: 양도인이 가진 콜 권리(유리한 부분)는 부채에서 빼준다</span></p><p style="line-height:1.8;"><span style="">즉, 수취인의 권리(put)와 양도인의 권리(call)의 상쇄효과를 고려한 결과, 저 공식이 나온 것이다.</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">■ 비교: 콜이 외가격(out of the money)일 때</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">이 경우에는 콜옵션이 사실상 가치가 없으므로, 부채 = 자산 FV + 풋옵션 공정가치 – 콜옵션 시간가치로 계산한다. 즉, 콜이 무의미해지면 행사가격 대신 자산의 FV를 기준으로 잡는다는 차이가 있다.</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style=""><b>🟢 결론</b></span></p><p style="line-height:1.8;"><span style=""><b>​</b></span></p><p style="line-height:1.8;"><span style=""><b>“콜 행사가격 + 풋옵션 공정가치 – 콜옵션 시간가치”</b></span><span style="">라는 공식은 콜라 구조에서 양도인이 보유한 풋옵션 권리를 반영하여 부채를 과소계상하지 않도록, 그러나 콜옵션의 시간가치는 양도인에게 유리하므로 부채에서 차감하는 방식으로 설계된 것이다. </span><span style=""><b>즉, IFRS 9은 자산(FV) + 옵션가치(put, call)를 조합해 순장부금액 = 발행·보유 옵션의 공정가치</b></span><span style="">가 되도록 맞추기 위해 이 공식을 쓴다.</span></p></div></td></tr></tbody></table>

**■ Put Call Parity**

**​**

위 내용은 Put - Call Parity 등식을 떠올리면 쉽다.

​

▶ Put–Call Parity 기본식

​

동일한 기초자산(가격 = S), 동일한 행사가격(K), 동일한 만기(T)를 가진 옵션에 대해:

**C – P = S – K**

(C = 콜옵션 가치, P = 풋옵션 가치)

​

이를 변형하면:

**K + P – C = S**

**​**

**즉,** **행사가격 + 풋 – 콜 = 기초자산**

**​**

여기서 중요한 점은 IFRS는 자산은 이미 FV로 인식했기 때문에, 콜의 내재가치(intrinsic value)는 자산 쪽에 반영된다. 즉, 자산이 오르면, 그 초과분을 양도인이 콜로 가져가니까 이건 자산 측정 단계에서 자연스럽게 잡히는 것이다. 따라서 부채에서는 콜의 시간가치만 차감한다. 즉, Put–Call parity에서의 K + P – C = S, 여기서 C = (콜 내재가치 + 시간가치)인데, 내재가치는 이미 자산 쪽에서 반영되므로, 부채 공식에서는 콜의 시간가치만 차감하는 것이다. 그래서 IFRS 9에서 "부채 = K + P – Call(시간가치만)"이라는 공식이 도출된다.

<table style=""><tbody><tr><td colspan="3" rowspan="1" style="width: 100.0%; height: 129.0px;  background-color: #b0f1ff;"><div><p style="line-height:1.8;"><span style=""><i>EY, International GAAP 2025</i></span></p><p style="line-height:1.8;"><span style=""><b>​</b></span></p><p style="line-height:1.8;"><span style=""><b>■ 콜라 구조의 매도·매수청구권이 부여된 경우 공정가치로 측정되는 자산(Asset measured at fair value subject to collar put and call options)</b></span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">한 기업이 공정가치로 회계처리되는 금융자산을 보유하고 있으며, 장부금액은 CU100이다. 20X2년 1월 1일에 이 자산을 제3자에게 양도하는데, 다음 조건이 붙는다.</span></p><p style="line-height:1.8;"><span style="">​</span></p><ul><li><p style="line-height:1.8;"><span style="">기업이 수취인에게 콜옵션을 부여하여 기업이 CU120에 자산을 다시 매입하도록 강제할 수 있음</span></p></li><li><p style="line-height:1.8;"><span style="">수취인이 기업에게 풋옵션을 부여하여 수취인이 CU80에 자산을 기업에게 되팔 수 있음</span></p></li></ul><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style=""><b>이 옵션들은 심각하게 내가격도, 심각하게 외가격도 아닌 것으로 간주된다. 따라서 IFRS 9은 기업이 자산의 제거를 거부당할 정도로 중요한 지속적 관여가 존재한다고 보고, 자산을 계속 공정가치로 인식하도록 요구한다.</b></span></p><p style="line-height:1.8;"><span style=""><b>​</b></span></p><p style="line-height:1.8;"><span style="">양도일에 풋옵션과 콜옵션의 시간가치는 각각 CU5와 CU1이다. 이때 콜옵션은 외가격이므로, 관련 부채는 </span><span style=""><b>자산의 공정가치와 풋옵션의 공정가치를 합한 금액에서 콜옵션의 시간가치를 차감한 값</b></span><span style="">으로 산정한다. 즉,</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">(CU100 + CU1) – CU5 = CU96</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style=""><b>자산(CU100)과 부채(CU96)의 순액은 CU4인데, 이는 옵션 두 개의 순공정가치(call CU1 – put CU5)의 결과와 같다</b></span><span style="">. 거래가 정상가격으로 이루어졌다고 가정하면, 수취인은 CU96을 지급하고, 기업은 다음과 같이 분개한다.</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style=""><i>Dr 현금 96</i></span></p><p style="line-height:1.8;"><span style=""><i>Cr 부채 96</i></span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style=""><b>A. 양도자산 가치가 증가하는 경우</b></span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">20X2년 12월 31일, 자산의 공정가치는 CU140이고, 풋옵션과 콜옵션의 시간가치는 각각 CU2와 CU3이다. 이때 </span><span style=""><b>콜옵션은 내가격</b></span><span style="">이므로, IFRS 9은 부채를 콜옵션 </span><span style=""><b>행사가격</b></span><span style="">과 풋옵션 공정가치를 합한 금액에서 콜옵션의 시간가치를 차감한 값으로 측정하도록 요구한다. 즉:</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">(CU120 + CU2) – CU3 = CU118.5</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style="">자산(CU140)과 부채(CU118.5)의 순액은 CU21.5로, 이는 옵션 두 개의 순공정가치(call CU20 + CU3 – put CU2)의 결과와 같다. 분개는 다음과 같다.</span></p><p style="line-height:1.8;"><span style="">​</span></p><p style="line-height:1.8;"><span style=""><i>Dr 자산 (140 – 100) 40.0</i></span></p><p style=""><span style=""><i>Cr 손익(이익) 17.5</i></span></p><p style="line-height:1.8;"><span style=""><i>Cr 부채 (118.5 – 96) 22.5</i></span></p><p style="line-height:1.8;"><span style=""><i>​</i></span></p><p style="line-height:1.8;"><span style=""><i>이익은 콜옵션의 공정가치가 CU17 증가한 것(CU5에서 시작하여 20X2년 12월 31일에 CU22가 됨)과, 풋옵션의 공정가치가 CU0.5 감소한 것(양도인의 관점에서 이익, CU1에서 시작하여 20X2년 12월 31일에 CU0.5가 됨)을 합한 것이다. 만약 기업이 콜옵션을 행사한다면 분개는 다음과 같다.</i></span></p><p style="line-height:1.8;"><span style=""><i>​</i></span></p><p style="line-height:1.8;"><span style=""><i>Dr 부채 118.5</i></span></p><p style=""><span style=""><i>Dr 손실 1.5</i></span></p><p style="line-height:1.8;"><span style=""><i>Cr 현금 120.0</i></span></p><p style="line-height:1.8;"><span style=""><i>​</i></span></p><p style="line-height:1.8;"><span style=""><i>이 거래에서의 총 CU16의 이익(앞서 기록된 CU1.5의 손실과 20X2년에 기록된 CU17.5의 이익)은, 자산의 공정가치가 CU40 증가한 것(CU100에서 시작하여 20X2년 12월 31일에 CU140이 됨)에서, 수취인에게 순액 CU24를 지급한 것(CU120을 콜옵션 행사 시 지급하고, 초기 양도 시 CU96을 수취한 차액)을 차감한 결과를 의미한다.</i></span></p><p style="line-height:1.8;"><span style=""><i>​</i></span></p><p style="line-height:1.8;"><span style=""><b>B. 양도자산 가치가 감소하는 경우</b></span></p><p style="line-height:1.8;"><span style="">​</span></p><p style=""><span style="">이번에는 20X2년 12월 31일에 자산의 공정가치가 CU78이고, 풋옵션과 콜옵션의 시간가치는 각각 CU3와 CU2라고 가정한다. 이때 콜옵션은 여전히 </span><span style=""><b>외가격</b></span><span style="">이므로, IFRS 9은 부채를 자산 </span><span style=""><b>공정가치</b></span><span style="">와 풋옵션 공정가치를 합한 값에서 콜옵션의 시간가치를 차감한 금액으로 측정하도록 요구한다. 즉:</span></p><p style=""><span style="">(CU78 + CU3) – CU2 = CU78.5</span></p><p style=""><span style="">​</span></p><p style="line-height:1.8;"><span style="">자산(CU78)과 부채(CU78.5)의 순액은 –CU0.5인데, 이는 옵션 두 개의 순공정가치(call CU2 – put CU2 – CU0.5)의 결과와 같다. 분개는 다음과 같다</span></p><p style="line-height:1.8;"><span style=""><i>​</i></span></p><p style="line-height:1.8;"><span style=""><i>Dr 부채 (78.5 – 96) 17.5</i></span></p><p style=""><span style=""><i>Dr 손실 4.5</i></span></p><p style="line-height:1.8;"><span style=""><i>Cr 자산 (100 – 78) 22.0</i></span></p><p style="line-height:1.8;"><span style=""><i>​</i></span></p><p style="line-height:1.8;"><span style=""><i>손실은 콜옵션의 공정가치가 CU3 감소한 것(CU5에서 시작하여 20X2년 12월 31일에 CU2가 됨)과, 풋옵션의 공정가치가 CU1.5 증가한 것(양도인의 관점에서는 감소, CU1에서 시작하여 20X2년 12월 31일에 CU2.5가 됨)을 합산한 것이다. 만약 수취인이 풋옵션을 행사한다면 분개는 다음과 같다.</i></span></p><p style="line-height:1.8;"><span style=""><i>​</i></span></p><p style="line-height:1.8;"><span style=""><i>Dr 부채 78.5</i></span></p><p style=""><span style=""><i>Dr 손실 1.5</i></span></p><p style="line-height:1.8;"><span style=""><i>Cr 현금 80.0</i></span></p><p style="line-height:1.8;"><span style=""><i>​</i></span></p><p style="line-height:1.8;"><span style=""><i>이 거래에서의 총 CU6 손실(앞서의 CU1.5 손실과 20X2년에 기록된 CU4.5 손실)은, 자산의 공정가치가 CU22 감소한 것(CU100에서 시작하여 20X2년 12월 31일에 CU78이 됨)에서, 수취인으로부터 받은 순액 CU16(초기 양도 시 수취한 CU96에서 풋옵션 행사 시 지급한 CU80을 차감한 금액)을 가감한 결과를 의미한다.</i></span></p></div></td></tr></tbody></table>

​

[\[IFRS Issue Paper1051\]KIFRS1109, 제거(derecognition), 자산양도와 동시에 Call Option을 보유하는 경우 회계처리](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250821185226515ck)

[![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fscs-phinf.pstatic.net%2FMjAyNTA4MjFfNzAg%2FMDAxNzU1NzY5ODM5MzEz.lD9ywYAC255EHF4BgRo5vbYUYCwzV976DcKPEhl9lj4g.JHrIx5JUPu_3PSp_wiUTvb34_E_eAR_AlwCzuYGGEy4g.JPEG%2FFB_IMG_1755435033039.jpg%3Ftype%3Dw800%22&type=ff500_300)](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250821185226515ck)[

**\[IFRS Issue Paper1051\]KIFRS1109, 제거(derecognition), 자산양도와 동시에 Call Option을 보유하는 경우 회계처리**

10501 ● 자산양도와 동시에 Call Option을 보유하는 경우 회계처리 ■ 자산양도자가 call option을 보유하는 경우 한 기업이 금융자산을 보유하고 있으며, 이는 당기손익-공정가치(FVTPL)로 회계처리되고 있으며 장부금액은 CU80이다. 이 자산을 제3

contents.premium.naver.com

](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250821185226515ck)

[\[IFRS Issue Paper1052\]KIFRS1109, 자산양도시 풋옵션을 부여한 경우 회계처리](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250822101519912jm)

[![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fscs-phinf.pstatic.net%2FMjAyNTA4MjJfMjk5%2FMDAxNzU1ODI1MjcxMTQx.N3jW9shlFUc0BbHx2elqnyyvRtgypF7FAquTXsIVYcIg.HcRwCbaWtUzyN-nhCrzLYMzCFaNHhELcFfXD8znEoS8g.JPEG%2FSmartSelect_20240224_181235_Instagram.jpg%3Ftype%3Dw800%22&type=ff500_300)](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250822101519912jm)[

**\[IFRS Issue Paper1052\]KIFRS1109, 자산양도시 풋옵션을 부여한 경우 회계처리**

1052 ● 자산양도시 풋옵션을 부여한 경우 회계처리 만약 수취인의 매도청구권이 공정가치로 측정되는 양도자산의 제거를 방해한다면, IFRS 9은 그 자산을 공정가치와 옵션의 행사가격 중 낮은 금액으로 측정할 것을 요구한다. 이러한 처리의 근거는 기업이 옵션의 행사가격

contents.premium.naver.com

](https://contents.premium.naver.com/busymoon/kicpakpmg/contents/250822101519912jm)

​