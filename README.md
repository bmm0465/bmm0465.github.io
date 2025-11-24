# ABCDE Project - 데이터 사이언스 포트폴리오 블로그

데이터와 교육의 결합을 통해, 더 나은 교실을 만들고자 합니다.

## 🚀 Jekyll 블로그

이 블로그는 Jekyll을 사용하여 구축되었습니다.

## 📦 설치 및 실행

### 로컬에서 실행하기

1. **Ruby와 Bundler 설치** (이미 설치되어 있다면 생략)
   ```bash
   # Windows의 경우 RubyInstaller 사용
   # https://rubyinstaller.org/
   ```

2. **의존성 설치**
   ```bash
   bundle install
   ```

3. **로컬 서버 실행**
   ```bash
   bundle exec jekyll serve
   ```

4. **브라우저에서 확인**
   - http://localhost:4000

## 📝 새 포스트 작성하기

`_posts/` 폴더에 새로운 Markdown 파일을 생성하세요.

파일명 형식: `YYYY-MM-DD-post-title.md`

예시:
```markdown
---
layout: post
title: "포스트 제목"
date: 2025-11-25
category: CategoryName
image: https://images.unsplash.com/...
---

포스트 내용...
```

## 🗂️ 프로젝트 구조

```
.
├── _config.yml          # Jekyll 설정
├── _layouts/            # 레이아웃 템플릿
│   ├── default.html
│   └── post.html
├── _includes/           # 재사용 가능한 컴포넌트
│   ├── nav.html
│   └── footer.html
├── _posts/              # 블로그 포스트 (Markdown)
├── index.html           # 메인 페이지
├── blog.html            # 블로그 리스트 페이지
├── style.css            # 스타일시트
└── Gemfile              # Ruby 의존성
```

## 🌐 GitHub Pages 배포

1. GitHub 저장소에 푸시
2. Settings > Pages에서 소스 브랜치 선택
3. 자동으로 빌드되어 배포됩니다

## 📚 주요 기능

- ✅ Jekyll 기반 정적 사이트 생성
- ✅ Markdown으로 포스트 작성
- ✅ 자동 카테고리 및 태그 생성
- ✅ 반응형 디자인
- ✅ 다크 테마

## 🔧 커스터마이징

- **스타일 수정**: `style.css` 파일 편집
- **레이아웃 수정**: `_layouts/` 폴더의 파일 편집
- **설정 변경**: `_config.yml` 파일 편집

## 📄 라이선스

© 2025 ABCDE Project. All Rights Reserved.
