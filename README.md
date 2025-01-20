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

### 프로젝트 배경과 목표
- 배경: 주택보유율이 낮은 이 시대에 사용자의 내 집 마련을 목표로 주택 특성, 주변 인프라, 도시별 평균 집값 차이 등에 따른 주택 가격을 예측하고 합리적인 주택 구매를 위한 시스템을 설계했습니다.
<br>
<img src="images/image.png" width="1000" height="800" />
출처 : https://news.kbs.co.kr/news/pc/view/view.do?ncd=8139571
<br>
<br>
- 목표:

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
<img src="images/image-3.png" width="650" height="500" />
<br>

- 기본 통계 정보를 확인하였을때 0인 값이 존재
<img src="images/image-4.png" width="650" height="500" />
<br>

- Price_per_SqFt는 제곱피트당 가격으로 0이 나와서는 안되는 값이라 따로 계산해본 결과,<br>소수점 둘째 자리에서 잘리면 0으로 나오는 것을 확인하였다.
<img src="images/image-5.png" width="650" height="500" />
<br>

- 라벨링을 통한 범주형 데이터 처리
<img src="images/image-13.png" width="800" height="350" />
<br>

- Locality 변수는 지역번호로 Locality_1 ~ Locality_500까지의 변수들이 들어있으며,<br>여기에 라벨 인코더를 사용하면 모델에 숫자형 처럼 적용될 것이며,<br>원-핫 인코더를 사용하면 데이터의 변수가 500개 이상으로 나와 분석이 어려워진다.
<br>

- 필요 없는 변수나 중복 데이터 제거(ID 제거 / locality, Year_Built 제거 / Floor_No, Total_Floors 제거 고려)
<br>


### 3. 결측치 및 이상치 탐색
- 데이터 탐색 과정에서 결측치(NaN)가 발견되지 않아 결측치 처리는 생략하였다.
- 이상치(Outlier)를 탐색하기 위하여 모든 변수에 대해 BoxPlot을 그려 보았으며 이상치를 찾을 수 없었다.
<img src="images/image-6.png" width="1000" height="600" />
<br>

---

# 📍데이터 시각화를 통한 탐색📊
- HeatMap을 통해 변수별 상관관계를 확인해 보았다.
<img src="images/image-7.png" width="800" height="800" />
<br>

- Regplot을 통해 Target변수와 선형관계를 확인해 보았다.
<img src="images/image-8.png" width="800" height="800" />
<img src="images/image-9.png" width="800" height="800" />
<img src="images/image-10.png" width="800" height="550" />
<br>

- 연도별 건축된 건물의 유형을 확인해 보았다.
<img src="images/image-11.png" width="800" height="800" />
<br>

- 층과 관련된 변수인 Floor_No, Total_Floors와 집값과의 관계를 확인해 보았다.
<img src="images/image-12.png" width="800" height="350" />
<br>

---
- 사회간접자본에 따른 평균 집값

![Relationship between Transport Score and Price in Lakhs](https://github.com/user-attachments/assets/3708ea8e-a0a9-4317-80b1-cb914b70716d)
![Nearby_Hospitals vs  House Prices (in Lakhs)](https://github.com/user-attachments/assets/cbe8e365-22c5-4488-9450-043b77b791eb)
![Nearby Schools vs  House Prices (in Lakhs)](https://github.com/user-attachments/assets/2530db8c-f09b-437c-97d9-ab630110fdab)

- 부대시설에 따른 평균 집값
  
![Price in Lakhs by Security Availability](https://github.com/user-attachments/assets/81cb6df1-21ba-4012-b744-914ea9b45f60)
![Price in Lakhs by Parking Space Availability](https://github.com/user-attachments/assets/85677d26-5f0a-4369-9b63-1e7ff0e1733c)
![Price in Lakhs by Number of Amenities](https://github.com/user-attachments/assets/b93fae53-2848-413c-ae73-659c7badc2e1)

- 시공상태에 따른 평균 집값
  
![Average Price in Lakhs by Availability_Status](https://github.com/user-attachments/assets/86bcb25c-3f8a-404e-8e22-971dc63e90b1)

- 채광방향에 따른 평균 집값
  
![Average Price in Lakhs by Facing](https://github.com/user-attachments/assets/f01f8666-4ce4-4646-b104-ffe6b52c4cdc)

- 소유주에 따른 평균 집값
  
![Average Price in Lakhs by Owner_Type](https://github.com/user-attachments/assets/08f88e3a-b0e0-422f-9e0a-28d4137338f2)

---
- 도시/주 별 평균 집값
<img src="images/city_state.png" width="800" height="450" />
<br>

- 도시/주 별 평균 평당 가격
<img src="images/city_state_sqft.png" width="800" height="450" />
<br>

- 전체 평균 집값을 기준, 도시별 평균 이상/이하 비율
<img src="images/under_above_avg.png" width="800" height="330" />
<br>

- 집값의 범위를 3구간으로 나누어 출력한 Boxplot과 KDE
<img src="images/price_range.png" width="800" height="330" />
<br>

- 도시별/구간별 집값의 비율
<img src="images/3_range_lakhs.png" width="800" height="330" />
<br>

- 도시별 100Lakhs 이상 / 400Lakhs 이하 집값의 비율
<img src="images/100_400lakhs._all_cities.png" width="800" height="330" />
<br>

- 도시별 100Lakhs 이상 / 400Lakhs 이하 집값의 비율의 하위 10개 도시
<img src="images/100_400lakhs.png" width="800" height="330" />
<br>

---


# 결론📈
처음에는 잘 설계하여 추출한 데이터로 생각하였으나 탐색적 데이터 분석을 한 결과 이 데이터는 시뮬레이션 데이터로 추측된다. 탐색적 데이터 분석 결과 변수 간 관계 및 특성을 파악할 수 없었으며, 몇가지 간단한 모델 학습도 잘 학습이 되지 않는 모습을 보였다. 데이터에 추가적인 처리를 가하는 것으로 성능을 끌어올리는 것이 불가능하다고 판단되어 추후 관련된 다른 데이터를 찾아 다음 단계를 진행할 예정이다.

---

# 한줄회고📌
- 김우중 : 시각화 자료를 너무 안일하게 보고 있었던 것 같다. Heatmap이나 regplot을  보고 데이터를 바꿨어야 했다.
- 임수연 : 
- 조민훈 : 
