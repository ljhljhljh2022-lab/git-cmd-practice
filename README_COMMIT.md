# COMMIT 명령어

`git commit` 명령어는 스테이징된 변경사항을 로컬 저장소에 기록합니다.

## 사용법
```bash
git commit -m "메시지"     # 메시지와 함께 커밋
git commit -am "메시지"    # add와 commit을 동시에
git commit --amend        # 마지막 커밋 수정
```

## 역할

- 변경사항의 스냅샷 저장
- 프로젝트 히스토리 기록
- 작업 내용을 영구적으로 보관

## 커밋 메시지 작성 규칙

- 첫 줄: 간단한 요약 (50자 이내)
- 빈 줄
- 상세한 설명 (필요시)

## 예시
```bash
# 간단한 커밋
git commit -m "Fix login bug"

# 추적 중인 파일 자동 add + commit
git commit -am "Update user profile"

# 마지막 커밋 수정
git commit --amend -m "Fix login bug and improve error handling"
```
