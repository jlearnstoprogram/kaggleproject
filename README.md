# Kaggle Project - GoDaddy MicroBusiness Density Prediction

## 프로젝트 목표
- Kaggle의 주어진 데이터를 활용하여 일정 지역의 월별 소상공인 밀도 예측하기

#### 프로젝트 기한: 2023/01/31-2023/02/15

### 요건
- SMAPE (대칭 평균 절대 오차 퍼센트) 예측 평가지표를 이용해 모델의 성능을 확인해야함
- 데이터셋 출처: Kaggle
- 개발도구 :  xgboost, lightgbm, catboost, sklearn, matplotlib, 쥬피터, pandas, numpy, seaborn
- 개발언어 및 프레임워크: 파이썬

### 프로젝트 진행
- 캐글에서 데이터셋 가져오기
- 모델에 활용 할수있도록 데이터 전처리
- 데이터 분석 및 시각화 
  - Blacklist CFIPS는 Kaggle Discussion에서 발견하여, 활용해 본 결과 성능이 더 높게 나와서 활용하기로 했음 
  - 시계열 데이터라고 판단되어 Timestamp, Lag 방식 이용
- 모델 구현 
  - XGBRegressor, LightGBM Regressor, CatBoostRegressor, HistGradientBoostingRegressor, Random forest regressor, 
  Extra trees regressor, KNN, Linear Regression , DecisionTree regressor, Extra tree regressor
    - 총 10개 모델 사용
- 모델 최적화
  - 모델 최적화 할때 학습 성능 낮은 모델들을 스태킹 방식으로 합치고, 스태킹한 모델을 성능이 좋은 모델과 함께 보팅한 방식으로 접근
    - 자료 조사한 결과 스태킹은 학습 성능이 낮은 모델을 앙상블할때 쓰이고, 보팅은 학습 성능이 높은 모델을 앙상블할때 쓰임
- 캐글에서 예측값 확인

### 프로젝트 결과 
- 소상공인 밀도는 과거 추세에 따른 예측이 유의미함
- 일부 타 지역과 성격이 다른 이상치 데이터는 제거하여 분석하는 것이 모델 학습 측면에서 더 유리함
- 다양한 모델을 이용한 앙상블 학습을 통해 최종 성능을 높임
- 결과: 1.0846점대의 오차까지 줄임
  - 프로젝트 기한 이후 데이터가 추가되어 코드를 실행해도 점수가 다르게 나옴

### 파일요약 
#### godaddy_final.ipynb
#### census_starter.csv
#### sample_submission.csv
#### test.csv
#### 

|파일 명|파일 내용|
|:--:|:--:|
| godaddy_final.ipynb | 코드 |
| census_starter.csv | 캐글에서 제공한 인구조사 데이터 |
| sample_submission.csv | 캐글에서 제공한 submission 양식 |
| test.csv | 캐글에서 제공한 test 데이터 |
| train.csv | 캐글에서 제공한 train 데이터 |
