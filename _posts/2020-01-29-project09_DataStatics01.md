---
title: "data statics #1"
excerpt: "Linear Regression on the number of bees"

categories:
  - project
tags:
  - Linear Regression

---

## Linear Regression
영상에서 50개의 이미지를 뽑아 foreground pixel의 수를 측정해주고, 해당 이미지에서 벌의 수를 측정하여 Linear Regression으로 foreground pixel 수에 대한 벌의 수의 식을 구하여 주었다.

statsmodels 라이브러리에서 OLS 클래스를 이용하여 선형회귀분석(Linear Regression)을 구현하였다.

그래프는 seabon 라이브러리를 이용하여 그렸다. 

![](https://raw.githubusercontent.com/beeot/beeot.github.io/master/_docs/project/linear_reg_graph.PNG)





![](https://raw.githubusercontent.com/beeot/beeot.github.io/master/_docs/project/linear_reg_result.PNG)

Data Frame 이름은 beeot이다.

bees는 벌의 수를 의미하고, pixel은 픽셀 수를 의미한다.

- R-squared : 0.494 

  R-squared는 앞서 회귀분석을 실시한 "bees = B0 + B1 * pixel"모델이 beeot 데이터프레임을 얼마나 설명해주는지 모델식의 적합성을 말해준다. 결과는 선형 회귀분석 모델이 bees변동성의 49.4%를 설명한다는 의미이다. R-squared는 0~1의 값을 가지고 0이면 모델의 설명력이 전혀 없는 상태, 1이면 모델이 완벽하게 데이터를 설명해주는 상태이다. 

  사회과학에서는 보통 0.4이상이면 괜찮은 모델이라고 보면 된다.

  

- P>|t|(유의확률):  0.000

  P>|t|(유의확률)은 독립변수의 유의확률이다. 보통 독립변수가 95%의 신뢰도를 가져야 유의미하다고 판단한다. 이 경우 독립변수의 유의확률은 0.05보다 작은 값이 산출된다. 즉, 독립변수의 유의확률이 0.05보다 작으면, 독립변수가 종속변수에 영향을 미치는 것이 유의미하다고 본다.

  위 경우 pixel의 유의확률은 0이다. 따라서 pixel은 bees에 유의미하게 영향을 미친다고 할 수 있다.

  

- No.observations : 50

  50개의 데이터 쌍을 가지고 회귀분석을 실시하였다는 것을 알 수 있다.

현재 데이터의 수는 겨우 50개밖에 되지 않아 사실상 유의미한 모델이라고 생각하지 않는다. 

또한 실제 데이터가 아니기 때문에 하루빨리 orchard에 가 직접 데이터를 추출해 더 높은 정확도를 가진 모델을 만들어 내는게 목표이다. 

