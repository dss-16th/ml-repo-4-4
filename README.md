

# 청소년의 질병 예측
machine learning project

<img width="450" src="https://user-images.githubusercontent.com/75352728/124350336-1f33e380-dc2f-11eb-87fb-3df6e7b2f0fe.png">


***

<br/>

## 1. INTRO


### 1-1. Purpose

<br/>

<img width="400" alt="스크린샷 2021-05-13 오전 11 04 09" src="https://user-images.githubusercontent.com/75352728/124360358-51136d00-dc64-11eb-8292-0251beb68ca0.png">

<br/>

- 뇌과학연구소가 제공한 2018년 데이터를 활용한 머신러닝 프로젝트입니다.
- 본 프로젝트에서는 청소년의 질병 예측과 소득에 따른 청소년의 질병 행태를 분석하였습니다.
- 본 프로젝트의 목적은 EDA를 통한 소득에 따른 청소년의 질병 형태를 분석하고 정신질환 코드를 예측하는 최적의 모델을 찾음에 있습니다.

<br/>

### 1-2. Conclusion

<img width="900" alt="스크린샷 2021-05-15 오후 9 29 41" src="https://user-images.githubusercontent.com/75352728/118361072-ac11d780-b5c4-11eb-80a8-cc40fdbb795d.png">

### 의료급여에서 높은 세가지 질병과 연관된 질병에 대해서 정부 지원금을 늘린다면 소득 수준의 차이가 감소될것 것으로 예상

<br/>


<img width="1394" alt="스크린샷 2021-05-15 오후 9 39 37" src="https://user-images.githubusercontent.com/75352728/118361388-3575d980-b5c6-11eb-98d3-98436b6f6495.png">


### 연령, 성별에 띠른 질병의 차이가 다르므로 연령, 성별에 따라 지원을 달리 한다면 효율적으로 지원 가능할것으로 보임. 

<br/>

1. 소득수준에 따라 질병의 종류가 다르다.
2. 의료급여 그룹 안에서 연령과 성별에 따라 질병의 종류의 차이가 있다.
3. 질병에 따라 연령, 성별 비율 또한 다르다.
4. 의료급여에서 성별, 연력에 차이가 있으므로 이러한 특성을 고려해 정부 지원금을 조정한다면 소득수준에 따른 의료 서비스의 차이를 줄일 수 있을 거라고 예상한다.
5. 의료급여 그룹에서 정신질환 비율이 높으므로 정부에서는 의료급여 그룹을 대상으로 한 정신질환 클리닉, 비용 절감 등을 통해 의료 서비스를 증진시킬거라고 예상한다.
<br/>
<br/>

### 1-3. Comment & Limitations
- F, P, O 코드 질환에 대해서만 EDA를 진행하였기 때문에 다른 질환에서의 성별, 연령에 따른 차이를 알 수 없다.
- 1개년 데이터만 사용하였기 때문에 연도별 변화는 알수 없다.


***



### 1-5 데이터

<br/>

1 출처
  - 뇌과학연구소
<br/>

### 1-6 팀원 / 역할
- [고원진]
  -  https://github.com/
  -  발표
- [이주영]
  - https://github.com/leekj3133
  - 데이터 확장자 변환(parquet), 데이터 전처리, EDA, 발표, README 작성

*****

<br/>


## 2. PROCESS

<img width="106" alt="스크린샷 2021-06-07 오전 12 17 51" src="https://user-images.githubusercontent.com/75352728/120929884-ce12fb80-c725-11eb-859f-99886025306f.png">

<br/><br/>

### 2-1 데이터 전처리

#### 1. 용량 줄이기

- 용량이 큰 데이터이기 떄문에 용량이 작은 데이터로 바꿔야함
- object 데이터 타입을 category 타입으로 변환 
- csv 파일을 parquet으로 변환

` df.to_parquet('경로/파일이름.parquet')`


`df = pd.read_parquet('./경로/파일이름.parquet', engine='pyarrow') `
	
	
#### 2. 데이터 mapping

- 코드로 이루어진 데이터 EDA를 위해 한글로 mapping 

<br/>
<br/>

### 2-2 시각화

<br/>

#### 1. 병원

