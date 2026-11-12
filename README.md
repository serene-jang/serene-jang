# 안녕하세요, serene-jang 입니다 👋

학교에서 쓰는 **크롬북 · 노트북 · 태블릿을 한곳에서 관리하는 교실 기기 관리 서비스**를 만들고 있어요.

---

## 🏫 Clario — 학생 기기를 한곳에서 관리하는 교실 기기 관리 서비스

> 교사가 수업 코드 하나로 학생 기기를 연결하고, 화면 확인 · 사이트 제한 · 자료 전달 · 수행평가 진행까지 관리해요. 설치 없이 브라우저에서 시작해요.

| | 링크 |
|---|---|
| 👩‍🏫 교사용 | [teacher.html](https://app-clario-v3-42e4.azurewebsites.net/teacher.html) (구글 로그인) |
| 🧑‍🎓 학생용 | [student.html](https://app-clario-v3-42e4.azurewebsites.net/student.html) (수업 코드 + 이름) |

> ⏳ Azure 무료 플랜에서 운영 중이라, 한동안 접속이 없으면 첫 접속에 몇십 초 걸릴 수 있어요.

### 어떤 서비스인가요?

선생님이 구글 계정으로 로그인해 **수업 코드**를 만들고, 학생은 계정 없이 코드와 이름만 입력해서 기기를 연결해요. 연결된 기기는 선생님 화면 한곳에서 상태를 보고 관리해요.

### 📱 지원 기기

| 기기 | 관리 방식 | 상태 |
|---|---|---|
| 💻 크롬북 · 윈도우/맥 노트북 | 브라우저(Chrome · Edge · 웨일)에서 화면 공유 + **학생 도우미 확장 프로그램** | 웹 기능은 시험 완료, **실제 크롬북은 검증 전** |
| 📲 갤럭시탭 (안드로이드) | **탭 도우미 앱**(소스 제공): 화면 보기 · 사이트 제한 · 다른 앱 차단 | 앱 소스와 서버 연동만 확인, **APK 빌드와 실기기는 검증 전** |
| 🍎 아이패드 · 아이폰 | 브라우저가 화면 공유를 지원하지 않아 **화면 확인은 불가** (수행평가 · 제출은 가능) | 한계로 안내 |

### 🛡 기기 관리 기능

- 학생 기기 **연결 상태와 화면 공유 상태**를 한눈에 확인, 연결이 끊기면 알림
- **인터넷 허용 사이트 설정**: 선생님이 허용한 사이트만 열리도록 학생 기기에 적용 (도우미 설치 필요)
- **도우미 원클릭 배포**: 설치하지 않은 학생 화면에 기기 종류에 맞는 설치 안내를 자동으로 띄움
- 수업 화면 이탈 · 화면 공유 중지 · AI 사이트와 검색 시도 **알림** (브라우저가 알 수 있는 범위만)
- 갤럭시탭: 수업 중 **다른 앱 실행 시 홈으로 돌려보내고** 알림, 앱 삭제 시 35초 안에 연결 끊김 알림

**선생님**
- 학생이 직접 허용한 **화면 공유**로 학생 화면을 한눈에 확인하고, 클릭해서 크게 보기
- **공지 · 과제 링크 · 파일**을 학생에게 보내고, 학생 제출물 받기 (여러 파일 한 번에)
- **시험 모드**: 학생이 수업 화면을 벗어나면 알림
- **수행평가**: 문서 · 파이썬 · 스크래치 중 원하는 도구를 골라 출제, 선생님이 만든 `.docx` 양식을 그대로 불러오기
- 학생의 **작성 과정 다시 보기**, 잠금 · 해제, 제출 상태 확인
- 녹화와 제출물을 **선생님 본인의 구글 드라이브 또는 PC 폴더**에 저장 (서버에는 남기지 않아요)

**학생**
- 계정 없이 수업 코드로 입장
- 받은 파일(그림 · PDF · 동영상 · 노트북 · zip · 문서 · 스크래치)을 **앱 안에서 바로 열기**
- 문서 작성기 · **브라우저 안에서 실행되는 파이썬**(Pyodide) · 스크래치로 수행평가 작성 후 제출
- 크롬북 · 노트북용 **학생 도우미 확장 프로그램**, 갤럭시탭용 **안드로이드 도우미 앱** 소스 제공

### 만들면서 지킨 원칙

- 화면 공유는 **학생이 직접 허용**하는 방식만 사용하고, 공유 중임을 학생에게 계속 보여줘요.
- 브라우저가 알 수 없는 것(다른 프로그램에서 하는 일)은 **아는 것처럼 표시하지 않아요.**
- 녹화와 제출물은 선생님이 고른 저장소로만 보내요. 서버는 잠깐 전달만 해요.
- 교사 로그인은 Firebase 구글 로그인, 비밀 값은 서버 설정에만 두고 코드에 넣지 않아요.

### 기술 스택

![Node.js](https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?logo=express&logoColor=white)
![Socket.IO](https://img.shields.io/badge/Socket.IO-010101?logo=socketdotio&logoColor=white)
![Firebase Auth](https://img.shields.io/badge/Firebase_Auth-FFCA28?logo=firebase&logoColor=black)
![Azure App Service](https://img.shields.io/badge/Azure_App_Service-0078D4?logo=microsoftazure&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Pyodide](https://img.shields.io/badge/Pyodide-3776AB?logo=python&logoColor=white)
![Scratch](https://img.shields.io/badge/Scratch-4D97FF?logo=scratch&logoColor=white)
![Chrome Extension](https://img.shields.io/badge/Chrome_Extension-4285F4?logo=googlechrome&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?logo=android&logoColor=white)

- **서버**: Node.js · Express · Socket.IO (실시간 화면 · 알림)
- **로그인**: Firebase Authentication (구글)
- **배포**: Azure App Service (HTTPS · WebSocket)
- **수행평가 도구**: 브라우저 문서 편집기, Pyodide(파이썬), Scratch GUI
- **도우미**: Chrome 확장 프로그램(Manifest V3), 안드로이드 앱(Java)

### 현재 상태

- ✅ 수업 만들기 · 학생 입장, 공지 · 링크 · 파일 전달, 파일 앱 안에서 열기, 수행평가 작성 · 제출, 도우미 설치 안내 배포를 직접 시험해 봤어요.
- ⚠️ **실제 학교 크롬북 · 갤럭시탭과 학교 관리 정책(MDM · 확장 프로그램 설치 제한)에서의 동작은 아직 검증하지 못했어요.** 구글 드라이브 저장, 확장 프로그램 사이트 차단, 갤럭시탭 앱 빌드와 실기기 동작도 검증이 남아 있어요.
- ℹ️ 학생이 도우미를 끄거나 지우면 막을 수 없어요. 대신 선생님께 알림이 가요. 완전한 통제는 학교 MDM과 함께 써야 해요.
- 🧪 앞으로 실제 수업에서 시험하며 다듬어 갈 계획이에요.

---

## 📂 다른 프로젝트

| 프로젝트 | 설명 |
|---|---|
| [BookMind](https://github.com/serene-jang/BookMind) | 책을 읽고 내용 파악을 도와주는 앱 |
| [CLARIO](https://github.com/serene-jang/CLARIO) | 교실 기기 관리 서비스의 초기 작업 저장소 |
| [sayso](https://github.com/serene-jang/sayso) | JavaScript 프로젝트 |
| [smart-schedule-notice](https://github.com/serene-jang/smart-schedule-notice) | JavaScript 프로젝트 |
| [connect-four](https://github.com/serene-jang/connect-four) | 사목 게임 |

<sub>이 README는 GitHub 프로필(`serene-jang/serene-jang`)에 표시돼요.</sub>
