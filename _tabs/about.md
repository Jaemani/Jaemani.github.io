---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---

# Jaeman Lee

**Undergraduate Student, Department of Computer Science**  
**Hanyang University**, South Korea


leejaeman0227@gmail.com  
+82-10-5892-2434  
[GitHub](https://github.com/Jaemani)

---

## Education

**Hanyang University**, South Korea  
Bachelor of Science in Computer Science Engineering (Sophomore)  
_Expected Graduation: Feb 2028_

---

## Technical Skills

**Languages**: Python, JavaScript, C/C++, Dart  
**Frameworks**:  
&emsp; **Frontend**: Flutter, React  
&emsp; **Backend**: Node.js, Next.js, Express, Firebase, AWS, GCP  
&emsp; **AI/ML**: PyTorch

---

## Projects & Research

### Hanwoollim Member App - Backend Developer
_Jun 2021 – Nov 2021_ 🔗 [GitHub Repo](https://github.com/Jaemani/Hanwoollim-Server)

- Independently developed and deployed a production-ready RESTful API server for a university club app.
- Designed scalable MySQL schemas using Sequelize ORM
- Implemented secure login and authentication with JWT and Bcrypt.js
- Deployed on AWS (EC2, RDS) with NGINX for reverse proxy and process management
- Created clear API documentation for users and admins using SwaggerHub

### WorldQuant Summer Bootcamp – Quantitative Alpha Factor Development
_Jul 2024 – Aug 2024_ 🔗 [Presentation](https://drive.google.com/file/d/1LUGGo68bG_dL4U_X9qY-90_mbCCLKJF7/view?usp=sharing)

- Developed a human-machine hybrid alpha factor development and optimization system for global markets
Built proprietary scoring algorithm through analysis of 30,750 alpha data points: derived evaluation formula based on Turnover, Returns, and Drawdown metrics via regression analysis of 3,081 high-performance alphas (Sharpe ≥ 1)
- Designed and implemented 4 alpha templates: deep learning prediction-based recession response alpha, MACD-based institutional movement detection alpha, option volatility-based alpha, and Williams %R overbought/oversold detection alpha
- Implemented efficient parameter exploration using TF-IDF-based datafield clustering to maximize variance while minimizing parameter count
- Built automated simulation pipeline using WorldQuant Brain API and ACE Library: progressed through 4 development stages from manual parameter tuning → API automation → clustering optimization → alpha mixing
- Validated model stability through VIF (Variance Inflation Factor) testing for multicollinearity (VIF < 1.13)
- Achieved best performance of 8.4‱ margin and 2.34 fitness score through alpha mixing ensemble models (30% improvement over basic vs. advanced/mixing)
- Implemented robustness validation through hyperparameter sweeping and alpha segmentation testing to prevent overfitting and ensure generalization
- Analyzed global risk management and portfolio diversification effects through Country Neutralization strategies

### WakeUp App – Real-Time Eye-Closure Detection *(1st Place, Google ML Bootcamp)*
_Aug 2024 – Oct 2024_ 🔗 [GitHub Repo](https://github.com/Jaemani/wakeup_app)

- Designed a real-time drowsiness detection system for drivers, deployed on mobile via Flutter + Firebase
- Built an end-to-end ML pipeline: collected raw eye data, removed low-quality/duplicate images, applied background removal and augmentation (~9,200 images)
- Evaluated and compared 4 models (YOLOv5n, v5s, v8n, v8s) for precision, recall, mAP, and mobile inference latency
- Initially explored EfficientDet-lite**, OpenCV + CNN, and CenterNet, but ruled them out due to high resource demand and limited mobile compatibility
- Significantly improved detection confidence (from <40% to over 99%) through iterative data preprocessing and model tuning
- Integrated the optimized YOLOv5n model via `flutter_vision`, balancing accuracy and real-time performance on mobile
- Implemented geolocation-based risk alerts and real-time event logging using Firebase (Auth, Firestore, Functions)
- Proposed a Gemini-based advisory system for user feedback (under development); designed system for future scalability

### 수리수리 마수리 – Repair History System for Mobility Devices - Backend Developer *(Social Value Award, Kakao Impact Tech for Impact Program)*
_Mar 2025 – Jun 2025_ 🔗 [Github Repo](https://github.com/techforimpact-archive/TFI_CAMPUS_HANYANG_25Spring_Soori-soori) / [Notion](https://jaeman-hyu.notion.site/1c4ec4b6449b80bca4f2d6413eb7e8ef?pvs=4)  
*Developed as part of [Tech for Impact](https://techforimpact.io/) Campus, a university–impact organization collaboration program by Kakao Impacts*  

- QR-based repair history platform for electric mobility devices, in collaboration with a local welfare center.
- Developed key backend modules using Next.js, Firebase Auth, and MongoDB, enabling role-based access and real-time repair tracking
- Led infrastructure setup and system integration
- Planned integration with [별따러가자](https://starpickers.imweb.me/), an AIoT-based accident detection company, to connect repair history with real-world incident data

### Regression-Based MNIST Digit Prediction *(Exploratory Study)*
_Apr 2025 – May 2025_ 🔗 [Notion Page](https://jaeman.notion.site/MNIST-via-Regression-1e95d7580ec180abaee4e429b7bb93bf?pvs=73)

- Designed image regression models using TensorFlow/Keras, exploring both MLP and CNN-based architectures
- Framed MNIST digit recognition as a regression task predicting continuous numerical values, not discrete classes
- Analyzed how spatial feature extraction prior to flattening (CNN) significantly reduced error compared to raw-pixel regression (MLP)

### XRP Payment SDK Development for Web and Mobile Platforms *(in progress)*  
_Apr 2025 – Present_  
*Part of a university–industry collaboration between HYBLOCK (Hanyang University Blockchain Society) and [XRPL Korea](https://www.xrplkorea.org/).*  

- Leading SDK design for a plug-and-play XRP payment module, modeled after commercial solutions (e.g., Toss Payments), using the Xaman platform
- Implementing secure sign-request lifecycle based on XRPL payloads for point-of-sale use cases
- Delivering frontend integration examples and developer documentation for partner adoption (e.g., Uniport platform)
- Participating in weekly sync meetings between HYBLOCK and XRPL Korea to share progress and align technical direction

### SK AI Dream Camp *(on going)*
_Jul 2025 - Aug 2025_

- Participating in systematic AI/ML training program with real-world datasets from SK Group companies (SK Hynix, SK Telecom)
- Conducting comprehensive projects focused on building modeling and analysis capabilities through hands-on experience
- Telecom ICT Infrastructure Project: Performing EDA on base station equipment performance statistics and developing anomaly detection models for ICT infrastructure fault identification using time-series machine learning techniques
- Semiconductor Process Optimization: Developing machine learning prediction models using SK Hynix semiconductor process data, specifically creating package test result prediction models leveraging Photo (lithography) process indicators
- Gaining expertise in exploratory data analysis (EDA), time-series anomaly detection, and predictive modeling for industrial applications

---

## Activities & Engagement
- **HYBLOCK – Hanyang University Blockchain Society (2024 – Present)**  
A blockchain-focused academic club officially affiliated with Hanyang University.  
  - Participating as a Development Team member; studied blockchain fundamentals, smart contract design, and dApp implementation  
  - Built a testnet-based prediction market system using Solidity, Hardhat, Infura, Metamask, and ERC-20 token contracts  
  - Covered advanced topics such as contract security (e.g., reentrancy guards) and contract verification via Etherscan  
  - Collaborating with XRPL Korea on a real-world XRP payment SDK project
- **Google ML Bootcamp (2024)** – Selected as 3rd Cohort Project Member
Developed a full-stack ML mobile application as part of the official Google ML Bootcamp project track, from model training to app deployment 
- **Regular ML self-study**: Kaggle practice (regression, classification, CV)

---

## Research Goals

I’m particularly interested in developing machine learning systems that are not only accurate but also practically applicable—especially in high-impact areas such as accessibility, safety, and health.
I focus on designing models and interactions together, while optimizing for real-world constraints like deployment, usability, and latency.
My goal is to contribute to research that bridges technical depth with tangible social impact.

---

## Recognitions & Certifications

### 2023

- **Kakao Enterprise X goorm:** 군 장병 맞춤형 온라인 AI·SW 교육 프로그램 인공지능 중급과정 I
- **Kakao Enterprise X goorm:** 군 장병 맞춤형 온라인 AI·SW 교육 프로그램 인공지능 중급과정 II

### 2024  

- **WorldQuant BRAIN Platform:** Quantitative Finance INTERMEDIATE LEVEL

- **Google Korea ML Bootcamp (2024, Cohort 3):** 1st Place  
Selected as the top project among final demo teams, based on technical depth, completeness, and impact  
Hosted by Google Korea and NIPA, the bootcamp focused on building deployable AI systems for real-world applications.

### 2025  

- **XRPL KOREA Blockchain Hackathon DE-BUTHON**
- **Kakao Impact Tech for Impact**: Social Value Reward
