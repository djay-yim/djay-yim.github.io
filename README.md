# 지킬(Jekyll) 기반 GitHub 블로그

이 저장소는 Jekyll과 GitHub Pages를 사용한 개인 블로그입니다. [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) 테마를 기반으로 제작되었습니다.

## 프로젝트 소개

이 블로그는 개발 관련 지식과 경험을 공유하기 위한 공간입니다. Jekyll 정적 사이트 생성기와 GitHub Pages를 활용하여 무료로 호스팅되고 있습니다.

## 로컬 환경 설정

### 필수 요구사항

- Ruby (2.5.0 이상 권장)
- RubyGems
- GCC 및 Make
- Bundler

### 설치 과정

1. Ruby 설치
   ```bash
   # macOS (Homebrew 이용)
   brew install rbenv
   rbenv init
   rbenv install 3.0.0 # 또는 최신 버전
   rbenv global 3.0.0
   ```

2. 프로젝트 의존성 설치
   ```bash
   gem install bundler jekyll
   bundle install
   ```

3. Ruby 3.0 이상 사용 시 webrick 추가 설치
   ```bash
   bundle add webrick
   ```

## 로컬 서버 구동 및 종료

### 서버 구동

```bash
bundle exec jekyll serve
```

성공적으로 구동되면 기본적으로 `http://localhost:4000`에서 사이트에 접속할 수 있습니다.

추가 옵션:
- 상세 오류 확인: `bundle exec jekyll serve --trace`
- 초안 포함: `bundle exec jekyll serve --drafts`
- 다른 포트 사용: `bundle exec jekyll serve --port 4001`

### 서버 종료

서버가 실행 중인 터미널 창에서 `Ctrl + C` 키 조합을 누르면 서버가 종료됩니다.

## 포스트 작성 가이드

### 새 포스트 생성

1. `_posts` 디렉토리에 `YYYY-MM-DD-제목.md` 형식의 파일을 생성합니다.
2. 다음과 같은 YAML 헤더(Front Matter)를 파일 상단에 추가합니다:

```yaml
---
title: "포스트 제목"
last_modified_at: YYYY-MM-DD
toc: true
toc_sticky: true
categories:
  - 카테고리명
tags:
  - 태그1
  - 태그2
---
```

### 마크다운 문법

포스트는 마크다운 문법을 사용하여 작성합니다. 주요 문법:

```markdown
# 제목 1
## 제목 2
### 제목 3

*기울임체* 또는 _기울임체_
**굵게** 또는 __굵게__

- 글머리 기호 목록
- 항목 2
  - 하위 항목

1. 번호 매기기
2. 항목 2

[링크 텍스트](URL)

![이미지 설명](/assets/images/파일명.jpg)

> 인용문

`인라인 코드`

```python
# 코드 블록
def hello():
    print("Hello World!")
```
```

### 이미지 추가

이미지 파일은 `/assets/images/` 디렉토리에 저장한 후 다음과 같이 참조합니다:

```markdown
![이미지 설명](/assets/images/파일명.jpg)
```

## 문제 해결

### favicon.ico 오류

`ERROR '/favicon.ico' not found` 오류가 발생하는 경우:

1. 프로젝트 루트에 favicon.ico 파일 추가
   ```bash
   touch favicon.ico
   ```
2. 또는 `_includes/head.html` 파일에 다음 코드 추가:
   ```html
   <link rel="shortcut icon" href="/favicon.ico" type="image/x-icon">
   <link rel="icon" href="/favicon.ico" type="image/x-icon">
   ```

## 참고 자료

- [Jekyll 공식 문서](https://jekyllrb-ko.github.io/)
- [Minimal Mistakes 테마 가이드](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)
- [GitHub Pages 공식 문서](https://docs.github.com/en/pages)