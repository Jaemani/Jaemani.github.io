---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---

# 이재만

**컴퓨터소프트웨어학부**  
**한양대학교**, 서울  


leejaeman0227@gmail.com  
+82-10-5892-2434  
[GitHub](https://github.com/Jaemani)

---

## 교육

**한양대학교**, 한국  
컴퓨터소프트웨어학부 학부생, 2학년  
_졸업예정 년도: 2028년_

---

## 기술 스택

**Languages**: Python, JavaScript, C/C++, Dart  
**Frameworks**:  
&emsp; **Frontend**: Flutter, React  
&emsp; **Backend**: Node.js, Next.js, Express, Firebase, AWS, GCP  
&emsp; **AI/ML**: PyTorch

---

## 프로젝트 & 연구

### 한울림 동아리용 앱 개발 - 백엔드 개발자
_2021 6월 – 2021 11월_ 🔗 [GitHub Repo](https://github.com/Jaemani/Hanwoollim-Server)

- 한울림 대학 동아리용 앱에 대해 독립적으로 RESTful API 서버를 개발하고 배포
- MySQL 스키마를 Sequelize ORM을 활용해 디자인
- JWT 와 Bcrypt.js 기반으로 보안 로그인 구현
- AWS (EC2, RDS)에 NGINX로 프록시 관리를 활용하여 배포

### WorldQuant Summer Bootcamp – 퀀트 알파 팩터 개발 프로젝트
_2024년 7월 – 8월_ 🔗 [발표자료](https://drive.google.com/file/d/1LUGGo68bG_dL4U_X9qY-90_mbCCLKJF7/view?usp=sharing)

- 휴먼-머신 하이브리드 접근법을 통한 글로벌 알파 팩터 개발 및 최적화 시스템 구축
- 30,750개 알파 데이터 분석을 통한 독자적 Scoring 알고리즘 개발: Sharpe ≥ 1인 3,081개 알파의 회귀분석으로 Turnover, Returns, Drawdown 기반 평가 공식 도출
- 4개 알파 템플릿 설계 및 구현: 딥러닝 예측 지표 기반 경기침체 대응 알파, MACD 기반 세력 움직임 감지 알파, 옵션 변동성 활용 알파, Williams %R 지수 활용 과매수/과매도 감지 알파
- TF-IDF 기반 데이터필드 클러스터링으로 variance 최대화 및 parameter 개수 최소화를 통한 효율적 탐색 구현
- WorldQuant Brain API 및 ACE Library를 활용한 시뮬레이션 자동화 파이프라인 구축: 수동 파라미터 조정 → API 자동화 → 클러스터링 최적화 → 알파 믹싱 4단계 발전
- VIF(Variance Inflation Factor) 검증을 통한 다중공선성 확인 및 모델 안정성 검증 (VIF < 1.13)
- 알파 믹싱을 통한 앙상블 모델로 최고 성능 8.4‱ margin, 2.34 fitness score 달성 (기초 대비 심화/믹싱 30% 성능 향상)
- 강건성 검증을 위한 하이퍼파라미터 스위핑 및 알파 세분화 테스트로 오버피팅 방지 및 일반화 성능 확보
- 국가 중립화(Country Neutralization) 전략을 통한 글로벌 리스크 관리 및 포트폴리오 다변화 효과 분석

### WakeUp 앱 – 실시간 눈 감음 감지 모델 *(구글 머신러닝 부트캠프 대상)*
_2024 8월 – 2024 10월_ 🔗 [GitHub Repo](https://github.com/Jaemani/wakeup_app)

- 실시간 졸음감지 시스템을 개발하고 Flutter + Firebase를 활용하여 모바일 배포
- end-to-end ML 파이프라인 구축: 눈 이미지 수집, 저화질 이미지 제거, 배경제거 및 augmentation(9,200장의 이미지)
- precision, recall, mAP와 모바일 딜레이 성능지표을 위해 4가지 모델 평가 및 비교(YOLOv5n, v5s, v8n, v8s)
- 초기에 EfficientDet-lite**, OpenCV + CNN, and CenterNet을 탐색했으나 높은 리소스 사용과 확장성 문제로 기각
- 데이터 전처리과 모델 튜닝을 통해 탐지 신뢰도를 40%에서 99%까지 끌어올림
- 모바일에서 실시간 작동과 정확도에 최적화된 flutter_vision과 YOLOv5n 모델을 채택
- 지리좌표 기반으로 위험경고를 하고 Firestore에 로그하는 기능 구현
- 미래 확장성을 위해 Gemini 기반으로 사용자 커스텀 경고 메시지를 주는 기능 구현(부분 구현, 미완료)

### 수리수리 마수리 – 수리이력 관리 시스템 - 백엔드 개발자 *(카카오임팩트 테크포임팩트 사회가치상)*
_2025 3월 – 2025 6월_ 🔗 [Github Repo](https://github.com/techforimpact-archive/TFI_CAMPUS_HANYANG_25Spring_Soori-soori) / [Notion](https://jaeman-hyu.notion.site/1c4ec4b6449b80bca4f2d6413eb7e8ef?pvs=4)  
*본 서비스는 카카오임팩트의 기술 이니셔티브 [테크포임팩트](https://techforimpact.io/) 의 지원으로 개발되었습니다.*  

- 사회복지관과 연계된 QR기반 수리기록 관리 플랫폼
- Next.js, Firebase Auth, MongoDB를 활용하여 역할별 접근권한, 실시간 기록관리 및 추적 구현
- Led infrastructure setup and system integration
- 펠로우 역할인 AIoT 기반 사고감지 서비스 운영중인 [별따러가자](https://starpickers.imweb.me/)와 연계할 수 있는 프로젝트

### 회귀 기반으로 MNIST 숫자 예측 *(추가 학습)*
_2025 4월 – 2025 5월_ 🔗 [Notion Page](https://jaeman.notion.site/MNIST-via-Regression-1e95d7580ec180abaee4e429b7bb93bf?pvs=73)

- TensorFlow/Keras를 사용하여 회귀 기반으로 하는 MLP, CNN 기반 모델 아키텍처 설계
- 이산적인 분류가 아닌 연속적인 값으로 회귀 예측결과가 나올 수 있도록 조정
- CNN을 거쳐 회귀를 진행한 작업과 일반 회귀작업과의 결과 분석

### 웹과 모바일 결제를 위한 XRP Payment SDK 개발 *(진행중)*  
_2025 4월 – 현재_  
*HYBLOCK (한양대학교 블록체인학회)와 [XRPL Korea](https://www.xrplkorea.org/)의 산학연계 프로젝트.*  

- Xaman 플랫폼을 통해 XRP Payment를 사용할 수 있는 SDK 모듈 설계
- 보안을 위한 자체 API 키 발급 및 관리
- 파트너 채택을 위한 프론트엔드 문서 제공(Uniport platform)
- HYBLOCK 와 XRPL Korea 매주 주간회의를 거쳐 진행상황 공유

### SK AI Dream Camp *(진행예정)*
_2025 7월 - 2025 8월_

- SK 멤버사(SK 하이닉스, SK 텔레콤)의 현장 데이터를 활용하여 진행되는 AI/ML 역량강화 프로젝트
- 실무 경험을 통한 모델링 및 분석에 중점을 둔 종합 프로젝트 수행
- 통신 ICT 인프라 프로젝트: 기지국 장비 성능 통계에 대한 EDA 수행 및 시계열 머신러닝 기법을 활용한 ICT 인프라 장애 식별을 위한 이상 탐지 모델 개발
- 반도체 공정 최적화: SK하이닉스 반도체 공정 데이터를 활용한 머신러닝 예측 모델 개발, 특히 포토(노광) 공정 지표를 활용한 패키지 테스트 결과 예측 모델 제작
- 탐색적 데이터 분석(EDA), 시계열 이상 징후 탐지, 산업 애플리케이션 예측 모델링에 대한 전문성 확보

---

## 활동 & 성과
- **HYBLOCK – 한양대학교 블록체인 학회 (2024 – 현재)**
블록체인에 대해서 깊이 탐구하고 리서치/개발을 진행하는 한양대학교 소속 학회.
  - 개발팀 멤버로 참여하여 블록체인 기초, 스마트 컨트랙트 설계, dApp 구현에 대해 학습
  - 솔리디티, Hardhat, Infura, 메타마스크, ERC-20 토큰 컨트랙트를 사용하여 테스트넷 기반 Polymarket(예측시장) 시스템 구축
  - 이더스캔을 통한 계약 검증 등 계약보안 같은 고급 주제에 대해서 다룸
  - 실제 XRP 결제 SDK 구현 프로젝트 등 XRPL Korea와 협력
- **Google ML Bootcamp (2024)** – 3기 멤버
Google ML 부트캠프의 일환 전처리와 모델 훈련부터 앱 구현까지 으로풀스택 ML 모바일 앱 개발.
- **Regular ML self-study**: 캐글 연습 (regression, classification, CV 등)
- **Kakao Impact Tech for Impact(2025)** - Campus Hanyang University & Yonsei University
카카오임팩트 재단에서 실시한 교육과정. 임팩트 사업 스타트업 별따러가자와 팰로우십 관계로 복지관과 협업하여 전동보장구 수리기록 관리 시스템 구현. 관리자 대시보드와 백엔드 시스템 담당. 지원을 받아 후속개발 참여 예정.  

---

## 증서 & 수료증

### 2023

- **Kakao Enterprise X goorm:** 군 장병 맞춤형 온라인 AI·SW 교육 프로그램 인공지능 중급과정 I
- **Kakao Enterprise X goorm:** 군 장병 맞춤형 온라인 AI·SW 교육 프로그램 인공지능 중급과정 II

### 2024  

- **WorldQuant BRAIN Platform:** Quantitative Finance INTERMEDIATE LEVEL

- **Google Korea ML Bootcamp (2024, 3기):** 대상
최종 성과 발표에서 기술적 깊이, 완성도, 임팩트등 종합적인 지표 고려하여 탑 프로젝트로 선정됨. Google Korea 와 정보통신산업진흥원이 주최한 실무 AI/ML 팀 프로젝트.  

### 2025  

- **XRPL KOREA Blockchain Hackathon DE-BUTHON**
- **Kakao Impact Tech for Impact**: 사회가치상
