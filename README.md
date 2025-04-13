# 뉴스 크롤링 및 AI 요약 봇

이 프로젝트는 해외 경제 뉴스를 자동으로 크롤링하고, Google의 Gemini AI를 사용하여 한글로 요약한 후 텔레그램 봇을 통해 전송하는 시스템입니다.

## 주요 기능

- RSS 피드에서 미국 및 중국 경제 뉴스 자동 수집
- Google Gemini AI를 사용한 영어 뉴스 한글 요약
- 텔레그램 봇을 통한 뉴스 요약 전송
- 정기적인 뉴스 모니터링 및 자동 전송 기능
- 간편한 커맨드 라인 인터페이스

## 설치 방법

### 필수 라이브러리 설치

```bash
pip install requests beautifulsoup4 schedule newspaper3k pandas python-dotenv feedparser translators nltk google-generativeai
```

### NLTK 데이터 설치

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
nltk.download('punkt_tab')
```

### 환경 변수 설정

`.env` 파일을 생성하고 다음 내용을 추가합니다:

```
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_CHAT_ID=your_telegram_chat_id
GOOGLE_API_KEY=your_gemini_api_key
```

## 사용 방법

1. 프로그램 실행:
   ```bash
   python news_crawler_gemini.py
   ```

2. 메뉴에서 원하는 옵션 선택:
   - 지금 바로 뉴스 수집 및 전송
   - 24시간 모니터링 시작
   - 48시간 모니터링 시작
   - 매일 아침 8시 자동 전송 활성화
   - 번역 설정 변경 (제목용)
   - Gemini API 설정 변경

## Gemini API 설정

1. [Google AI Studio](https://makersuite.google.com/app/apikey)에서 API 키 발급
2. 프로그램의 `GOOGLE_API_KEY` 변수 업데이트 또는 메뉴에서 API 키 설정 옵션 사용

## 텔레그램 봇 설정

1. Telegram의 [BotFather](https://t.me/botfather)를 통해 새 봇 생성
2. 발급받은 토큰을 `.env` 파일 또는 코드의 `TELEGRAM_BOT_TOKEN` 변수에 설정
3. 봇과 대화를 시작한 후 `/start` 명령어 입력
4. [userinfobot](https://t.me/userinfobot)을 통해 사용자 ID 확인
5. 확인한 ID를 `.env` 파일 또는 코드의 `TELEGRAM_CHAT_ID` 변수에 설정

## 주의사항

- 뉴스 사이트에 따라 접근이 제한될 수 있습니다.
- Gemini API 사용량에 따라 비용이 발생할 수 있습니다.
- 네트워크 상태에 따라 크롤링 성능이 달라질 수 있습니다.

## 라이선스

MIT License