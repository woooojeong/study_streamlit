### ✅ 주요 수행 작업

1. **Streamlit 기반 UI 구성 (`chat.py`)**
   - `streamlit`을 사용하여 웹 기반 챗봇 인터페이스 구성  
   - `st.chat_message()` 및 `st.chat_input()`을 활용해 사용자 입력과 챗봇 응답을 채팅 UI로 시각화  
   - 사용자 입력과 챗봇 응답을 `st.session_state`에 저장해 대화 기록 유지  
   - 기본 페이지 제목 및 설명 추가  

2. **예시 문답 데이터 구성 (`config.py`)**
   - 실제 소득세 관련 Q&A 예시 3개를 리스트 형태로 구성  
   - LangChain의 Few-shot learning에 활용하기 위해 `answer_examples` 형태로 저장  

3. **LLM 처리 및 RAG 체인 구성 (`llm.py`)**
   - LangChain 및 OpenAI의 `ChatOpenAI`, `OpenAIEmbeddings` 등을 활용하여 LLM 및 벡터 기반 검색 기능 구성  
   - Pinecone 벡터스토어를 통해 외부 문서 검색 기반 QA 시스템 구현 (`get_retriever`)  
   - 과거 대화 히스토리를 고려한 질문 재구성 (`get_history_retriever`)  
   - 질문 전처리를 위한 "사전 체인" 구성: 특정 표현을 자동 치환  
   - 예시 기반의 few-shot prompting 및 문서 기반 답변을 결합한 RAG 체인 구성 (`get_rag_chain`)  
   - 최종적으로 사용자 질문을 받아 전처리 후 RAG 체인을 통해 답변 생성 (`get_ai_response`)
