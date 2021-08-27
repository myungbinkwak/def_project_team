# 데이터청년캠퍼스 심화 프로젝트

## 농작물 생산량 기반 가격 예측 시스템

### < 지역&품목 정하기 >

강원도
논벼, 겉보리, 콩, 참깨, 봄감자, 고랭지감자, 건고추, 양파, 마늘, 가을배추, 가을무, 사과, 배

⇒ 최종 5가지 품목 :  감자(희성), 고추(보미), 양파(은정), 사과(석원), 마늘(명빈)



### < 목적 >

 + 농산물 수급조절과 안정적인 농가 소득 보장
 + 농업의 혁신적인 성장 동력
 + 소비자의 체감 물가에 직접 영향을 주는 농산물 가격변동 예측으로 효과적인 대응방안 제시


### < 선정 배경 >

 + 해외에 비해 우리나라는 농업 빅데이터가 부족하다.
 +  농업 빅데이터의 발전을 통해 기업의 경우 도매가격을 알고 대량 구매를 하는 등 상업적인 측면에서 활용할 수도 있고, 농업관련 공공기관이 농업인들에게 스마트팜 자료를 공유한다면 우리나라 농산업이 한층 더 도약할 수 있을 것으로 보인다. 
 +  농작물의 가격 변동성이 큼 → 농가의 소득 보장이 어려움
 +  생산량  기반 가격예측 시스템의 부족 (각 기관이 뭉쳐 빅데이터 플랫폼을 구축한다고 했지만 이렇다 할 진척이 없음)
 +  농산물 가격 정보가 턱없이 부족함.
 +  선택한 작물은 강원도의 주요 재배 작물로 선정함.


### < 방법 >

 + 과거 가격데이터를 기반으로 가격 예측
 + 생산량은 일단 있는 자료 받아써서 가격 예측부터하고 생산량 예측을 시도해보는 건 어떨까 / 두 개의 예측 결과를 내기에 시간이 부족하진 않을까 걱정
 + 시간이 없어서 역할을 확실히 나눠서 빠르게 진행해야할 것 같음
 + 나중에 결과 보여줄 때 예측 가격과 전 날 가격 판매가격을 같이 보여줘서 차액정보를 보여주는 것도 좋을 듯 ( 시각화 단계에서 )
 + 표현은 앱보다는 웹이 더 좋을 것 같음
 + 가격예측 분석은 보통 시계열 분석 기법을 이용한다.
 + 대략 분석은 20년 정도만 해도 될 것 같긴함
 + LSTM 모델이 시계열 데이터에 효과적인 모델이라고 함 !



### < 효과 >

 + 농산물 수급조절 해결
 + 농작물 생산량을 기반으로한 가격 예측을 통해  농작물 공금이 안정화되면 소비자 가격 또한 안정화되어 서민경제에 긍정적인 영향을 끼칠 수 있다
 + 농업데이터 기반 새로운 가치 창출
 + 가격의 명확한 기준이 생겨 합리적이고 이성적인 의사결정 시스템이 도입된다면 수십 년간 이어져 온 유통구조의 파괴적 혁신도 가능함.
 + 농산물 가격 표준화와 미래 예측은 농산물 시세에 관한 불확실성을 최소화 할 수 있음
 + 농업경영인의 출하시기 및 출하처에 대한 경영의사결정에 도움이 될 수 있음




### < 필요한 데이터 >

 + 농작물 생산량 / 단위 면적당 생산량 / 기후데이터(기온, 강수량, 일조량)
 + 농작물 도매 가격 추이
 + 농작물 판매량 (?) / 농산물 도매시장 반입물량
     

### < 데이터수집 사이트 >

 + 농넷 (여기서 쓸거면 직접 긁어와야 할 듯)
 + 서울시 농수산식품공사
 + 도매유통정보시스템 OpenAPI
 + 전국농산물 도매시장 경락가격표준데이터
 + 농림수산식품교육문화정보원



### < 추가로 찾아볼 것 >

 + 도매시장별로 가격이 다를텐데 이것에 대한 처리는 어떻게 할지 (평균값, 도매시장을 정하거나)
 + 기후데이터를 강원도 데이터로 봐야할지 전국으로 봐야할지
 + 1) 강원도 지역 가격 예측이므로 강원도 기후를 봐야할지도 
 + 2) 강원도가 아닌 지역의 급격한 기후변화로 인해 강원도의 농산물 가격이 변동할 수도 있으므로 전국 기후데이터를 이용하는 것도 타당해 보이긴 함  ((같이고민해보자))
 + 어떤 변수를 사용할 것인지

### < 활용 데이터 정의 > 

 + 농산물 가격 데이터
 + 기후데이터생산량 데이터
 + 수출입 데이터

### < 데이터 처리방안 및 활용기법 >

 + 감자/양파/사과/배추/마늘
 + 과거 가격데이터를 기반으로 가격 예측
 + LSTM / SVM / RF / Prophet

### < 서비스 활용방안 >

 + 웹 페이지를 통해 도매가격을 직관적으로 예상할 수 있게 해준다.
 + 실제 도매가격과 예측 도매가격을 비교해서 보여준다.
 + (가능하다면) 하루에 한 번 갱신 혹은 실시간으로 갱신되어 최신 예상  데이터를 보여준다.

### < 기대효과 >

 + 강원도에 국한되지 않고 전국적으로 가격예측을 시도해볼 수 있다.
 + 농산물 수급조절 해결
 + 농작물 생산량을 기반으로한 가격 예측을 통해  농작물 공금이 안정화되면 소비자 가격 또한 안정화되어 서민경제에 긍정적인 영향을 끼칠 수 있다
 + 농업데이터 기반 새로운 가치 창출
 + 가격의 명확한 기준이 생겨 합리적이고 이성적인 의사결정 시스템이 도입된다면 수십 년간 이어져 온 유통구조의 파괴적 혁신도 가능함.
 + 농산물 가격 표준화와 미래 예측은 농산물 시세에 관한 불확실성을 최소화 할 수 있음
 + 농업경영인의 출하시기 및 출하처에 대한 경영의사결정에 도움이 될 수 있음
