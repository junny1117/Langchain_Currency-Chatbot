# Currnecy-Chatbot_Ollama_gemma2-9b
## 개요
Langchain, Ollama, Streamlit을 활용한 환율 정보 제공 챗봇

## 구현 사항
### 환율 정보 크롤링
- **사용자**가 **원하는 국가**의 **환율 정보**를 **크롤링**을 통해 수집
- 수집되는 데이터:
  - 현재 환율(매매기준율)
  - 전일 대비 차이 및 변동률
  - 현찰 살 때와 팔 때의 환율
  - 송금 보낼 때와 받을 때의 환율
### 사용자 질문 답변
- **문장 유사도 파악**을 통해 사용자 **질문**에 대한 **답변** 성능 **향상**
- **언어 모델**을 **사용**하여 사용자의 **질문 의도 파악** 및 **자연스러운 답변** 가능


## 작동 과정

1. **사용자 입력**:
   - 사용자는 국가 이름과 환율에 관해 궁금한 점을 입력
   - 예: 현찰 살때 환율은 얼마니? 등의 질문

2. **웹 크롤링**:
   - `Selenium`을 사용하여 다음 검색 - 환율+국가명 [예시](https://search.daum.net/search?nil_suggest=btn&w=tot&DA=SBC&q=환율미국)에서 해당 국가 환율 정보 크롤링

3. **문서 분할**:
   - 크롤링한 데이터를 문서 형식으로 변환하여 `RecursiveCharacterTextSplitter`를 사용해 효과적으로 검색할 수 있도록 분할

4. **유사도 검색**:
   - `FAISS`를 사용해 유사도 검색 인덱스를 구축하여, 사용자 질문에 맞는 내용 검색.

5. **답변**:
   - `ChatOllama` 및 gemma2:9b 모델을 이용해 검색된 내용을 바탕으로 자연어로 답변을 생성.

## 사용도구/기술
- **Python**: 개발언어
- **Selenium**: 웹 크롤링
- **Streamlit**: 사용자 인터페이스
- **Langchain**: LLM 활용 애플리케이션 개발 프레임워크
- **gemma2:9b**: 언어모델
- **Visual Studio Code**: 코드 작성
- **Windows**: 운영체제

## 실행 결과 이미지
![스크린샷 2024-10-24 172805](https://github.com/user-attachments/assets/adb00a4d-e894-4423-8f87-be24a9d5834f)
![스크린샷 2024-10-24 172849](https://github.com/user-attachments/assets/65891377-19e0-4baa-a9e2-083c08a18f8b)



