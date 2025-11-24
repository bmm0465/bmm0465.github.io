# 🚀 Jekyll 로컬 테스트 가이드 (Windows)

Windows에서 Jekyll 블로그를 로컬에서 테스트하는 방법입니다.

## 📋 사전 준비

### 1단계: Ruby 설치 확인

먼저 Ruby가 설치되어 있는지 확인합니다:

```bash
ruby -v
```

**Ruby가 설치되어 있지 않다면:**

1. **RubyInstaller 다운로드**
   - https://rubyinstaller.org/downloads/ 접속
   - **Ruby+Devkit 3.2.x** 버전 다운로드 (권장)
   - 설치 시 "Add Ruby executables to your PATH" 체크

2. **설치 확인**
   ```bash
   ruby -v
   # 예: ruby 3.2.0 (2023-12-25 revision 5124f9ac75) [x64-mingw-ucrt]
   ```

### 2단계: Bundler 설치

Ruby가 설치되어 있다면 Bundler를 설치합니다:

```bash
gem install bundler
```

설치 확인:
```bash
bundle -v
```

## 🔧 프로젝트 설정

### 3단계: 프로젝트 폴더로 이동

터미널(CMD 또는 PowerShell)에서 프로젝트 폴더로 이동:

```bash
cd C:\Users\김민제\Documents\Dev\abcde
```

### 4단계: 의존성 설치

프로젝트의 Gemfile에 명시된 패키지들을 설치합니다:

```bash
bundle install
```

**⚠️ 주의사항:**
- 첫 설치 시 시간이 걸릴 수 있습니다 (5-10분)
- Windows Defender나 방화벽 경고가 나올 수 있지만 허용하세요
- 오류가 발생하면 관리자 권한으로 실행해보세요

### 5단계: Jekyll 서버 실행

의존성 설치가 완료되면 로컬 서버를 실행합니다:

```bash
bundle exec jekyll serve
```

또는 간단하게:

```bash
jekyll serve
```

**성공 메시지 예시:**
```
Configuration file: C:/Users/김민제/Documents/Dev/abcde/_config.yml
            Source: C:/Users/김민제/Documents/Dev/abcde
       Destination: C:/Users/김민제/Documents/Dev/abcde/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in X.XXX seconds.
 Auto-regeneration: enabled for 'C:/Users/김민제/Documents/Dev/abcde'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

### 6단계: 브라우저에서 확인

브라우저를 열고 다음 주소로 접속:

```
http://localhost:4000
```

또는

```
http://127.0.0.1:4000
```

## 🎯 유용한 명령어

### 서버 옵션

```bash
# 포트 변경 (기본: 4000)
bundle exec jekyll serve --port 4001

# 호스트 변경 (외부 접근 허용)
bundle exec jekyll serve --host 0.0.0.0

# 자동 재생성 비활성화 (빌드 속도 향상)
bundle exec jekyll serve --no-watch

# 상세 로그 출력
bundle exec jekyll serve --verbose
```

### 빌드만 하기 (서버 실행 없이)

```bash
bundle exec jekyll build
```

빌드된 파일은 `_site` 폴더에 생성됩니다.

## ❗ 문제 해결

### 문제 1: "bundle: command not found"

**해결:**
```bash
gem install bundler
```

### 문제 2: "Could not locate Gemfile"

**해결:** 프로젝트 루트 폴더에서 명령어를 실행해야 합니다.

### 문제 3: "jekyll: command not found"

**해결:**
```bash
bundle exec jekyll serve
```
`bundle exec`를 앞에 붙여서 실행하세요.

### 문제 4: 포트 4000이 이미 사용 중

**해결:**
```bash
bundle exec jekyll serve --port 4001
```
다른 포트를 사용하세요.

### 문제 5: UTF-8 인코딩 오류

**해결:** `_config.yml` 파일이 UTF-8로 저장되어 있는지 확인하세요.

### 문제 6: Windows에서 경로 오류

**해결:** Jekyll 4.x는 Windows를 잘 지원하지만, 만약 문제가 있다면:
```bash
set JEKYLL_ENV=production
bundle exec jekyll serve
```

## 🔄 변경사항 반영

Jekyll은 파일 변경을 자동으로 감지하고 재빌드합니다:
- HTML/CSS 파일 수정 → 자동 새로고침
- `_config.yml` 수정 → 서버 재시작 필요 (Ctrl+C 후 다시 실행)
- 새 포스트 추가 → 자동 반영

## 📝 새 포스트 테스트

1. `_posts/` 폴더에 새 파일 생성
2. 파일명: `2025-11-25-test-post.md`
3. Front Matter 추가:
   ```markdown
   ---
   layout: post
   title: "테스트 포스트"
   date: 2025-11-25
   category: Test
   ---
   
   테스트 내용입니다.
   ```
4. 브라우저에서 자동으로 반영되는지 확인

## 🛑 서버 중지

서버를 중지하려면:
```
Ctrl + C
```

터미널에서 `Ctrl + C`를 누르면 서버가 중지됩니다.

---

**💡 팁:** 개발 중에는 서버를 계속 실행해두고, 파일을 수정하면 자동으로 반영됩니다!

