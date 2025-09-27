<img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="32" style="vertical-align:middle; margin-right:8px;" />

GitHub Actions를 사용하여 Pull Request의 충돌을 감지하고 Discord로 알림을 보내는 시스템입니다.

<br>

### 기능

- **PR 이벤트 감지**: PR이 열리거나 업데이트될 때 충돌 확인
- **Push 이벤트 감지**: main/develop 브랜치에 push될 때 모든 PR 충돌 확인
- **Discord 알림**: 충돌 발생 시 Discord Webhook로 알림 전송

<br>

### 설정

GitHub 저장소의 Settings > Secrets and variables > Actions에서 다음 시크릿을 설정해야 합니다.

1. **`PAT_KEY`**
   - 권한: `repo` (전체 저장소 접근)

2. **`DISCORD_WEBHOOK_URL`**
   - Discord 서버에서 Webhook 생성 후 URL 복사

<br>

### 알림 메시지 형식

**단일 PR 충돌 (PR 이벤트)**
```
⚠️ PR 충돌 발생!
PR에서 충돌이 감지되었습니다.

PR 정보: [#1](링크) Modify file
브랜치 정보: Kim-Yukyung | test → main
```

**Push로 인한 PR 충돌 (Push 이벤트)**
```
⚠️ Push로 인한 PR 충돌!
main 브랜치에 푸시된 변경사항으로 인해 PR에서 충돌이 발생했습니다.

PR 정보: [#1](링크) Modify file
브랜치 정보: Kim-Yukyung | test → main
Push 커밋 메시지: 커밋 메시지 내용
```