<img width="400" alt="스크린샷 2021-05-13 오전 11 00 08" src="https://user-images.githubusercontent.com/75352728/118066844-62fe2f80-b3da-11eb-996d-66460bdcbfc0.png">

- 의료법 시행규칙에 명시되어 있는 것처럼 요양기관의 종류에 따라 법률에 명시된 병상 수 
- 즉 병원 베드 수, 의사, 치과의사, 한의사, 간호사 수나 그 이상을 둘 수 있습니다.
- 5가지 컬럼 대신 요양기관의 종류를 사용

<br/>

<img width="400" alt="스크린샷 2021-05-13 오전 11 02 12" src="https://user-images.githubusercontent.com/75352728/118067010-ac4e7f00-b3da-11eb-953c-012787e2afa3.png">
출처 : 경북일보 / 폭염에 노출된 임산부, 저체중아 출산…소득 낮을수록 위험 / 류진희 기자

<br/>
<br/>

<img width="400" alt="스크린샷 2021-05-13 오전 11 04 09" src="https://user-images.githubusercontent.com/75352728/118067141-f20b4780-b3da-11eb-9156-b52b7b5e07a0.png">
출처 : 마인드 포스트 / 정신질환자 의료급여 수준 건강보험의 58%…'행위별 수가제'로 전환해야 / 박종언 기자

<br/>
<br/>




<br/>

## 공중보건 문제에는 항상 거론되는 건강불평등을 주제로 진행해보자!

## 소득에 따라 질병에 차이가 있다.!! 

<br/>

<img width="400" alt="스크린샷 2021-05-13 오전 11 06 04" src="https://user-images.githubusercontent.com/75352728/118067290-3696e300-b3db-11eb-9149-5419dd41d67f.png">

- 의료급여 비율 
	1. 임신, 출산, 산후 질환 (O, P 코드)
	2. 신경계 질환 (G 코드)
	3. 정신 및 행동장애 (F코드)
	
<br/>


<img width="400" alt="스크린샷 2021-05-15 오후 10 21 45" src="https://user-images.githubusercontent.com/75352728/118362783-fb0f3b00-b5cb-11eb-8701-33b234a2d521.png">

- 의료급여 중 주상병과 부상병의 비율
	- F 코드 :  K 코드 소화기 계통과 연관
	- G 코드 : F 코드 정신질환과 연관
	- P 코드 : Q 코드 기형, 선천적이상, 유전병과 연관

<br/>

#### 2. 연령

<img width="400" alt="스크린샷 2021-05-13 오전 11 28 54" src="https://user-images.githubusercontent.com/75352728/118069045-672c4c00-b3de-11eb-8b36-5e068541853a.png">

- 전체 비율과 비교하였을 때 13-19세 의료급여 비율이 다른 연령보다 현저히 높게 나타남

<br/>

#### 3. 지역

<img width="400" alt="스크린샷 2021-05-13 오전 11 30 03" src="https://user-images.githubusercontent.com/75352728/118069135-90e57300-b3de-11eb-9030-c25f68a47643.png">

- 서울 경기에 비율이 높음을

<br/>

#### 4. 월

<img width="400" alt="스크린샷 2021-05-13 오전 11 30 32" src="https://user-images.githubusercontent.com/75352728/118069169-a22e7f80-b3de-11eb-8fa5-395118feaebc.png">

<br/>

#### 5. 주상병 이름

<img width="400" alt="스크린샷 2021-05-13 오전 11 30 57" src="https://user-images.githubusercontent.com/75352728/118069195-b07c9b80-b3de-11eb-9840-f591d49e5e49.png">

- 의료급여와 전체를 비교하였을 때 전체에서 볼 수 없었던 소아기 및 청소년기 행동 및 정서장애가 상위 10개의 10개의 상병안에 포함되어있음
- 의료급여에서 정신질환이 높은 비율이 나타남을 알 수 있음

<br/>

#### 6. 부상병 이름

<img width="400" alt="스크린샷 2021-05-13 오전 11 32 17" src="https://user-images.githubusercontent.com/75352728/118069286-e02ba380-b3de-11eb-9c09-b7cd759fe22c.png">

- 전체와 의료급여를 비교했을 떄 기분 장애, 소아청소년기 행동 정서 장애 등이 상위 10개 상병에 포함됨.
- 기분 장애, 소아청소년기 행동 정서 장애 : F코드인 정신질환에 포함되는 상병
- 의료급여에서 정신질환 비율이 높은 것을 알 수 있음.

