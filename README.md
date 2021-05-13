
# 청소년의 질병 예측
machine learning project

<img width="450" alt="스크린샷 2021-03-26 오후 2 58 02" src="https://user-images.githubusercontent.com/75352728/117994274-61514f00-b37b-11eb-9633-a3872c057ba4.png">


*그림 출처 : freepik

***
## 1. INTRO

### 1-1 개요
- 뇌과학연구소가 제공한 2018년 데이터를 활용한 머신러닝 프로젝트입니다.
- 본 프로젝트에서는 청소년의 질병 예측과 소득에 따른 청소년의 질병 행태를 분속하였습니다.
- 본 프로젝트의 목적은 EDA를 통한 소득에 따른 청소년의 질병 형태를 분석하고 정신질환 코드를 예측하는 최적의 모델을 찾음에 있습니다.

### 1-2 데이터
1 출처
  - 뇌과학연구소
  
2. 데이터 구성
  - 명세서 일반 내역
    - Data 갯수 : 약 1570만개
    - 컬럼 수 : 28개
    - 구성
      - 명세서조인키(진료내역, 상명내역, 원외처방내역과 조인키)
      - 보험자 구분코드
      - 수진자식별대체키
      - 성별구분코드
      - 수진자연령군
      - 소아청소년연령군
      - 추출확률
      - 샘플가중치
      - 요양기관식별대체키(요약기관현황정보와 조인키)
      - 서식코드
      <img width="256" alt="스크린샷 2021-05-13 오전 10 32 51" src="https://user-images.githubusercontent.com/75352728/118064786-a9518f80-b3d6-11eb-8136-868187b6c6fb.png">

      - 주상병명
      - 부상병명
      
      <img width="339" alt="스크린샷 2021-05-13 오전 10 13 19" src="https://user-images.githubusercontent.com/75352728/118063328-d81a3680-b3d3-11eb-9d2f-3a3360214286.png">

      - 진료과목코드
      
      <img width="290" alt="스크린샷 2021-05-13 오전 10 16 12" src="https://user-images.githubusercontent.com/75352728/118063532-3f37eb00-b3d4-11eb-88a4-acf67c49ac40.png">

      - 표시과목코드
      
      <img width="227" alt="스크린샷 2021-05-13 오전 10 14 13" src="https://user-images.githubusercontent.com/75352728/118063393-f849f580-b3d3-11eb-8b0b-c0987b92eac3.png">

      - 내과세부과목코드
      
      <img width="126" alt="스크린샷 2021-05-13 오전 10 14 25" src="https://user-images.githubusercontent.com/75352728/118063405-013ac700-b3d4-11eb-9c87-b18a0aae6f95.png">

      - 요양개시일자(진료 시작 일자)
      - 요양종료일자(진료 종료 일자)
      - 최초입원날짜(최초 내원 날짜)
      - 입내원일수(진료받기 위해 요양기관에 내원한 일수) 
      - 요양일수(수진자를 치료한 총 일수(투약일수 포함))
      - 심사결정요양급여비용총액금액
      - 심사결정보험자부담금액
      - 심사결정 100분의 100미만 총액
      - 수술여부
        - 비수술, 수술
      - 진료결과구분코드
        - 계속, 이송, 회송, 사망, 기타, 퇴원
      - 도착경로 + 입원도착경로
        - 타기관경유, 응급구조대, 기타 입원경로(응급실, 외래)
      - 질병군(DRG) 청구 번호
 
  - 진료 내역
    - 데이터 갯수 : 약 5400만개
    - 컬럼수 : 15개
    - 구성
      - 명세서 조인키
      - 줄번호
      - 항목코드
      - 분류코드구분
     
     <img width="290" alt="스크린샷 2021-05-13 오전 10 18 31" src="https://user-images.githubusercontent.com/75352728/118063702-92aa3900-b3d4-11eb-8d3a-89f9119cca2b.png">
      
      - 분류코드 (수가, 약가, 재료대 코드)
      - 1회투약량
      - 1일투약량
      - 1일투여량실시횟수
      - 총투여일수실시횟수
      - 총사용량 또는 실시횟수
        - 1회 투여량 * 1일 투여량 * 총 투여일수 또는 실시횟수
      - 분류코드별 단가
      - 단가 * 총사용량
      - 가산율적용금액
      - 약주성분코드

  - 상병내역
    - 데이터 갯수 : 약 4500만개
    - 컬럼 수 : 5개
    -  구성
      -  명세서 조인키
      -  수진자 상병일련번호
      -  청구진료과목코드
      -  주상병코드
      
  - 원외처방내역
    - 데이터 갯수 : 약 4700만개
    - 컬럼 수 : 10개
    - 구성
      - 명세서 조인키
      - 줄번호
      - 1회투약량
      - 1일투약량
      -  총투여일수실시횟수
      -  총 사용량 또는 실시횟수
        - 1회 투여량 * 1일 투여량 * 총 투여일수 또는 실시횟수
        - 단가 
        - 단가 * 총사용량
        - 등재약의 성분코드
        
   - 요양기관현황정보
    - 데이터 갯수 : 약 4700만개
    - 컬럼 수 : 10개  
    - 구성
      - 요양기관식별대체키
      - 시도코드
      - 요양기관종별코드

      <img width="341" alt="스크린샷 2021-05-13 오전 10 25 43" src="https://user-images.githubusercontent.com/75352728/118064224-95595e00-b3d5-11eb-979d-b9e8b91219b6.png">
      
      - 병상등급
      
      <img width="341" alt="스크린샷 2021-05-13 오전 10 26 13" src="https://user-images.githubusercontent.com/75352728/118064271-a609d400-b3d5-11eb-8311-3aa95d03a47a.png">
      
      - 50병상당의사수
		    - 총 의사수 / 총 병상수 x 50
      - 50병상당치과의사수
			  - 총 치과의사수 / 총 병상수 x 50
			- 50병상당한의사수
			  - 총 한의사수 / 총 병상수 x 50
      - 50병상당 간호사 수
        - 총 긴호수 / 총 병상수 x 50

