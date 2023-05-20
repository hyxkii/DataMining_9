# DataMining_9

## 결과
**LogisticRegression을 사용했을 때 약 61% 예측률을 보여줌

**당뇨합병증에 영향을 많이 주는 인자를 coef값 활용하여 선정

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


**당뇨합병증에 걸릴 확률에 대한 회귀식

*오즈활용
*Log ( p / ( 1 - p ) ) = -107.6542 + 0.3010 (SEX) + 0.1957 (SBP) + 0.2101 (DBP) +1.4397 (BMI) + 3.5926 (AGE) -0.0393 (HEIGHT) + 0.1672 (WAIST) - 0.2796 (HDL) - 0.0266 (LDL)

회귀식은 차후 당뇨합병증을 예측하는 프로그램 제작에 활용된다면 당뇨합병증 위험도를 자가진단 할 수 있는 서비스를 할 수 있을 것이라고 봄


**분석 한계점

-모형이 설명력이 다소 미흡하여 당뇨합병증이 잘 예측되었다고 볼 수 없었음
-1년 단위의 데이터를 분석하였기에 최소 '' 3년이상의 데이터 ''들을 분석하였다면 더욱 예측력이 좋은 모형을 만들 수 있었을 것