<br/>

## 의료급여에서 정신질환이 높은 확률이 나타나는 것을 알 수 있다. 정신질환(F코드)에 대해 알아보자!

<br/>

## 정신질환 (F코드)

<br/>

#### 7. 연령

<img width="400" alt="스크린샷 2021-05-13 오전 11 34 56" src="https://user-images.githubusercontent.com/75352728/118069477-3e588680-b3df-11eb-9301-4192b406c666.png">

- 정신질환 코드 : 청소년의 비율이 현저히 높음
- 전체, 의료급여 청소년 비울이 높음

<br/>

#### 8. 병원

<img width="400" alt="스크린샷 2021-05-13 오전 11 36 24" src="https://user-images.githubusercontent.com/75352728/118069622-752e9c80-b3df-11eb-8ab1-ce628e4465d8.png">

- 의료급여 그룹: 외과외래 다음으로 정신과 입원에서 높은 비율이 나타남.

<br/>

<img width="400" alt="스크린샷 2021-05-13 오전 11 37 36" src="https://user-images.githubusercontent.com/75352728/118069720-9db69680-b3df-11eb-8df9-db7370fd2c50.png">

<img width="400" alt="스크린샷 2021-05-13 오전 11 37 18" src="https://user-images.githubusercontent.com/75352728/118069696-93949800-b3df-11eb-974f-892794985bd8.png">
출처 : 조선일보 / 저소득층 정신질환자 울리는 의료급여/ 이지혜 

<br/>

- 이러한 현상의 원인: 정신과의 진료비 제한으로 인해 조기에 치료를 할 수 없어 장기 입원을 하기 때문임.

<br/>

#### 9. 지역

<img width="400" alt="스크린샷 2021-05-13 오전 11 38 39" src="https://user-images.githubusercontent.com/75352728/118069788-c3dc3680-b3df-11eb-8012-de3054be301b.png">

- 서울 경기 :  높은 비율

<br/>

#### 10. 연령에 따라서

<br/>

#### 1. 주상병대분류 & 부상병 대분류

<img width="400" alt="스크린샷 2021-05-13 오전 11 39 50" src="https://user-images.githubusercontent.com/75352728/118069876-ee2df400-b3df-11eb-9e2e-920d3cace097.png">


<img width="400" alt="스크린샷 2021-05-13 오전 11 40 15" src="https://user-images.githubusercontent.com/75352728/118069920-fd14a680-b3df-11eb-955e-42fc2d72dddd.png">

- 정신질환: 신경계통 질환, 근골격 결합조직 질환, 대사질환, 소화계통 질환과 연관됨.

<br/>

## 조금 더 자세하게 알아보자.

##### 2. 주상병 이름 & 부상병 이름


<img width="400" alt="스크린샷 2021-05-13 오전 11 42 06" src="https://user-images.githubusercontent.com/75352728/118070080-3f3de800-b3e0-11eb-86c2-53efe9599545.png">

<img width="400" alt="스크린샷 2021-05-13 오전 11 42 16" src="https://user-images.githubusercontent.com/75352728/118070098-45cc5f80-b3e0-11eb-8659-36ed7bd6542c.png">

<img width="300" alt="스크린샷 2021-05-13 오전 11 42 34" src="https://user-images.githubusercontent.com/75352728/118070141-4fee5e00-b3e0-11eb-9f65-02414d6f03d2.png">
출처 :  연구보고서/nre2018-10_03.pdf

<br/>

- 정신질환: 소화계통과도 연관
- 소화계통: 정신질환과 연관

<br/>

## 조금 더 자세하게 알아보면~

#### 3. 주상병 & 부상병

<br/>

##### 1. F코드 포함

<img width="400" alt="스크린샷 2021-05-13 오전 11 55 00" src="https://user-images.githubusercontent.com/75352728/118071093-0d2d8580-b3e2-11eb-9094-e6aeb3452e0a.png">

<img width="400" alt="스크린샷 2021-05-13 오전 11 55 17" src="https://user-images.githubusercontent.com/75352728/118071111-16b6ed80-b3e2-11eb-82d6-20bd4c511991.png">
출처 : 건강보험심사평가원, 보건의료빅데이터개방 시스템

