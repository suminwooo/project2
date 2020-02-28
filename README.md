# project2

  - 주가 예측 모델을 위해 이용한 아이디어와 구상한 코드 및 결과  
  - 데이터는 2017년부터 2020년 2월까지의 OHLC, volumne, 외 9개의 변수 활용.(비공개 데이터)  

1. 종가의 상관계수를 활용.

  - 가설 : 상관관계가 높은 종목들을 활용하여 새로운 대표 지표를 만들어서 활용할 수 있다.  
  - 예를 들어, 한종목이 새로운 index의 위쪽에 있으면 매도 포지션이고 아래에 있다면 매수 포지션이다.(index를 따라갈 것이라고 가정함.)
  - 1-1.은 종가의 상관관계가 95%이상인 것들로만 모았을때의 경우를 표현함.(문제점 : 개별 종목이 같은 종목으로만 선택됨.)  
  - 결과가 좋지 않아서 1-2.를 통해 70~85%로 수정함. 그결과 포함된 개별 종목이 개선이 됨.

  1-1. 종가의 상관관계가 95% 이상일 경우
  
  1-2. 종가의 상관관계가 70%~85%일 경우
