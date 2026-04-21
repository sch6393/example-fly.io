# example-fly.io

코파일럿을 통한 fly.io 환경 배포

## 개요

Node.js 기반의 간단한 HTTP 웹 서버를 [fly.io](https://fly.io) 플랫폼에 배포하는 예제입니다.

## 로컬 실행

```bash
# 의존성 설치 (현재 없음)
npm install

# 서버 실행
npm start
# → http://localhost:3000
```

## fly.io 배포

### 사전 준비

1. [fly.io 계정 가입](https://fly.io/app/sign-up)
2. [flyctl CLI 설치](https://fly.io/docs/hands-on/install-flyctl/)
3. 로그인

```bash
flyctl auth login
```

### 배포 절차

```bash
# 앱 이름을 유니크하게 변경 (fly.toml의 app 항목)
# 예) app = "my-node-server-12345"

# 앱 생성 및 배포
flyctl launch --no-deploy   # fly.toml을 기반으로 앱 생성
flyctl deploy               # 빌드 후 배포
```

### 배포 확인

```bash
# 앱 상태 확인
flyctl status

# 브라우저로 열기
flyctl open
```

## 프로젝트 구조

```
.
├── server.js       # Node.js HTTP 서버
├── package.json    # 프로젝트 메타데이터
├── Dockerfile      # 컨테이너 이미지 정의
├── fly.toml        # fly.io 배포 설정
└── .gitignore
```
