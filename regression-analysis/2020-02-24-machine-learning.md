## sklearn.preprocessing 패키지
스케일링 및 변수변환을 위한 `StandardScaler` 클래스에서
<!-- more -->

- `fit()`: 학습용 데이터를 입력으로 실행하면 평균값과 표준편차를 계산하여 객체내에 저장
- `transform()`: 저장했던 평균값을 빼서 새로운 평균값이 0이 되도록 만들고, 저장한 표준편차로 나누어 새로운 표준편차가 1이 되도록 데이터를 변환하여 출력
- `fit_transform()`: 1,2단계를 합친것

데이터에 아웃라이어가 있을 경우 `RobustScaler` 클래스를 사용
- 중앙값이 0, IQR(interquartile range)이 1이 되도록 변환하여, 아웃라이어가 섞여 있어도 데이터는 0주위에 남게 된다.


`FunctionTransformer`클래스와 `PolynomialFeatures`클래스
- `PolynomialFeatures`클래스는 입력데이터를 여러개의 다항식으로 변환
  - degree: 차수
  - include_bias: 상수항 생성 여부
- `FunctionTransformer`클래스는 사용자가 지정한 함수를 사용하여 입력값을 변환
  - 각도 0도와 360도를 구분하기위한 sin,cos함수 사용 예제