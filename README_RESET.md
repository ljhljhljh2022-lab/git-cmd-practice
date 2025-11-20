# RESET 명령어

`git reset` 명령어는 커밋 히스토리를 되돌립니다.

## 사용법
```bash
git reset --soft HEAD~1     # 커밋만 취소 (스테이징 유지)
git reset --mixed HEAD~1    # 커밋과 스테이징 취소 (기본값)
git reset --hard HEAD~1     # 모든 변경사항 취소 (위험!)
git reset <커밋해시>        # 특정 커밋으로 이동
```

## 옵션별 동작

### --soft
- HEAD만 이동
- 스테이징 영역 유지
- 작업 디렉토리 유지
- 용도: 커밋 메시지 수정, 커밋 합치기

### --mixed (기본값)
- HEAD 이동
- 스테이징 영역 초기화
- 작업 디렉토리 유지
- 용도: 커밋 취소 후 재작업

### --hard
- HEAD 이동
- 스테이징 영역 초기화
- 작업 디렉토리 초기화
- 용도: 완전히 되돌리기 (복구 불가!)

## 주의사항

⚠️ **공유된 브랜치에서는 사용 금지!**
- 히스토리가 재작성됨
- 협업자에게 문제 발생
- 대신 `git revert` 사용 권장

⚠️ **--hard 옵션 주의!**
- 작업 내용이 완전히 삭제됨
- 복구가 어려움

## 예시
```bash
# 마지막 커밋 취소 (파일은 유지)
git reset --soft HEAD~1

# 마지막 커밋과 스테이징 취소
git reset HEAD~1

# 모든 변경사항 완전히 취소 (위험!)
git reset --hard HEAD~1

# 특정 커밋으로 이동
git reset --hard abc1234

# 특정 파일만 unstage
git reset HEAD <파일명>
```

## 복구 방법
```bash
# reflog로 과거 상태 확인
git reflog

# 특정 상태로 복구
git reset --hard HEAD@{2}
```

## reset vs revert

| 구분 | reset | revert |
|------|-------|--------|
| 히스토리 | 삭제 | 보존 |
| 새 커밋 | 생성 안함 | 생성함 |
| 공유 브랜치 | 위험 | 안전 |
| 사용 시기 | 로컬 작업 | 공유 후 |