<br/>

### 1-3 팀원 / 역할
- [고원진]
  -  https://github.com/
  -  
- [이주영]
  - https://github.com/leekj3133
  - 데이터 확장자 변환(parquet), 데이터 전처리, EDA

*****

<br/>

## 2. Result


## 3. PROCESS

데이터 확장자 변경 -> 데이터 전처리 -> EDA -> 모델 학습과 예측 평가 -> 모델 검증

<br/>

### 3-1 데이터 전처리

#### 1. 용량 줄이기

- 용량이 큰 데이터이기 떄문에 용량이 작은 데이터로 바꿔야함
- object 데이터 타입을 category 타입으로 변환 
- csv 파일을 parquet으로 변환
	- df.to_parquet('경로/파일이름.parquet')
	- df = pd.read_parquet('./경로/파일이름.parquet', engine='pyarrow') 
	
#### 2. 데이터 mapping

- 코드로 이루어진 데이터 EDA를 위해 한글로 mapping 

### 3-2 시각화

#### 1. 병원

<img width="391" alt="스크린샷 2021-05-13 오전 11 00 08" src="https://user-images.githubusercontent.com/75352728/118066844-62fe2f80-b3da-11eb-996d-66460bdcbfc0.png">

- 의료법 시행규칙에 명시되어 있는 것처럼 요양기관의 종류에 따라 법률에 명시된 병상 수 
- 즉 병원 베드 수, 의사, 치과의사, 한의사, 간호사 수나 그 이상을 둘 수 있습니다.
- 5가지 컬럼 대신 요양기관의 종류를 사용


<img width="307" alt="스크린샷 2021-05-13 오전 11 02 12" src="https://user-images.githubusercontent.com/75352728/118067010-ac4e7f00-b3da-11eb-953c-012787e2afa3.png">
출처 : 경북일보 / 폭염에 노출된 임산부, 저체중아 출산…소득 낮을수록 위험 / 류진희 기자


<img width="338" alt="스크린샷 2021-05-13 오전 11 04 09" src="https://user-images.githubusercontent.com/75352728/118067141-f20b4780-b3da-11eb-9156-b52b7b5e07a0.png">
출처 : 마인드 포스트 / 정신질환자 의료급여 수준 건강보험의 58%…'행위별 수가제'로 전환해야 / 박종언 기자


