# 텍스트 마이닝을 이용한 화장품 유통업체 O사 기초화장품 사용자의 리뷰 데이터 분석
<br>

## 📋 프로젝트 개요

본 연구는 온·오프라인 화장품 유통업체 O사 웹사이트의 기초 화장품 리뷰 데이터를 분석하여, 텍스트 마이닝 및 데이터 마이닝 기법을 활용한 마케팅 전략 수립 방법을 도출하는 것을 목표로 합니다.
<br>

### 🎯 연구 목적
- 화장품 리뷰 데이터에서 주요 키워드 추출 및 분석
- 브랜드별 고객 니즈 순위 파악
- 키워드와 브랜드 간의 유의미한 연관성 확인
- 마케팅 전략 및 신제품 개발을 위한 기초 자료 제공
<br>

## 📊 데이터셋

### 데이터 수집 정보
- **수집 기간**: 2024년 3월 29일 ~ 2024년 4월 16일
- **대상**: O사 웹사이트 기초화장품 리뷰
- **총 샘플 수**: 11,965개
  - 토너: 4,481개 (5개 브랜드)
  - 세럼: 3,420개 (5개 브랜드)  
  - 크림: 4,064개 (5개 브랜드)
- **수집 방법**: Scrapestorm 웹크롤러 활용

### 데이터 구성
- 사용자 닉네임, 재구매 여부, 별점, 리뷰 작성 날짜, 피부 고민, 자극도, 리뷰 내용
<br>

## 🛠️ 기술 스택

### 개발 환경
- **언어**: Python 3.8+
- **주요 라이브러리**:
  - `pandas`: 데이터 처리 및 분석
  - `numpy`: 수치 연산
  - `konlpy`: 한국어 자연어 처리
  - `scikit-learn`: 머신러닝 및 클러스터링
  - `matplotlib`, `seaborn`: 데이터 시각화
  - `wordcloud`: 워드클라우드 생성

### 분석 도구
- **텍스트 전처리**: KoNLPy의 Okt 형태소 분석기
- **키워드 추출**: KR-WordRank 알고리즘
- **통계 분석**: 분산분석 (ANOVA)
- **군집 분석**: K-means 클러스터링
- **시각화**: Elbow Method, 실루엣 분석
<br>

## 🔍 분석 방법론

### 1. 데이터 전처리
- 중복 리뷰 제거
- KoNLPy Okt 형태소 분석기를 이용한 명사 추출
- 불용어 제거 및 텍스트 정규화

### 2. 키워드 추출 및 항목화
- **KR-WordRank 알고리즘** 적용하여 중요도 기반 키워드 추출
- **5개 항목으로 분류**:
  - 기능성: 보습, 미백, 주름 개선 등
  - 제품 특성: 추천, 가격, 용량 등
  - 피부 타입: 건성, 지성, 민감성 등
  - 사용감: 흡수력, 무게감, 쿨링감 등
  - 피부 반응: 계절, 환절기, 자극 등

### 3. 통계 분석
- **분산분석(ANOVA)**: 키워드와 브랜드 간 유의성 검정
- **유의수준**: p < 0.05(*), p < 0.01(**), p < 0.001(***)

### 4. 군집 분석
- **K-means 클러스터링**: 브랜드 간 유사성 분석
- **최적 군집 수 결정**: Elbow Method + 실루엣 분석
- **결과**: 유사한 마케팅 포지션을 가진 브랜드들이 동일 군집으로 분류
<br>

## 📈 주요 연구 결과

### 분산분석 결과
- **토너**: p-value = 1.19e-06 (***) - 키워드와 브랜드 간 강한 연관성
- **세럼**: p-value = 0.00205 (**) - 유의미한 연관성 확인
- **크림**: p-value = 0.04512 (*) - 통계적 유의성 확인

### 군집분석 결과
| 제품군 | 최적 군집 수 | 실루엣 점수 | 주요 특징 |
|--------|--------------|-------------|-----------|
| 토너 | 3 | 0.39 | 제품 특성 중심 vs 기능성 중심 vs 피부타입별 특화 |
| 세럼 | 4 | 0.15 | 기능성 + 추가 차별화 요소별 군집 형성 |
| 크림 | 2 | 0.43 | 다기능 제품 vs 수분 특화 제품 |

### 브랜드별 키워드 순위
각 제품군별로 브랜드마다 소비자가 중요하게 여기는 키워드 항목의 순위가 다르게 나타남:
- **1순위**: 대부분 브랜드에서 '기능성'이 최우선
- **차별화 요소**: 제품 특성, 사용감, 피부 반응 등에서 브랜드별 차이 발생
<br>

## 🎯 마케팅 전략 제안

### STP 전략 수립
연구 결과를 바탕으로 제품 유형별 타겟 세분화 및 포지셔닝 전략 제시:

#### 토너
- **타겟**: 10대 후반~30대 초반, 다양한 피부타입
- **포지셔닝**: 수분감 + 저자극 + 가성비

#### 세럼
- **타겟**: 20대 직장인, 특정 피부 고민 보유자
- **포지셔닝**: 핵심 성분 고농축 + 기능성 특화

#### 크림
- **타겟**: 전 연령대, 피부타입별 세분화
- **포지셔닝**: 다기능 vs 수분 특화 전략
<br>

## 📊 결과 해석

### 주요 인사이트
1. **기능성 우선**: 모든 제품군에서 기능성 키워드가 최우선 순위
2. **브랜드별 차별화**: 제품 특성, 사용감 등에서 브랜드만의 강점 확인
3. **군집별 전략**: 유사한 포지셔닝을 가진 브랜드들의 경쟁 관계 파악
4. **타겟별 접근**: 제품군별로 다른 고객 니즈와 선호도 확인

### 활용 방안
- **신제품 개발**: 시장 gap 분석을 통한 차별화 포인트 발굴
- **마케팅 전략**: 타겟별 맞춤형 메시지 및 채널 전략 수립
- **포지셔닝**: 경쟁사 대비 차별적 브랜드 가치 제안
<br>

## 👥 팀 정보

**프로젝트 기간**: 6개월 (2024.03 - 2024.08)

**팀 구성**: 3명

**맡은 역할**: 데이터 수집 및 전처리, 키워드 추출 및 분석, 시각화,통계 분석
<br>

## 📚 참고문헌

본 연구는 다음 학술지에 게재되었습니다:
- **학술지**: 빅데이터서비스학회 논문집
- **권호**: 제2권 제2호 (2024)
- **페이지**: 5-19
- **DOI**: https://doi.org/10.61241/KBDSS.02.02.01
