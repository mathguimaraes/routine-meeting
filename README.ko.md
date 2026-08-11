<div align="center">

<img src="icon.png" width="128" height="128" alt="Routine Meeting icon">

# Routine Meeting

**회의는 일어난다. 메모는 당신의 일이 아니어야 한다.**

[macOS용 다운로드](https://github.com/mathguimaraes/routine-meeting/releases/latest) · Apple Silicon · macOS 13+

[![en](https://img.shields.io/badge/lang-en-red.svg)](README.md)
[![es](https://img.shields.io/badge/lang-es-yellow.svg)](README.es.md)
[![pt--br](https://img.shields.io/badge/lang-pt--br-green.svg)](README.pt-BR.md)
[![ja](https://img.shields.io/badge/lang-ja-blue.svg)](README.ja.md)
[![de](https://img.shields.io/badge/lang-de-orange.svg)](README.de.md)
[![fr](https://img.shields.io/badge/lang-fr-lightgrey.svg)](README.fr.md)
[![ko](https://img.shields.io/badge/lang-ko-blueviolet.svg)](README.ko.md)
[![zh--cn](https://img.shields.io/badge/lang-zh--cn-critical.svg)](README.zh-CN.md)

</div>

---

## 문제

통화에 참여했는데, 흥미로워지는 순간 선택을 해야 한다. 집중해서 들을 것인가, 받아 적을 것인가. 메모 앱을 찾느라 회의 초반을 놓친다. 녹음 버튼 누르는 걸 잊는다. 금요일이 되면 여섯 번의 회의에서 나온 결정과 할 일들이 오직 내 기억 속에만 남아 있다.

대부분의 녹음 도구는 이 문제를 더 악화시킨다 — 시작 버튼을 직접 눌러야 하고, 원본 음성을 어딘가의 서버로 보내며, 절반은 내 목소리와 다른 사람 목소리조차 구분하지 못한다.

## Routine Meeting이 하는 일

Routine Meeting은 메뉴 막대에 조용히 자리 잡고, 요청하지 않아도 모든 것을 처리한다.

- **회의 중임을 감지하고 스스로 녹음을 시작한다 — *어떤* 앱에서든.** Zoom/Meet/Teams처럼 지원 앱 목록이 정해진 통합 방식이 아니라, 실제 대화의 마이크 + 시스템 오디오 패턴을 감지한다. 그래서 Google Meet, Zoom, Microsoft Teams, Webex, Slack 허들, Discord, FaceTime, WhatsApp 통화, 또는 Mac을 거치는 전화 통화까지 양방향 오디오만 있으면 앱별 설정 없이 동일하게 작동한다. 기억해야 할 버튼도 없고, "이거 녹음되고 있었나?" 하는 불안한 순간도 없다.
- **모든 것을 Mac에서 전사한다.** [WhisperKit](https://github.com/argmaxinc/WhisperKit)이 Apple Silicon의 Neural Engine에서 실행되며, 오디오는 절대 기기 밖으로 나가지 않는다.
- **내가 한 말과 다른 사람이 한 말을 구분한다.** 마이크와 시스템 오디오를 별도로 캡처하고 분리하기 때문에, 요약과 인사이트가 올바른 사람에게 귀속된다.
- **전사 내용을 쓸모 있게 바꾼다** — 제목, 요점 요약, 액션 아이템, 그리고 선택적으로 1:1, 고객 통화, 디자인 리뷰 등 그 특정 대화에서 본인이 어떻게 했는지에 대한 솔직한 평가까지.
- **모든 것을 일일 리포트로 정리한다** — 오늘 모든 회의에서 무슨 일이 있었는지, 아직 누군가에게 갚아야 할 것은 무엇인지.

AI 계층에는 본인의 [Gemini API 키](https://aistudio.google.com/apikey)를 사용한다(무료 등급으로도 개인 사용에는 충분하다) — 아니면 키 없이 기기에서 로컬 모델을 완전히 실행할 수도 있다.

## 이렇게 만들어진 이유

- **설계부터 앱 독립적.** 대부분의 회의 녹음 도구는 각 앱의 SDK와 개별적으로 통합하기 때문에 몇몇 주요 앱에서만 작동한다. Routine Meeting은 대신 시스템 오디오 수준에서 캡처하므로, Mac에서 소리를 내는 모든 앱이 대상이 된다. 팀, 고객, 가족이 무엇을 표준으로 쓰든 상관없다.
- **로컬 우선.** API 키를 추가하든 안 하든 녹음과 전사는 Mac에서 이루어진다. 기기를 벗어날 수 있는 것은 텍스트 전사본뿐이며, 그마저도 클라우드 요약을 켰을 때만 해당된다.
- **계정도, 구독도 없음.** SaaS 래퍼가 아니라 네이티브 앱이다. DMG도 내 것, 데이터도 내 것이다.
- **실제 회의가 돌아가는 방식에 맞춰 제작.** 잘못된 감지(음악, 우연한 음성 메시지)가 유령 녹음으로 이어지지 않으며, 통화 중 마이크가 끊겨도 전사본의 절반이 조용히 사라지지 않는다.

## Routine Meeting이 다른 점

대부분의 회의 어시스턴트는 눈에 보이는 봇(Fireflies, Otter)을 쓰든 "봇 없는" 방식(Fellow, Fathom)을 쓰든, 결국 녹음과 전사본을 처리를 위해 자사 서버로 보낸다. Routine Meeting은 다르게 접근한다: 모든 것이 Mac에서 일어난다.

- **기기 밖으로 아무것도 나가지 않는다.** 녹음과 전사가 전적으로 기기 내에서 실행된다. "봇 없음"을 내세우는 도구와 비교해도 마찬가지다. 봇 없음이란 단지 통화에 눈에 보이는 참가자가 들어오지 않는다는 뜻일 뿐, 데이터가 로컬에 머문다는 뜻은 아니기 때문이다. 클라우드 AI 요약을 명시적으로 활성화하지 않는 한, Routine Meeting은 아무것도 업로드하지 않는다.
- **모든 앱에서 자동으로 작동한다.** Routine Meeting은 참가자로 통화에 들어가거나 특정 앱의 API에 연결하는 대신, 실제 대화의 마이크 + 시스템 오디오 패턴을 감지해서 회의를 인식한다. 즉 Google Meet, Zoom, Teams, Webex, Slack 허들, Discord, FaceTime, 또는 Mac을 거치는 전화 통화가 모두 앱별 설정 없이 동일하게 작동한다.
- **직접 키를 쓰거나, 클라우드를 아예 건너뛰거나.** AI 요약은 본인의 Gemini API 키를 사용하거나(무료 등급으로 개인 사용 충분), 키도 클라우드 호출도 없이 완전히 로컬 모델을 실행할 수도 있다.
- **계정도, 구독도 없음.** Routine Meeting은 무료이며 어떤 가입도 요구하지 않는다.

### 아직 없는 것

솔직히 말하면, Routine Meeting은 투자를 받은 플랫폼이 아니라 한 사람이 만든 macOS 앱이다. Fireflies, Fellow 등 비슷한 도구들이 제공하지만 Routine Meeting에는 없는 것들:

- 회의 간 검색이나 장기적으로 검색 가능한 지식 베이스 (현재는 일일 요약으로 제한)
- CRM, Slack, 채용 도구, 다이얼러와의 연동
- 엔터프라이즈 컴플라이언스 인증 (SOC 2, HIPAA, GDPR)
- Windows 또는 모바일 지원

지금 당장 이런 기능이 필요하다면 Fireflies나 Fellow 같은 플랫폼이 더 적합할 수 있다. 특히 이런 인증이 중요한 규제 산업이라면 더욱 그렇다. 반대로 Mac을 벗어나지 않고, 봇도 클라우드 계정도 필요 없는 것을 원한다면, Routine Meeting이 채우는 것이 바로 그 빈틈이다.

## 설치

1. [Releases](https://github.com/mathguimaraes/routine-meeting/releases/latest)에서 최신 `RoutineMeeting.dmg`를 다운로드한다.
2. DMG를 열고 **Routine Meeting**을 **응용 프로그램** 폴더로 드래그한다.
3. 앱을 실행한다. 짧은 설정 가이드가 각 권한이 왜 필요한지 설명한 뒤 시스템 프롬프트(마이크, 화면 기록, 로그인 시 시작, 손쉬운 사용, 알림)를 안내하며, Gemini 키를 추가하거나 온디바이스 모드로 건너뛸 수 있다. 화면 기록 단계는 다른 참가자의 오디오를 캡처하기 위한 것으로 보라색 녹화 표시등을 켜는데, 이는 예상된 동작이며 필요한 과정이다.
4. 이 가이드는 메뉴 막대 아이콘 → **설정 가이드…**에서 언제든 다시 실행할 수 있다.

전사가 완료된 녹음은 7일이 지나면 자동으로 삭제된다(전사본과 요약은 영구히 보관) — 설정 → 저장공간에서 조정 가능하며, "지금 공간 확보하기" 수동 버튼도 있다.

Routine Meeting은 자동으로 업데이트를 확인하고([Sparkle](https://sparkle-project.org) 사용), 새 버전이 준비되면 앱 내에서 알려준다.

## 개인정보 보호

오디오와 전사본은 Mac에 남는다. 클라우드 AI 제공업체를 활성화하지 않는 한 어디로도 전송되지 않으며, 활성화하더라도 전사 텍스트만 나갈 뿐 원본 오디오는 절대 나가지 않는다.

앱은 또한 하루에 한 번 익명 핑을 보낸다(회의 내용, 이름, 이메일이 없는 무작위 ID). 이를 통해 대략적인 사용량을 파악할 수 있다. 기본적으로 켜져 있으며, 설정 → 개인정보 보호에서 언제든 끌 수 있고, 그 외 다른 동작에는 영향이 없다.

## 피드백 / 문제 신고

앱 내 메뉴 막대 아이콘 → **피드백 보내기…**, 또는 여기서 [이슈](https://github.com/mathguimaraes/routine-meeting/issues)를 열어주세요.
