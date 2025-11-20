# ADD 명령어

`git add` 명령어는 작업 디렉토리의 변경사항을 스테이징 영역에 추가합니다.

## 사용법
```bash
git add <파일명>        # 특정 파일 추가
git add .              # 모든 변경사항 추가
git add *.txt          # 특정 패턴의 파일 추가
```

## 역할

- 커밋할 파일을 선택
- 변경사항을 임시 저장
- 스테이징 영역(Staging Area)에 파일 추가

## 예시
```bash
# 단일 파일 추가
git add README.md

# 현재 디렉토리의 모든 변경사항 추가
git add .

# 특정 확장자 파일만 추가
git add *.md
```