## 소득에 따라 질병에 차이가 많다!! 소득 관련해서 알아보자!!

<img width="485" alt="스크린샷 2021-05-13 오전 11 06 04" src="https://user-images.githubusercontent.com/75352728/118067290-3696e300-b3db-11eb-9149-5419dd41d67f.png">

- 의료급여 비율 
	1. 임신, 출산, 산후 질환 (O, P 코드)
	2. 신경계 질환 (G 코드)
	3. 정신 및 행동장애 (F코드)
	
<img width="371" alt="스크린샷 2021-05-13 오전 11 12 34" src="https://user-images.githubusercontent.com/75352728/118067742-1f0c2a00-b3dc-11eb-95d9-1d8fd68bdaac.png">

- 의료급여 중 주상병과 부상병의 비율
	- F 코드 :  K 코드 소화기 계통과 연관
	- G 코드 : F 코드 정신질환과 연관
	- P 코드 : Q 코드 기형, 선천적이상, 유전병과 연관

#### 2. 연령

<img width="205" alt="스크린샷 2021-05-13 오전 11 28 54" src="https://user-images.githubusercontent.com/75352728/118069045-672c4c00-b3de-11eb-8b36-5e068541853a.png">

- 전체 비율과 비교하였을 때 13-19세 의료급여 비율이 다른 연령보다 현저히 높게 나타남

#### 3. 지역

<img width="320" alt="스크린샷 2021-05-13 오전 11 30 03" src="https://user-images.githubusercontent.com/75352728/118069135-90e57300-b3de-11eb-9030-c25f68a47643.png">

- 서울 경기에 비율이 높음을

#### 4. 월

<img width="221" alt="스크린샷 2021-05-13 오전 11 30 32" src="https://user-images.githubusercontent.com/75352728/118069169-a22e7f80-b3de-11eb-8fa5-395118feaebc.png">

#### 5. 주상병 이름

<img width="221" alt="스크린샷 2021-05-13 오전 11 30 57" src="https://user-images.githubusercontent.com/75352728/118069195-b07c9b80-b3de-11eb-9840-f591d49e5e49.png">

- 의료급여와 전체를 비교하였을 때 전체에서 볼 수 없었던 소아기 및 청소년기 행동 및 정서장애가 상위 10개의 10개의 상병안에 포함되어있음
- 의료급여에서 정신질환이 높은 비율이 나타남을 알 수 있음

#### 6. 부상병 이름

<img width="233" alt="스크린샷 2021-05-13 오전 11 32 17" src="https://user-images.githubusercontent.com/75352728/118069286-e02ba380-b3de-11eb-9c09-b7cd759fe22c.png">

- 전체와 의료급여를 비교했을 떄 기분 장애, 소아청소년기 행동 정서 장애 등이 상위 10개 상병에 포함됨.
- 기분 장애, 소아청소년기 행동 정서 장애 : F코드인 정신질환에 포함되는 상병
- 의료급여에서 정신질환 비율이 높은 것을 알 수 있음.

## 의료급여에서 정신질환이 높은 확률이 나타나는 것을 알 수 있다. 정신질환(F코드)에 대해 알아보자!

## 정신질환 (F코드)

#### 7. 연령

<img width="233" alt="스크린샷 2021-05-13 오전 11 34 56" src="https://user-images.githubusercontent.com/75352728/118069477-3e588680-b3df-11eb-9301-4192b406c666.png">

- 정신질환 코드 : 청소년의 비율이 현저히 높음
- 전체, 의료급여 청소년 비울이 높음

#### 8. 병원

<img width="233" alt="스크린샷 2021-05-13 오전 11 36 24" src="https://user-images.githubusercontent.com/75352728/118069622-752e9c80-b3df-11eb-8ab1-ce628e4465d8.png">

- 의료급여 그룹: 외과외래 다음으로 정신과 입원에서 높은 비율이 나타남.

