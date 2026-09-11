# GameMatching Firebase 설정

## Authentication

Firebase Console에서 다음 provider를 활성화해야 합니다.

1. Authentication → Sign-in method
2. Anonymous provider 활성화
3. 저장

## Realtime Database Rules 배포

Firebase CLI가 설치되어 있다면 저장소 루트에서 실행합니다.

firebase login
firebase use tingtongame
firebase deploy --only database

`.firebaserc`는 기존 tingtongame Firebase 프로젝트를 계속 사용하도록 설정되어 있습니다.

## 데이터 구조

- 방 접근 권한: gamematching_v1/rooms/{inviteCode}/access/{uid}
- 회원 명단: gamematching_v1/rooms/{inviteCode}/roster/members/{memberId}
- 날짜별 경기 세션: gamematching_v1/rooms/{inviteCode}/sessions/{YYYY-MM-DD}
- 동시성 ID 카운터: gamematching_v1/rooms/{inviteCode}/counters
