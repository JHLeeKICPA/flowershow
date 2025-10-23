# Supporting Tool 관련 통제에 대해 문의 드립니다.

## 질문
회사에서 Supporting Tool에 대해 적용되는 통제를 1) 관리자 권한을 소유한 사용자에 대한 적정성 판단을 위한 통제와 2) 로그인 시, 적용되는 패스워드 정책 적정성 관련 통제로 구분하여 설계 및 운영 중에 있습니다.
회사에서 도입한 Supporting Tool은 패키지 제품입니다.
이런 Supporting Tool 제품에 대해 감사인이 본 제품에 대한 업데이트 패치 변경에 대한 요청 및 승인 통제까지 설계해서 운영하라고, 미비점을 제시하였는데 Supporting Tool 제품에 대해 패치 통제까지 설계되어 운영되는 것이 적합한 부분인지 문의 드립니다.
(※ 회사 내, 각종 IT자산에 대한 O/S 및 DB 레벨에서의 프로그램 업데이트 및 패치하는 부분에 대해서는 통제가 당연히 존재합니다)
Supporting Tool 제품에 대한 패치 여부까지 통제되어야 한다면 각종 데이터의 처리 및 수식연산 처리하는 업무용 프로그램으로 많이 사용하는 Excel도 MS사에서 패치를 하는 것으로 알고 있는데 이런 오피스 프로그램은 상관없는건지 문의드립니다.

## 답변
Supporting tool의 ITGC 설계 범위는 해당 supporting tool의 특성과 관련 위험에 따라 달라질 수 있습니다. Supporting tool이 패키지 솔루션일 경우 프로그램 변경과 관련된 Risk는 패치 변경의 경우에 해당될 수 있으므로 해당 통제를 설계 및 운영하는 경우가 있습니다.
또한 Supporting tool은 in-scope 시스템의 ITGC를 지원하기 위한 보조 Tool(예 : DB접근제어솔루션 등)이 해당되어 MS office 프로그램 등은 일반적으로 Supporting tool로 식별하지 않는 경우가 많습니다.

## 출처
https://www.k-icfr.org/sub/menu/qna.asp?rWork=TblRead&rNo=685&rGotoPage=27&rSchText=&rType=1

---
*게시글 번호: 473*
