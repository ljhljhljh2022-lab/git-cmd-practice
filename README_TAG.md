# TAG 명령어

`git tag` 명령어는 특정 커밋에 이름표(태그)를 붙여 버전을 관리합니다.

## 사용법
```bash
git tag v1.0.0                  # Lightweight 태그
git tag -a v1.0.0 -m "메시지"   # Annotated 태그 (권장)
git tag -l                      # 태그 목록 확인
git tag -l "v1.*"               # 패턴으로 태그 검색
git push origin v1.0.0          # 특정 태그 푸시
git push origin --tags          # 모든 태그 푸시
```

## 역할

- 릴리스 버전 표시
- 중요한 커밋 북마크
- 특정 시점의 스냅샷 표시

## 태그 유형

### Lightweight Tag
- 단순한 포인터
- 메타데이터 없음
- 임시 마킹용

### Annotated Tag (권장)
- 완전한 Git 객체
- 태그 작성자, 날짜, 메시지 포함
- 공식 릴리스에 사용

## 예시
```bash
# Lightweight 태그 생성
git tag v1.0.0

# Annotated 태그 생성 (권장)
git tag -a v1.0.0 -m "Release version 1.0.0"

# 특정 커밋에 태그 추가
git tag -a v0.9.0 9fceb02 -m "Beta release"

# 태그 확인
git show v1.0.0

# 태그 삭제
git tag -d v1.0.0

# 원격 태그 삭제
git push origin --delete v1.0.0
```

## 시맨틱 버저닝 (Semantic Versioning)

형식: **MAJOR.MINOR.PATCH** (예: v1.2.3)

- **MAJOR**: 하위 호환되지 않는 API 변경
- **MINOR**: 하위 호환되는 기능 추가
- **PATCH**: 하위 호환되는 버그 수정
