# DataMining_9

# 프로젝트 과정

__건강검진정보데이터와 혈압혈당데이터 병합__

'SEX', 'SBP', 'DBP', 'BMI', 'FBS' 변수들을 기준으로 데이터 병합

## Decision Tree
_Decision Tree는 feature inmportance 확인하고 영향력이 센 변수(FBS: 공복혈당)를 제외하는 용도로 사용_

모델 학습 후 feature importance 확인 결과 FBS가 다른 features를 압도할 정도로 높게 나와 FBS 제외하고 모델링 다시 진행

## Logistic Regression
_FBS 변수 제외하고 모델 학습 진행_

### 가중치 부여
종속변수인 DIS(당뇨병 진단내역)의 클래스 비율이 맞지 않아 가중치 부여하는 경우와 부여하지 않는 경우 두 가지 경우로 나누어서 분석 진행

_분석결과 가중치를 부여하지 않았을 경우:_

-클래스 비율 차이가 너무 커서 accuracy가 극단적으로 높게 나옴

-p-value 값이 0.05보다 낮은 변수들이 적고 정확한 해석 어려움

__따라서 minority class(1: 당뇨병 진단내역 있음)에 높은 가중치를 부여한 후 분석 진행__

###




# 결과
__LogisticRegression을 사용했을 때 약 61% 예측률을 보여줌__

__당뇨합병증에 영향을 많이 주는 인자를 coef값 활용하여 선정__

|    Feature   |   Coefficient   |
|--------------|-----------------|
| Intercept    |    -107.6542    |
| SEX          |     0.3010      |
| SBP          |     0.1957      |
| DBP          |     0.2101      |
| BMI          |     1.4397      |
| AGE          |     3.5926      |
| HEIGHT       |    -0.0393      |
| WAIST        |     0.1672      |
| HDL          |    -0.2796      |
| LDL          |    -0.0260      |


__당뇨합병증에 걸릴 확률에 대한 회귀식__

_오즈활용_
_Log ( p / ( 1 - p ) ) = -107.6542 + 0.3010 (SEX) + 0.1957 (SBP) + 0.2101 (DBP) +1.4397 (BMI) + 3.5926 (AGE) -0.0393 (HEIGHT) + 0.1672 (WAIST) - 0.2796 (HDL) - 0.0266 (LDL)_

회귀식은 차후 당뇨합병증을 예측하는 프로그램 제작에 활용된다면 당뇨합병증 위험도를 자가진단 할 수 있는 서비스를 할 수 있을 것이라고 봄


__분석 한계점__

-모형이 설명력이 다소 미흡하여 당뇨합병증이 잘 예측되었다고 볼 수 없었음

-1년 단위의 데이터를 분석하였기에 최소 3년이상의 데이터들을 분석하였다면 더욱 예측력이 좋은 모형을 만들 수 있었을 것
