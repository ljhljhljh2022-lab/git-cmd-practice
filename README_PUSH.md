# PUSH 명령어

`git push` 명령어는 로컬 커밋을 원격 저장소에 업로드합니다.

## 사용법
```bash
git push origin main      # main 브랜치를 원격에 푸시
git push -u origin main   # 기본 upstream 설정
git push --tags           # 태그 푸시
git push --all            # 모든 브랜치 푸시
```

## 역할

- 로컬 변경사항을 원격 저장소와 동기화
- 다른 개발자와 코드 공유
- 백업 및 협업 지원

## 옵션 설명

- `-u` (--set-upstream): 기본 원격 브랜치 설정
- `--force`: 강제 푸시 (주의 필요!)
- `--tags`: 태그도 함께 푸시

## 예시
```bash
# 기본 푸시
git push origin main

# 처음 푸시 시 upstream 설정
git push -u origin main

# 이후에는 간단하게
git push

# 태그와 함께 푸시
git push origin main --tags
```
