# 📊 Telco Customer Churn Prediction  
통신사 고객 이탈 예측 프로젝트

> 데이터마이닝 팀 프로젝트 (TEAM 5)

---

## 📌 프로젝트 개요

스마트폰 사용률 증가와 함께 통신사 간 경쟁이 심화되면서  
고객 이탈(Churn)을 줄이는 것이 중요한 비즈니스 과제가 되었다.

본 프로젝트는  
👉 고객 이탈 여부를 예측하고  
👉 이탈에 영향을 미치는 주요 요인을 분석하여  
👉 실제 비즈니스 의사결정에 활용 가능한 인사이트를 도출하는 것을 목표로 한다. 

## 🎯 목표

- 고객 이탈 여부 예측 모델 구축
- 이탈에 영향을 주는 주요 변수 분석
- 데이터 기반 고객 유지 전략 인사이트 도출


## 📂 Dataset

- **출처**: Kaggle - Telco Customer Churn  
- **데이터 규모**: 7,043명 고객  
- **특징 수**: 52개 변수  
- **타겟 변수**: `Churn` (이탈 여부)

### 주요 변수
- 계약 유형 (`Contract`)
- 월 요금 (`MonthlyCharges`)
- 서비스 사용 여부 (Streaming, Internet 등)
- 고객 만족도 (`Satisfaction Score`)
- 사용 기간 (`tenure`)

## 🔍 EDA (Exploratory Data Analysis)

- 불필요 변수 제거 (target leakage 및 중복 변수)
- 결측치 분석 (TotalCharges 11개 결측 존재)
- 클래스 불균형 확인 (약 3:1 비율)
- 주요 영향 변수 도출:
  - 계약 유형
  - 고객 만족도
  - 인터넷 서비스 유형
  - 기술 지원 여부

## 🧹 Preprocessing

### 1. 결측치 처리
- `TotalCharges` → 선형회귀 기반 대치
- (`TotalRevenue`와 높은 상관관계 활용)

### 2. 인코딩
- 명목형 변수 → One-hot Encoding
- 순서형 변수 → Label Encoding

### 3. Feature Transformation
- Skewness 기반 log / sqrt 변환

### 4. Feature 제거
- City 변수 → 영향 미미하여 제거
- 불필요/중복 변수 제거


## 🧠 Modeling

### 사용 모델
- Logistic Regression
- SVM
- KNN
- Decision Tree
- Naive Bayes
- Ridge / Lasso / ElasticNet

### Feature Selection 방법
- Forward Selection
- Backward Elimination
- Stepwise
- Genetic Algorithm
- Random Forest Importance
- PCA / Truncated SVD

👉 총 7가지 방법으로 변수 선택 및 비교 수행

---

## 📈 Results

### Logistic Regression (기본 모델)
- F1 Score ≈ **0.91**

### KNN (Forward Selection)
- F1 Score ≈ **0.94 (최고 성능)**

👉 최종적으로  
**KNN + Forward Selection 조합이 가장 높은 성능**을 보임


## 🔍 XAI (Explainable AI)

### 주요 영향 변수
- 고객 만족도 (`Satisfaction Score`)
- 사용 기간 (`tenure`)
- 온라인 보안 서비스 (`OnlineSecurity`)
- 추천 수 (`Number of Referrals`)

👉 고객 이탈은 단순 요금보다  
**만족도와 서비스 경험이 더 큰 영향**을 미침

---

## 💡 Insight

- 단기 계약 고객 (Month-to-month) 이탈률 높음
- 고객 만족도 ↓ → 이탈 확률 ↑
- 보안/기술 지원 서비스 사용 고객 → 이탈률 낮음
- 추천 기반 고객 → 충성도 높음

👉 **서비스 품질 + 고객 경험 개선이 핵심 전략**

---

## 👥 Team

- 윤주호
- 복성준
- 송명섭
- 윤지형
- 박규민
---

## 🚀 Conclusion

본 프로젝트는 고객 이탈 예측뿐 아니라  
👉 **비즈니스 의사결정에 활용 가능한 인사이트 도출**에 초점을 맞췄다.

특히  
- 고객 만족도
- 계약 구조
- 서비스 품질

이 세 가지 요소가 핵심적인 이탈 요인으로 확인되었으며,  
이를 기반으로 **실제 고객 유지 전략 수립 가능성**을 제시하였다.
