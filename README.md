# **노트북 정보 제공 챗봇**

## 1. 문제 제기

### 1) 최신 노트북에 대한 정보 제공  
- 이전에 기록된 정보만 제공되어 최신 노트북에 대한 정보가 제공되지 않았습니다.

### 2) 할루시네이션 발생  
- GPT에서 제공하는 웹 검색 기능을 사용하더라도, 원하는 정보와 동일한 명칭에 대한 정보가 포함되어 할루시네이션이 발생할 수 있습니다.

---

## 2. 최신 노트북 사용 설명 챗봇 소개  
- **RAG (Retrieval-Augmented Generation)** 기반 챗봇 서비스 구현

![플로우차트](images/플로우차트.png)

---

## 3. Task 유형 정의 / 주요 기능

### 1) 대화형 인터페이스 설계 및 구현  
- 사용자 요청을 자연스럽게 처리하는 직관적인 챗봇 UI 개발  
- 사용자 경험(UX) 최적화를 위한 인터페이스 개선  

### 2) DB 생성  
- 최신 노트북 정보가 담긴 데이터베이스 구축

### 3) 대규모 언어 모델(LLM) 활용  
- LLM을 통해 자연스러운 대화와 문맥 기반 응답 생성

### 4) RAG 기법 적용  
- DB 검색 결과를 바탕으로 LLM이 최적의 답변을 생성하도록 설계

---

## 4. 사용 툴
## 아키텍처
![아키텍처](images/Frame%201.png)
### 프론트엔드: Node.js  
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)  
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)

### 백엔드: FastAPI  
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)  
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)

### 데이터베이스: Pinecone  
![Pinecone](https://img.shields.io/badge/Pinecone-black?style=for-the-badge&logo=pinecone&logoColor=339933)

### 모델: LangChain, ChatGPT, Embedding (Upstage), Retrieval (MMR), 테스트 (RAGAS)  
![LangChain](https://img.shields.io/badge/LangChain-%23F5A623.svg?style=for-the-badge&logo=svg&logoColor=white)  
![ChatGPT](https://img.shields.io/badge/chatGPT-74aa9c?style=for-the-badge&logo=openai&logoColor=white)  
![Upstage](https://img.shields.io/badge/Upstage-%23805CFB.svg?style=for-the-badge&logo=data:image/png;base64,...)  
![MMR](https://img.shields.io/badge/MMR-%23007BFF.svg?style=for-the-badge&logo=MMR&logoColor=white)  
![RAGAS](https://img.shields.io/badge/RAGAS-%23F9C23C.svg?style=for-the-badge&logo=RAGAS&logoColor=white)

### 배포: AWS, Fly.io  
![Amazon AWS](https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)  
![Fly.io](https://img.shields.io/badge/Fly.io-24175B?style=for-the-badge&logo=flydotio&logoColor=white)

### GitHub 도구  
![Mattermost](https://img.shields.io/badge/Mattermost-0058CC?style=for-the-badge&logo=Mattermost&logoColor=white)  
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)

---

## 기능

- 사용자가 노트북에 대한 사용 방법을 묻는 경우, 질문 내용에서 노트북 제조사를 식별하는 기능을 추가했습니다.  
- 식별된 노트북 제조사를 기반으로, 사전 학습된 사용 설명서를 참조하여 정확한 답변을 제공합니다.

### 주요 기능

#### 1. 할루시네이션 답변 방지

- **notbot의 답변**  
    ![image.png](images/notbot_1.png)

- **OpenAI ChatGPT의 답변**:  
  - "Yoga"는 레노바의 노트북 모델명이지만, 그래픽 디지털 디자인 소프트웨어와 혼동될 수 있습니다.  
  - "Pen Pro"는 스타일러스(디지털 펜)로 혼동될 수 있습니다.  
  ![image.png](images/gpt_1.png)

#### 2. 부정확한 답변 방지

- **notbot의 답변**  
    ![image.png](images/notbot_2.png)

- **OpenAI ChatGPT의 답변** → 웹 검색을 통한 답변  
  삼성 S펜에 대한 답변도 포함하여 제공되고 있습니다.  
    ![image.png](images/gpt_2.png)

---

## 사용법


### [사용 화면]
  ![사용방법](images/NoteBot%20사용방법.jpg)


[시연 연상]

https://github.com/user-attachments/assets/9894beb4-9683-4cbd-8fc7-58743e17ae25

---

## 배포된 링크

- **프론트**: [https://main.d23vfmqy5vhe9g.amplifyapp.com/](https://main.d23vfmqy5vhe9g.amplifyapp.com/)  
- **백**: [https://ssafy-2024-back.fly.dev/](https://ssafy-2024-back.fly.dev/)

---
# 로컬 실행 방법


## 프론트엔드 서버 실행 방법

```bash
npm init -y
pip install -r requirements.txt 
npm run build
npm start
```

## 백엔드 서버 실행 방법

```bash
pip install -r requirements.txt 
python app.py
```