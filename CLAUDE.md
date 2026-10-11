# 아요거북목요 (AYO Turtle Neck Scanner)

일반 사용자용 거북목 측정·관리 앱. 애플스토어 + 플레이스토어 동시 출시 목표.

## 확정된 결정사항 (2026-10-11)
- 앱 이름: **아요거북목요** / 영문 **AYO Turtle Neck Scanner**
- 패키지명: **com.physiomaster.ayoneck** (스토어 등록 후 변경 불가)
- 스택: 웹(HTML/JS 단일 파일 지향) + **Capacitor 8** (android/ios 폴더 생성됨)
- 서버 **없음**: 모든 기록은 기기에만 저장 (localStorage / Capacitor Preferences). Supabase 안 씀.
- 수익: **AdMob 광고** (하단 배너 + 측정 완료 후 전면광고, 빈도는 측정 3회당 1번 수준으로 시작)
- 측정: 기존 posture-check(아요바디요)의 CVA 거북목 측정 코드(MediaPipe Pose) 이식.
  원본 위치: `C:\Users\USER\Documents\GitHub\posture-check\index.html` (v147에서 거북목 추가, grep "CVA")

## 사용자 / 소통 규칙
- 사용자: 아요. 한국어, 결론부터, 비개발자 — 콘솔 작업은 메뉴 경로로 안내.
- 시크릿·keystore 절대 커밋 금지. 패키지명 변경 금지.

## 빌드
- 안드로이드: 로컬 빌드 가능 (`npx cap sync android` 후 Android Studio 또는 gradle)
- iOS: **Windows라 로컬 빌드 불가** → GitHub Actions macOS 러너에서 빌드 (워크플로 추후 작성)
- 웹 미리보기: `npm run serve` (포트 8766)

## 남은 일 (플랜 순서)
1. [ ] 아요: Apple Developer 가입 (연 $99) / AdMob 가입
2. [ ] GitHub 저장소 생성 + 푸시
3. [ ] CVA 측정 기능 이식 (카메라 → MediaPipe → 각도 → 점수/등급)
4. [ ] 로컬 기록 저장 + 변화 그래프
5. [ ] 스트레칭 리마인더 (로컬 알림, @capacitor/local-notifications)
6. [ ] AdMob 연동 (@capacitor-community/admob) + iOS ATT 팝업
7. [ ] 개인정보처리방침(광고 SDK 수집 고지) + app-ads.txt — GitHub Pages에 게시
8. [ ] Play 내부 테스트 → TestFlight → 심사 제출
   - 심사 주의: "진단/치료" 표현 금지, 애플 4.2(최소 기능성) 대비 네이티브 느낌 유지
