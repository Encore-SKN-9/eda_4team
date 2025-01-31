# [SKN09-EDA-4Team]
✅ SKN AI FAMILY CAMP 9기<br>
✅ 개발 기간: 2025.01.15 - 2025. 01.21

---

# 📍Introduction Team(팀 소개)
### 🏠팀명: Howse<br>
  부동산(House) 데이터를 어떻게(How?) 분석할 것인가에 대해 연구하는 하우즈입니다.
### 👩‍💻팀원
 
| 김우중👨‍💻 | 임수연👩‍💻 | 조민훈👨‍💻 |
|--|--|--|
|<a href="https://github.com/kwj9942">@kwj9942</a>|<a href="https://github.com/ohback">@ohback</a>|<a href="https://github.com/alche22">@alche22</a>|
<br>

# 📍프로젝트 개요
### 프로젝트명
주택 특성을 이용한 가격 예측

### 프로젝트 배경
- 배경: 주택보유율이 낮은 이 시대에 사용자의 내 집 마련을 목표로 주택 특성, 주변 인프라, 도시별 평균 집값 차이 등에 따른 주택 가격을 예측하고 합리적인 주택 구매를 위한 시스템을 설계했습니다.
<br>
<img src="images/image.png" width="1000" height="700" />
출처 : https://news.kbs.co.kr/news/pc/view/view.do?ncd=8139571
<br>
<br>

---

# 📍Data Pre-Processing(데이터 전처리)
## ✅EDA 진행 목차
### 1. 데이터 로드 & 확인<br>
- Kaggle에서 "House Price Prediction" 으로 검색하여 가장 최근에 업데이트 된 데이터를 선정.
<img src="images/image-1.png" width="650" height="170" />
<img src="images/image-2.png" width="650" height="250" />
<br>

### 2. 데이터 구조 및 기초 통계 확인
- 12개의 문자형 변수와 11개의 숫자형 변수로 구성되어 있으며 결측치가 존재하지 않는다.
<img src="images/image-3.png" width="650" height="600" />
<br>

- 기본 통계 정보를 확인하였을때 0인 값이 존재
<img src="images/image-4.png" width="650" height="400" />
<br>

- Price_per_SqFt는 제곱피트당 가격으로 0이 나와서는 안되는 값이라 따로 계산해본 결과,<br>소수점 둘째 자리에서 잘리면 0으로 나오는 것을 확인하였다.
<img src="images/image-5.png" width="650" height="500" />
<br>

- 라벨링을 통한 범주형 데이터 처리
<img src="images/image-13.png" width="800" height="350" />
<br>


### 3. 결측치 및 이상치 탐색
- 데이터 탐색 과정에서 결측치(NaN)가 발견되지 않아 결측치 처리는 생략하였다.
- 이상치(Outlier)를 탐색하기 위하여 모든 변수에 대해 BoxPlot을 그려 보았으며 대부분의 데이터들이 고르게 분포하는 것을 확인할 수 있었다.
<img src="images/image-볼 수 있을 것 같습니다.
- 조민훈 : 이번 데이터를 반면교사 삼아 이후의 데이터를 찾을 때는 원산지를 확인하고 데이터 신뢰도 검증을 보다 철저히 해야겠다.
