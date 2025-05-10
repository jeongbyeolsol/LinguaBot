# LinguaBot
NLTK와 Transformer 모델을 활용해 동사 문법 오류를 교정하는 CLI 챗봇


**LinguaBot**은 영어 문장을 입력받아 문법 오류를 탐지하고 피드백을 제공하는 **영어 문법 보정 챗봇**입니다.  
Rule-based 방식과 사전학습된 Transformer 모델 기반 두 가지 모드를 지원하며,  
실시간으로 문법 오류를 수정하거나 사용자에게 올바른 표현을 제안합니다.

---

## 주요 기능

- 사용자 입력 문장에서 **동사 품사(VB\*) 추출**
- 잘못된 과거형 동사 사용 시, **정확한 형태로 교정 제안**
- 접속사(Conjunction) 개수에 기반한 **문장 구조 피드백**
- 사전학습된 Transformer 모델 (`pszemraj/grammar-synthesis-small`)을 사용한 **AI 기반 문법 수정 기능**
- `LinguaBot` (규칙 기반), `Zrammar` (LLM 기반) 모드 전환 가능

---

## 사용 기술

- Python 3
- NLTK (품사 태깅)
- HuggingFace Transformers (pszemraj/flan-t5-small) (transformers는 HuggingFace에서 제공하는 라이브러리)
- PyTorch (모델 실행) (transformers 라이브러리가 내부적으로 PyTorch를 사용)
- CLI 기반 챗봇 인터페이스 (Command Line Interface)

---

## 실행 예시

```bash
You: I goed to school and buyed milk.
LinguaBot: Did you mean 'went' instead of 'goed'? Did you mean 'bought' instead of 'buyed'?

You: I goed to school and.
LinguaBot: More verbs are needed!

You: I goed to school.
Zrammar: I went to school.
