# MERGE 명령어

`git merge` 명령어는 다른 브랜치의 변경사항을 현재 브랜치에 통합합니다.

## 사용법
```bash
git merge <브랜치명>           # 브랜치 병합
git merge --no-ff <브랜치>     # Fast-forward 없이 병합
git merge --squash <브랜치>    # 커밋을 하나로 합쳐서 병합
git merge --abort             # 병합 취소
```

## 역할

- 여러 브랜치의 작업 통합
- 협업 시 코드 합치기
- 기능 개발 완료 후 메인 브랜치에 반영

## 병합 유형

### Fast-Forward 병합
- 브랜치가 일직선상에 있을 때
- 단순히 포인터만 이동

### 3-way 병합
- 브랜치가 분기되었을 때
- 새로운 병합 커밋 생성

## 예시
```bash
# feature 브랜치를 main에 병합
git checkout main
git merge feature

# Fast-forward 없이 병합 (병합 커밋 생성)
git merge --no-ff feature

# 충돌 발생 시 병합 취소
git merge --abort
```

## 병합 충돌 해결

1. 충돌 파일 확인: `git status`
2. 충돌 부분 수정
3. 수정된 파일 스테이징: `git add <파일명>`
4. 병합 완료: `git commit`