<br/>

- F코드에서 제일 높은 비중을 나타내는 13-19세 연령에서 반응성 우울증 단일 에피소드, ADHD, 기타 불안장애 순으로 높았음.
- 6-9세는 ADHD, 틱장애 순으로 10-12세는 ADHD, 틱장애, 반응성우울증의 단일 에피소드 순으로 나타남.

<br/>

##### 2. 주상병 분류(F코드 제외) & 부상병 분류(F코드 제외)

<img width="400" alt="스크린샷 2021-05-13 오전 11 44 27" src="https://user-images.githubusercontent.com/75352728/118070292-9348cc80-b3e0-11eb-9a2c-f5f7931564b3.png">

- 부상병분류코드 : F코드이면서 부상병도 F코드인 환자가 제일 많음.
- F코드를 제외한 다른 부상병분류코드 : 소화불량, 기타 약물유발 이차성 파킨슨병 상세불명의 위염 메네트리에병 순으로 높음
- 소화기관 질환 함께 발생.
- 기타 약물 유발 이차성 파킨슨병, 메네트리에병: 보통 유발연령이 장년층 이상에서 나타남.

<img width="400" alt="스크린샷 2021-05-13 오전 11 44 54" src="https://user-images.githubusercontent.com/75352728/118070323-a491d900-b3e0-11eb-8e07-6d9cc9d49ffc.png">
출처 : 통합 뇌질환학회

<br/>

- 약물유발 이차성 파킨슨병: 정신질환 약물 복용이 원인으로 발생

<img width="400" alt="스크린샷 2021-05-13 오전 11 45 23" src="https://user-images.githubusercontent.com/75352728/118070352-b4a9b880-b3e0-11eb-83c2-4043ef71a453.png">
출처 : 위키피디아

<br/>

- 메네트리에병 : 40-60세에 주로 발병, 소화장애와 연관

<br/>

#### 11. 성별에 따라서

<br/>

##### 1. 주상병 분류

<img width="400" alt="스크린샷 2021-05-13 오전 11 51 45" src="https://user-images.githubusercontent.com/75352728/118070830-97c1b500-b3e1-11eb-91c3-30a505d388e6.png">

- 남자 : 운동과다장애 즉 ADHD, 반응성 우울증의 단일 에피소드, 틱장애 순으로 높음
- 여자 : 반응성 우울증의 단일 에피소드, 운동과다장애, 기타 불안장애 순으로 높음.

<br/>

<img width="400" alt="스크린샷 2021-05-13 오전 11 52 18" src="https://user-images.githubusercontent.com/75352728/118070864-ac05b200-b3e1-11eb-811e-0d4603e1a69a.png">
출처 : 대한민국정책브리핑/소아.청소년에서 주로 발생하는 ‘틱장애’/보건복지부

<br/>

- 틱장애 : 여성보다 남성에서 많이 유발되는 질병

<img width="400" alt="스크린샷 2021-05-13 오전 11 52 37" src="https://user-images.githubusercontent.com/75352728/118070893-b758dd80-b3e1-11eb-9178-da2ac5c7c755.png">
출처: 연합뉴스/ 한해 ADHD 진료환자 5만3천명…"80% 남성, 57% 10대"/ 강애란 기자

<br/>

- ADHD : 여성보다 남성에서 많이 유발되는 질병

<br/>

#### 12. 입내원일수 차이

<img width="400" alt="스크린샷 2021-05-13 오후 12 00 35" src="https://user-images.githubusercontent.com/75352728/118071477-d441e080-b3e2-11eb-885c-e87236d57bef.png">

<img width="400" alt="스크린샷 2021-05-13 오후 12 01 02" src="https://user-images.githubusercontent.com/75352728/118071517-e459c000-b3e2-11eb-8b07-35e4c0803b00.png">
출처 : 서울대학교어린이병원 / 진료질환정보 조현병

<br/>

<img width="400" alt="스크린샷 2021-05-13 오후 12 01 19" src="https://user-images.githubusercontent.com/75352728/118071532-ee7bbe80-b3e2-11eb-817c-c8d25ce65852.png">
출처: 마인드 포스트 / [당사자 가족 칼럼] “청소년 정신질환 의심시 부모 동의 없이도 전문가 상담받도록 해야” / 배점태 심지회 부회장

