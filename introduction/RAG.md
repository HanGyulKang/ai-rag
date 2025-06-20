# RAG
## Retrieval-Augmented Generation : 검색, 증강, 생성

---

### RAG란?
RAG는 대규모 언어 모델(LLM)의 성능을 향상시키기 위한 기술이다.  
기존의 LLM이 가지고 있던 한계점(예: 최신 정보 부족, 도메인 특화 지식 부족, Hallucination 등)을  
해결하기 위해 외부 지식 베이스를 활용하는 방식이다.

### 작동 방식
Question → **[Document → Embedding → Vector Store → Retriever]** → Prompt → LLM

1. **Document (문서)**
   - 회사 내부 문서, 위키피디아, 기술 문서 등 다양한 형태의 지식 베이스를 준비한다.
   - 이 문서들은 나중에 질문에 대한 답변을 생성할 때 참조될 수 있는 베이스 데이터가 된다.

2. **Embedding (임베딩)**
   - 문서의 내용을 컴퓨터가 이해할 수 있는 숫자 형태(벡터)로 변환한다.
   - 이 과정을 통해 문서의 의미를 수치화하여 저장한다.

3. **Vector Store (벡터 저장소)**
   - 임베딩된 문서들을 효율적으로 저장하고 검색할 수 있는 데이터베이스다.
   - 유사한 의미를 가진 문서들을 빠르게 찾을 수 있게 해준다.

4. **Retriever (검색기)**
   - 사용자의 질문과 관련된 가장 적절한 문서들을 찾아낸다.
   - 질문의 의미와 가장 유사한 문서들을 선별한다.

5. **Prompt (프롬프트)**
   - 검색된 문서들과 사용자의 질문을 조합하여 LLM이 이해할 수 있는 형태로 만든다.
   - "다음 문서들을 참고하여 질문에 답변해주세요"와 같은 지시사항이 포함된다.

6. **LLM (대규모 언어 모델)**
   - 최종적으로 프롬프트를 받아 적절한 답변을 생성한다.
   - 검색된 문서들을 참고하여 더 정확하고 신뢰할 수 있는 답변을 제공한다.

### RAG의 장점
1. **정확성 향상**
   - 외부 베이스 데이터를 활용하여 더 정확한 답변을 제공한다.
   - Hallucination(환각) 현상을 크게 줄일 수 있다.

2. **최신 정보 활용**
   - LLM의 학습 데이터 이후의 새로운 정보도 활용할 수 있다.
   - 실시간으로 업데이트되는 정보를 반영할 수 있다.

3. **도메인 특화**
   - 특정 분야나 회사의 전문 지식을 LLM에 제공할 수 있다.
   - 일반적인 LLM보다 특정 도메인에서 더 나은 성능을 발휘한다.

4. **투명성과 제어**
   - 답변의 출처를 추적할 수 있다.
   - 개발자가 각 단계를 직접 튜닝하고 모니터링할 수 있다.

### 기타
Open AI의 Chat GPT같은 경우 Document 부터 Retriever 까지의 단계들이 어떻게 작동되는지 **비공개**되어있다.  
RAG 기술을 통해서 개발자가 직접 해당 단계들을 튜닝, 모니터링, 디버깅 할 수 있고 결과적으로 **Hallucination을 줄일 수 있다**.



