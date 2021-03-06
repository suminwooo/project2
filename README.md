# project2

-> [링크](링크url)   
-> [사진](사진url)   

  - 주가 예측 모델을 위해 이용한 아이디어와 구상한 코드 및 결과    
  - 데이터는 2017년부터 2020년 2월까지의 OHLC, volumne, 외 9개의 변수 활용.(비공개 데이터)    
  - 공개하지 못하는 데이터는 표시 하지 않음.  
  
0. OHLC 값을 이용하여 새로운 변수 생성-> [코드](https://github.com/suminwooo/project2/blob/master/0.%20OHLC%20%EA%B0%92%EC%9D%84%20%EC%9D%B4%EC%9A%A9%ED%95%98%EC%97%AC%20%EC%83%88%EB%A1%9C%EC%9A%B4%20%EB%B3%80%EC%88%98%20%EC%83%9D%EC%84%B1.ipynb)   
 

1. 종가의 상관계수를 활용. ->[결과](https://github.com/suminwooo/project2/blob/master/1.plot.pdf)    

  - 가설 : 상관관계가 높은 종목들을 활용하여 새로운 대표 지표를 만들어서 활용할 수 있다.    
  - 예를 들어, 한종목이 새로운 index의 위쪽에 있으면 매도 포지션이고 아래에 있다면 매수 포지션이다.(index를 따라갈 것이라고 가정함.)  
  - 1-1.은 종가의 상관관계가 95%이상인 것들로만 모았을때의 경우를 표현함.(문제점 : 개별 종목이 같은 종목으로만 선택됨.)    
  - 결과가 좋지 않아서 1-2.를 통해 70~85%로 수정함. 그결과 포함된 개별 종목이 개선이 됨.   
      - 1-1. 종가의 상관관계가 95% 이상일 경우-> [코드 1-1-1](https://github.com/suminwooo/project2/blob/master/1-1-1.%20%EC%83%81%EA%B4%80%EA%B4%80%EA%B3%84%EA%B0%80%2095%25%EC%9D%B4%EC%83%81%EC%9C%BC%EB%A1%9C%20%EA%B5%B0%EC%A7%91.ipynb), [코드 1-1-2](https://github.com/suminwooo/project2/blob/master/1-1-2.%20%EA%B5%B0%EC%A7%91%20%EC%A7%91%ED%95%A9%EC%9D%84%20%EC%8B%9C%EA%B0%81%ED%99%94%ED%95%98%EA%B8%B0.ipynb)   
        - 1-1-1.은 상관관계가 95%이상이고 6개의 set에서 공통으로 나온 종목들을 확인한뒤, 1-1-2.에서 총6개의 set을 만듬.(3년의 기간을 6개월씩 나누어 상관관계가 항상 95% 이상인 종목만)  
          - 앞서 구상한 set을 이용한 결과 35개의 종목이 뽑혀져 나오므로 이를 재구상하여  포트폴리오로 만듬. 이를 그래프를 확인한 결과 그래프의 모양이 똑같이 나옴. -> 종목을 확인한 결과, 같은 상품으로 구성되어있음.  
          - 이는 전혀 도움이 되지 않는 모델임을 확인함. 이를 개선하여 2번에서는 상관관계를 좀 더 줄여서 새롭게 모델을 구성함.  

      - 1-2. 종가의 상관관계가 70%~85%일 경우-> [코드 1-2-1](https://github.com/suminwooo/project2/blob/master/1-2-1.%20%EC%83%81%EA%B4%80%EA%B4%80%EA%B3%84%EA%B0%80%2070%25%EC%9D%B4%EC%83%81%2085%25%EC%9D%B4%ED%95%98%EB%A1%9C%20%EA%B5%B0%EC%A7%91.ipynb), [코드 1-2-2](https://github.com/suminwooo/project2/blob/master/1-2-2.%20%EA%B5%B0%EC%A7%91%20%EC%A7%91%ED%95%A9%EC%9D%84%20%EC%8B%9C%EA%B0%81%ED%99%94%ED%95%98%EA%B8%B0.ipynb)  
        - 1-1.의 문제를 개선하기 위해서 새로운 기준으로 데이터를 뽑음.
        - 앞서 마찬가지의 방법으로 구상함. 한가지 차이점은 앞선 모델은 6개의 기간에 모두 포함되어야 하지만 유연하기 표현하기 위해 6개중 5개 이상일 때에도 포함시킴.
        - 비슷한 방법으로 분석결과를 시각화 한 결과, 종목도 다양하게 뽑혀져 나오며 그래프도 유의미한 해석을 할 수 있게 되었음.
        - 이번에 나온 결과를 바탕으로 평균을 새로운 index로 잡아서 다양한 모델로 예측을 해 볼 예정.   

      - 1-3. 군집분석-> [코드 1-3-1](https://github.com/suminwooo/project2/blob/master/1-3-1.%20%EA%B5%B0%EC%A7%91%20%EB%B6%84%EC%84%9D%20%EC%A7%91%ED%95%A9%20%EB%B6%84%EC%84%9D%20set01%20%ED%85%8C%EC%8A%A4%ED%8A%B8.ipynb), [코드 1-3-2](https://github.com/suminwooo/project2/blob/master/1-3-2.%20%EA%B5%B0%EC%A7%91%20%EB%B6%84%EC%84%9D%20%EC%A7%91%ED%95%A9%20%EB%B6%84%EC%84%9D%20set02%20%ED%85%8C%EC%8A%A4%ED%8A%B8.ipynb)   
        - 1-2 를 토대로 하나의 종목들이 평균과 얼마나 만나는 지 확인함. 1-3-1은 set01, 1-3-2은 set02. 많이 만나는 경우에는 20여번정도 되고 적게 만나는 경우 10이하이다. 이를 통해 전략을 잘 수립한다면 효과적인 매도매수 포지션을 취할 수 있다.
    
    
      - 1-4. 최종본-> [코드 1-3-1](https://github.com/suminwooo/project2/blob/master/1-3-1.%20%EA%B5%B0%EC%A7%91%20%EB%B6%84%EC%84%9D%20%EC%A7%91%ED%95%A9%20%EB%B6%84%EC%84%9D%20set01%20%ED%85%8C%EC%8A%A4%ED%8A%B8.ipynb), [코드 1-3-2](https://github.com/suminwooo/project2/blob/master/1-3-2.%20%EA%B5%B0%EC%A7%91%20%EB%B6%84%EC%84%9D%20%EC%A7%91%ED%95%A9%20%EB%B6%84%EC%84%9D%20set02%20%ED%85%8C%EC%8A%A4%ED%8A%B8.ipynb)   
        - 지금까지를 토대로 단순히 짧은 기간에 다양한 종목과 상관관계를 가지는 것들로만 구성하였을때를 표현함.
        - 이를 새로운 지표로 활용할수 있다.
      
      
2. 클래스를 활용한 주가 예측 모델 만들기.

- 가설 : 3일간의 데이터를 활용해 5개의 추세로 나누어서 2개의 집합을 하나의 추세로 보고 추세가 들어갈 class를 예측함.
- 코스피 200에 3년 데이터가 온전히 있는 종목을 이용. return값을 활용해 -1.0, -0.3, 0.3,,1.0 총 다섯개의 범위에 따라 class를 지정해줌.
- 이러한 데이터를 훈련시킨 다음 미래에 어떻게 나올지 예측할 예정.
    - 방법: 코스피200 종목 하나씩 훈련시켜 하나의 주가에만 적용할수 있도록
      - 2-1. 코스피 200 종목 크롤링 [코드](https://github.com/suminwooo/project2/blob/master/2-1.%20%EC%BD%94%EC%8A%A4%ED%94%BC%20200%20%EC%A2%85%EB%AA%A9%20%ED%81%AC%EB%A1%A4%EB%A7%81.ipynb)  
      : 네이버 금융을 활용하여 코스피 200 종목과 코드를 크롤링 
      - 2-2. class 설정  [코드](https://github.com/suminwooo/project2/blob/master/2-2.%20class%20%EC%84%A4%EC%A0%95.ipynb)    
      : return값을 활용해 -1.0, -0.3, 0.3,,1.0 총 다섯개의 범위에 따라 class를 지정해줌. 
      - 2-3-1. 한개의 종목 활용한 RNN [코드](https://github.com/suminwooo/project2/blob/master/2-3-1.%20%ED%95%9C%EA%B0%9C%EC%9D%98%20%EC%A2%85%EB%AA%A9%20%ED%99%9C%EC%9A%A9%ED%95%9C%20RNN.ipynb)  
      : RNN을 활용하여 데이터를 훈련시킨뒤 다음에 나올 2개의 클래스를 예측하는 모델을 만들어줌.(사용 종목 : 005930)
      - 2-3-2. RNN 최종모델 [코드](https://github.com/suminwooo/project2/blob/master/2-3-2.%20RNN%20%EC%B5%9C%EC%A2%85%EB%AA%A8%EB%8D%B8.ipynb)  
      : 2-2-1을 바탕으로 코드를 정리하고 코스피200에 있는 종목은 사용할수 있도록 설정.
      - 2-4. 평가 [코드](https://github.com/suminwooo/project2/blob/master/2-4.%20%ED%8F%89%EA%B0%80.ipynb)  
      : 지금까지의 결과를 클래스를 원래 상태의 형태로 돌려줌. 총 4일간의 데이터의 형태가 표현이 됨.  이를 토대로 각각의 점수와 가중치를 선택하여 부여함. 보는 관점에 따라 점수를 선택하여 나온 종목을 사용하면 됨.


3. CNN을 활용한 주가 예측.

- 2D와 1D를 활용하여 CNN모델을 만들어봄.
- 데이터는 현재 코스피200 종목중 지난 3년간 계속 유지되어온 종목만 활용

1. 2D 기본모델(close만 활용) [코드](https://github.com/suminwooo/Stock-price-prediction2/blob/master/3-1.%202D%20%EA%B8%B0%EB%B3%B8%EB%AA%A8%EB%8D%B8(close%EB%A7%8C%20%ED%99%9C%EC%9A%A9).ipynb)  
      : 기본적인 모델을 만들기 위해서 종가를 5일씩 나누어 그림으로 저장해줌.  
      y값같은 경우에는 마지막 5일을 기준으로 6일째 되는날 가격이 오르면 1 가격이 내려가면 0으로 설정
      
      - 문제점 : 아직까지 하이퍼 파라미터를 설정해주지 않았고 종목마다 대부분 50~55% 사이에 머뭄
      
