<h1 align="center">JavaScript & TypeScript Library Template</h1>

<p align="center">
간결하고 강력한 환경을 제공하는 <b>JavaScript & TypeScript 라이브러리 개발 템플릿</b>입니다.<br>
<code>tsup</code>을 기반으로 CJS, ESM 빌드를 지원하며 GitHub Actions를 통한 자동 배포 시스템이 구축되어 있습니다.
</p>

## 🚀 주요 특징

- **Dual Build**: `tsup`을 사용하여 `CommonJS(.js)`와 `ESM(.mjs)` 환경을 모두 지원합니다.
- **TypeScript First**: 자동 `.d.ts` 선언 파일 생성 및 타입 체크가 포함되어 있습니다.
- **Modern Stack**: SWC 기반의 빠른 테스트(`Jest`), ESLint, Prettier 설정이 완료되어 있습니다.
- **CI/CD Ready**: 특정 커밋 메시지(`release:`, `hotfix:`) 푸시 시 자동으로 `release` 브랜치 업데이트 및 GitHub Release를 생성합니다.

---

## 📦 설치 방법 (Installation)

GitHub 레포지토리를 통해 직접 의존성을 추가할 수 있습니다.

```bash
# 최신 안정 버전(release 브랜치) 설치
npm install github:yundohyun/js-libs-template#release

# 특정 태그(버전) 설치
npm install github:yundohyun/js-libs-template#v0.0.1
```

---

## 🛠 개발 명령어 (Scripts)

### 빌드 및 개발

- `npm run dev`: 개발 모드 실행 (변경 감지 및 자동 빌드)
- `npm run build`: 프로덕션용 최적화 빌드 실행 (`dist/` 폴더 생성)

### 품질 관리

- `npm run type-check`: TypeScript 타입 에러 체크
- `npm run test`: Jest를 이용한 테스트 실행
- `npm run lint`: ESLint 코드 스타일 검사
- `npm run format`: Prettier 코드 포맷팅 적용

---

## 🚀 배포 워크플로우 (Deployment)

본 템플릿은 GitHub Actions를 활용한 자동화된 릴리즈 프로세스를 따릅니다.

1. `main` 브랜치에 코드를 푸시할 때, 커밋 메시지에 버전 번호를 **코드 블록**으로 포함하세요.
   - 예: ``release: `0.1.0` 릴리즈``
2. 워크플로우가 자동으로 실행되어 다음 작업을 수행합니다:
   - 테스트 및 타입 체크 수행
   - `dist` 폴더 빌드
   - `release` 브랜치에 빌드 결과물 푸시
   - 해당 버전으로 **GitHub Release** 생성 및 빌드 파일 압축 업로드

---

## 📂 프로젝트 구조 (Structure)

```text
.
├── src/                # 소스 코드
│   └── index.ts        # 엔트리 포인트
├── dist/               # 빌드 결과물 (npm publish/배포용)
├── out/                # CI/CD 배포 준비용 임시 폴더
├── tests/              # 테스트 코드
└── package.json        # 프로젝트 설정 및 의존성
```

---

## 📄 라이선스 (License)

이 프로젝트는 [MIT](LICENSE) 라이선스를 따릅니다.
