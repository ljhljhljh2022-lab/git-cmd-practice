# REVERT 명령어

`git revert` 명령어는 특정 커밋을 취소하는 새로운 커밋을 생성합니다.

## 사용법
```bash
git revert <커밋해시>        # 특정 커밋 취소
git revert HEAD             # 마지막 커밋 취소
git revert HEAD~3           # 3개 전 커밋 취소
git revert --no-commit HEAD # 커밋 없이 취소 (스테이징만)
git revert --abort          # revert 작업 취소
```

## 동작 원리

1. 지정된 커밋의 변경사항을 **반대로** 적용
2. 새로운 revert 커밋 생성
3. 히스토리는 보존됨

## 장점

✅ **히스토리가 보존됨**
- 과거 커밋은 그대로 유지
- 투명한 작업 기록

✅ **공유된 브랜치에서 안전**
- 협업자에게 영향 없음
- 충돌 가능성 낮음

✅ **되돌리기 가능**
- revert 커밋도 다시 revert 가능
- 실수 복구 용이

## 예시
```bash
# 마지막 커밋 취소
git revert HEAD

# 특정 커밋 취소
git revert abc1234

# 여러 커밋 취소
git revert HEAD~3..HEAD

# 병합 커밋 취소
git revert -m 1 <병합커밋해시>

# 커밋 메시지 없이 revert
git revert --no-commit HEAD
git commit -m "Revert multiple changes"
```

## revert vs reset 비교

| 항목 | revert | reset |
|------|--------|-------|
| 히스토리 | 보존 | 삭제 |
| 새 커밋 | 생성 | 생성 안함 |
| 협업 | 안전 | 위험 |
| 사용 상황 | 공유 후 | 공유 전 |
| 복잡도 | 높음 | 낮음 |

## 충돌 해결

revert 중 충돌 발생 시:
```bash
# 1. 충돌 파일 확인
git status

# 2. 충돌 해결
# 파일 수정

# 3. 스테이징
git add <파일명>

# 4. revert 계속
git revert --continue

# 또는 취소
git revert --abort
```

## 사용 시나리오

### 시나리오 1: 배포 후 버그 발견
```bash
# 문제 있는 커밋 revert
git revert abc1234
git push origin main
```

### 시나리오 2: 실수로 병합한 경우
```bash
# 병합 커밋 revert
git revert -m 1 def5678
git push origin main
```

### 시나리오 3: 여러 커밋 한번에 revert
```bash
# 커밋 없이 여러 개 revert
git revert --no-commit HEAD~3..HEAD
git commit -m "Revert changes from last 3 commits"
```

## 최종 수정일
2025-11-20
