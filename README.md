# FlyPenguin 🐧

> 📚 본 프로젝트는 패스트캠퍼스(FastCampus) 강의 자료입니다.

웹캠 앞에서 **팔을 날개처럼** 움직여 펭귄을 조종하는 레트로 로우폴리 3D 비행 웹앱입니다. 별도 빌드 없이 `index.html` 하나만 열면 동작합니다.

## 입력 → 반응 → 형태

- **입력** — MediaPipe Pose로 어깨·팔꿈치·손목을 실시간 추적
- **반응** — 팔 제스처를 비행 조작으로 매핑
- **형태** — three.js 로우폴리 씬(펭귄 + 끝없이 흐르는 지형: 나무·돌·구름)

## 조작법

| 동작 | 결과 |
|---|---|
| 양팔 수평으로 벌리기 | 직진 |
| 오른팔 내리기 | 오른쪽으로 |
| 왼팔 내리기 | 왼쪽으로 |
| 맹렬하게 파닥파닥 | 상승 (멈추면 중력으로 하강) |

## 실행

브라우저는 보안 컨텍스트에서만 웹캠을 허용하므로 로컬 서버로 띄웁니다.

```bash
python3 -m http.server 8731
# 브라우저에서 http://localhost:8731/index.html 접속 → "웹캠 켜고 시작"
```

## 기술 스택

- [MediaPipe Tasks Vision](https://ai.google.dev/edge/mediapipe) — `pose_landmarker_lite`
- [three.js](https://threejs.org/) — r160 (ESM, importmap)
- 순수 HTML/JS 단일 파일, CDN 의존성만 사용