<br/>

- 입내원일 수: 보통 1일이지만 조울반응과 조현병, 경도 정신저하는 입내원일수가 길었음
- 조현병은 입내원일수가 가장 길었음
- 조현병은 치료경과가 길기 때문.

<br/>

#### 13. 요양일수 차이

<img width="400" alt="스크린샷 2021-05-13 오후 12 05 59" src="https://user-images.githubusercontent.com/75352728/118071855-95605a80-b3e3-11eb-9840-cd5717b61984.png">

- 입내원일수와 같이 조현병등 조울반응등은 꾸준하게 치료와 경과 관찰이 필요하므로 요양일수가 높다.

<br/>

<img width="400" alt="스크린샷 2021-05-13 오후 12 06 33" src="https://user-images.githubusercontent.com/75352728/118071894-a9a45780-b3e3-11eb-9c39-8d0c214c44ce.png">

- 의료급여 그룹 : 중등도 정신장애이 높음을 알 수 있는데 소득 수준이 낮을 수록 값비싼 정신과 진료 비용으로 인해 초기에 치료를 할 수 없어, 질환이 심화 되기 떄문. 

<img width="400" alt="스크린샷 2021-05-13 오후 12 06 50" src="https://user-images.githubusercontent.com/75352728/118071919-b3c65600-b3e3-11eb-8152-4b0c31f6f9a1.png">
출처 : 주간경향 1427호 / [특집]소득격차는 호르몬을 따라 흐른다 / 김태훈기자

<br/>

- 행동장애: 소득이 낮은 가정에서 비교적 육아에 신경 쓰기 어려워 아이의 욕구가 충족되지 않아 아이의 스트레스 호르몬이 자주 분비되므로 ADHD가 많이 나타남.

<br/>
<br/>

## 임신, 출산, 산후 질환 (O, P 코드)

<br/>

#### 14. 연령

<img width="500" alt="스크린샷 2021-05-13 오후 12 38 17" src="https://user-images.githubusercontent.com/75352728/118074048-29ccbc00-b3e8-11eb-8d52-179e52a2aac1.png">

- 의료급여 그룹 군에서 높게 나타났던 O 코드(임신, 출산, 산후질환에 관련된 코드로 관련 질환) : 소득수준에 큰 영향을 미침.

<br/>

<img width="450" alt="스크린샷 2021-05-13 오후 12 40 41" src="https://user-images.githubusercontent.com/75352728/118074201-6e585780-b3e8-11eb-9691-f03782bfb1f2.png">

출처 : 조선비즈/ 경제수준차 따라 산모 건강도 극과 극…저소득층, 합병증 더 많아 / 허지윤기자

<br/>

<img width="450" alt="스크린샷 2021-05-13 오후 12 41 49" src="https://user-images.githubusercontent.com/75352728/118074293-96e05180-b3e8-11eb-969a-08d651d2811e.png">

- 저소득층 산모는 적절한 관리를 받지 못함 -> 신생아의 건강에 영향을 미침
- 교육의 미비 등으로 인한 저소득층 청소년의 임신 또한 발생가능
- 청소년 시기의 임신
	- 신체적인 영향 : 적혈구 감소, 미숙아를 출산하거나 조산할 확률이 높아짐.
	- 정신적인 영향 :  두려움, 우울

<br/>

#### 15. 입내원일

<img width="500" alt="스크린샷 2021-05-13 오후 12 44 00" src="https://user-images.githubusercontent.com/75352728/118074454-e58deb80-b3e8-11eb-8b7c-47b1c3e6a2a9.png">

- O코드와 P코드 두 질병 분류 :  전체에 비해 의료급여그룹이 장기간 입내원일 확률이 높음.

<br/>

#### 16. 주상병

<img width="500" alt="스크린샷 2021-05-13 오후 12 48 41" src="https://user-images.githubusercontent.com/75352728/118074780-a01dee00-b3e9-11eb-8c27-0edd4c580673.png">!

<br/>

#### 17. 부상병

<img width="500" alt="스크린샷 2021-05-13 오후 12 48 51" src="https://user-images.githubusercontent.com/75352728/118074791-a7dd9280-b3e9-11eb-9c7c-d43f99dbf3e6.png">

<br/>
<br/>