<img width="265" alt="스크린샷 2021-05-13 오전 11 37 36" src="https://user-images.githubusercontent.com/75352728/118069720-9db69680-b3df-11eb-8df9-db7370fd2c50.png">

<img width="313" alt="스크린샷 2021-05-13 오전 11 37 18" src="https://user-images.githubusercontent.com/75352728/118069696-93949800-b3df-11eb-974f-892794985bd8.png">
출처 : 조선일보 / 저소득층 정신질환자 울리는 의료급여/ 이지혜 


- 이러한 현상의 원인: 정신과의 진료비 제한으로 인해 조기에 치료를 할 수 없어 장기 입원을 하기 때문임.

#### 9. 지역

<img width="386" alt="스크린샷 2021-05-13 오전 11 38 39" src="https://user-images.githubusercontent.com/75352728/118069788-c3dc3680-b3df-11eb-8012-de3054be301b.png">

- 서울 경기 :  높은 비율

#### 10. 연령에 따라서

#### 1. 주상병대분류 & 부상병 대분류

<img width="273" alt="스크린샷 2021-05-13 오전 11 39 50" src="https://user-images.githubusercontent.com/75352728/118069876-ee2df400-b3df-11eb-9e2e-920d3cace097.png">


<img width="273" alt="스크린샷 2021-05-13 오전 11 40 15" src="https://user-images.githubusercontent.com/75352728/118069920-fd14a680-b3df-11eb-955e-42fc2d72dddd.png">

- 정신질환: 신경계통 질환, 근골격 결합조직 질환, 대사질환, 소화계통 질환과 연관됨.

## 조금 더 자세하게 알아보자.

##### 2. 주상병 이름 & 부상병 이름


<img width="273" alt="스크린샷 2021-05-13 오전 11 42 06" src="https://user-images.githubusercontent.com/75352728/118070080-3f3de800-b3e0-11eb-86c2-53efe9599545.png">

<img width="220" alt="스크린샷 2021-05-13 오전 11 42 16" src="https://user-images.githubusercontent.com/75352728/118070098-45cc5f80-b3e0-11eb-8659-36ed7bd6542c.png">

<img width="192" alt="스크린샷 2021-05-13 오전 11 42 34" src="https://user-images.githubusercontent.com/75352728/118070141-4fee5e00-b3e0-11eb-9f65-02414d6f03d2.png">

- 정신질환: 소화계통과도 연관
- 소화계통: 정신질환과 연관

## 조금 더 자세하게 알아보면~

#### 3. 주상병 & 부상병

##### 1. F코드 포함

<img width="413" alt="스크린샷 2021-05-13 오전 11 55 00" src="https://user-images.githubusercontent.com/75352728/118071093-0d2d8580-b3e2-11eb-9094-e6aeb3452e0a.png">

<img width="417" alt="스크린샷 2021-05-13 오전 11 55 17" src="https://user-images.githubusercontent.com/75352728/118071111-16b6ed80-b3e2-11eb-82d6-20bd4c511991.png">

- F코드에서 제일 높은 비중을 나타내는 13-19세 연령에서 반응성 우울증 단일 에피소드, ADHD, 기타 불안장애 순으로 높았음.
- 6-9세는 ADHD, 틱장애 순으로 10-12세는 ADHD, 틱장애, 반응성우울증의 단일 에피소드 순으로 나타남.

##### 2. 주상병 분류(F코드 제외) & 부상병 분류(F코드 제외)

<img width="358" alt="스크린샷 2021-05-13 오전 11 44 27" src="https://user-images.githubusercontent.com/75352728/118070292-9348cc80-b3e0-11eb-9a2c-f5f7931564b3.png">

- 부상병분류코드 : F코드이면서 부상병도 F코드인 환자가 제일 많음.
- F코드를 제외한 다른 부상병분류코드 : 소화불량, 기타 약물유발 이차성 파킨슨병 상세불명의 위염 메네트리에병 순으로 높음
- 소화기관 질환 함께 발생.
- 기타 약물 유발 이차성 파킨슨병, 메네트리에병: 보통 유발연령이 장년층 이상에서 나타남.

