# 데이터 전처리에 사용하는 패키지
## missingno 
- 결측데이터를 검색하여 시각화 함
- `.bar()`, `.matrix()`함수로 확인

## scikit-learn 패키지의 SimpleImputer 클래스
- 결측값을 채우고자 할때, strategy 인수를 "mean"으로 하면 중앙값 "median"으로 하면 중앙값, "most_frequent"로 하면 최빈값을 대체값으로 사용한다.


## patsy
- 데이터를 선택, 변환, 추가, 스케일링 함
- `dmatrx()` 함수를 사용하면 데이터 프레임에 상수항을 추가하거나 원하는 데이터만 선택하거나 변형할 수 있다.
- 스케일링을 위한 함수 
  - center(): 평균을 0으로 스케일링
  - standardize(): 평균을 0으로하고 표준편차를 1로 스케일링
  - scale(): standardize() 과 같음