<img width="545" alt="스크린샷 2021-05-13 오전 11 44 54" src="https://user-images.githubusercontent.com/75352728/118070323-a491d900-b3e0-11eb-8e07-6d9cc9d49ffc.png">

- 약물유발 이차성 파킨슨병: 정신질환 약물 복용이 원인으로 발생

<img width="518" alt="스크린샷 2021-05-13 오전 11 45 23" src="https://user-images.githubusercontent.com/75352728/118070352-b4a9b880-b3e0-11eb-83c2-4043ef71a453.png">

- 메네트리에병 : 40-60세에 주로 발병, 소화장애와 연관

#### 11. 성별에 따라서

##### 1. 주상병 분류

<img width="390" alt="스크린샷 2021-05-13 오전 11 51 45" src="https://user-images.githubusercontent.com/75352728/118070830-97c1b500-b3e1-11eb-91c3-30a505d388e6.png">

- 남자 : 운동과다장애 즉 ADHD, 반응성 우울증의 단일 에피소드, 틱장애 순으로 높음
- 여자 : 반응성 우울증의 단일 에피소드, 운동과다장애, 기타 불안장애 순으로 높음.

<img width="519" alt="스크린샷 2021-05-13 오전 11 52 18" src="https://user-images.githubusercontent.com/75352728/118070864-ac05b200-b3e1-11eb-811e-0d4603e1a69a.png">

- 틱장애 : 여성보다 남성에서 많이 유발되는 질병

<img width="528" alt="스크린샷 2021-05-13 오전 11 52 37" src="https://user-images.githubusercontent.com/75352728/118070893-b758dd80-b3e1-11eb-9178-da2ac5c7c755.png">

- ADHD : 여성보다 남성에서 많이 유발되는 질병

#### 12. 입내원일수 차이

<img width="344" alt="스크린샷 2021-05-13 오후 12 00 35" src="https://user-images.githubusercontent.com/75352728/118071477-d441e080-b3e2-11eb-885c-e87236d57bef.png">

<img width="486" alt="스크린샷 2021-05-13 오후 12 01 02" src="https://user-images.githubusercontent.com/75352728/118071517-e459c000-b3e2-11eb-8b07-35e4c0803b00.png">

<img width="514" alt="스크린샷 2021-05-13 오후 12 01 19" src="https://user-images.githubusercontent.com/75352728/118071532-ee7bbe80-b3e2-11eb-817c-c8d25ce65852.png">
출처: 마인드 포스트


- 입내원일 수: 보통 1일이지만 조울반응과 조현병, 경도 정신저하는 입내원일수가 길었음
- 조현병은 입내원일수가 가장 길었음
- 조현병은 치료경과가 길기 때문.

#### 13. 요양일수 차이

<img width="327" alt="스크린샷 2021-05-13 오후 12 05 59" src="https://user-images.githubusercontent.com/75352728/118071855-95605a80-b3e3-11eb-9840-cd5717b61984.png">

- 입내원일수와 같이 조현병등 조울반응등은 꾸준하게 치료와 경과 관찰이 필요하므로 요양일수가 높다.

<img width="327" alt="스크린샷 2021-05-13 오후 12 06 33" src="https://user-images.githubusercontent.com/75352728/118071894-a9a45780-b3e3-11eb-9c39-8d0c214c44ce.png">

- 의료급여 그룹 : 중등도 정신장애이 높음을 알 수 있는데 소득 수준이 낮을 수록 값비싼 정신과 진료 비용으로 인해 초기에 치료를 할 수 없어, 질환이 심화 되기 떄문. 

<img width="351" alt="스크린샷 2021-05-13 오후 12 06 50" src="https://user-images.githubusercontent.com/75352728/118071919-b3c65600-b3e3-11eb-8152-4b0c31f6f9a1.png">

- 행동장애: 소득이 낮은 가정에서 비교적 육아에 신경 쓰기 어려워 아이의 욕구가 충족되지 않아 아이의 스트레스 호르몬이 자주 분비되므로 ADHD가 많이 나타남.

## 임신, 출산, 산후 질환 (O, P 코드)

#### 14. 연령



## 4. CONCLUSION

## 5. comment & limitations


