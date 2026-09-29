# 블루 테마와 배포

- 기본 강조색 / 버튼 / 강조 텍스트: `#2B61D6` (`--primary`)
- 보조 강조색 / 테두리 / 그라데이션: `#4B90E2` (`--secondary`)
- 옅은 배경과 그림자는 위 두 색상의 블루 계열 변형을 사용합니다.
- 오류 표시와 고객사 로고의 고유 색상은 유지합니다.

## 이미지

기존 PNG를 참조하여 내장 AI 이미지 편집 도구로 블루 버전을 생성했습니다.
최종 파일은 기존 경로인 `public/assets/figma/`, `public/assets/subvisual/`,
`public/assets/`와 `public/favicon.png`, `public/og-image.png`에 적용합니다.
동일한 원본을 사용하는 여러 페이지에는 같은 편집 결과를 적용합니다.
SVG는 도형과 좌표를 보존하고 색상 값만 변경합니다.

공통 이미지 편집 프롬프트:

> Edit this exact website asset by changing ONLY teal, green and cyan brand surfaces
> to royal blue #2B61D6 and sky blue #4B90E2, with pale blue tints and deeper blue
> shadows. Preserve all shapes, composition, object positions, perspective,
> 3D materials, white/gray areas, text and crop. No new objects. Do not change
> geometry or rearrange items. No green/teal remaining. Match original aspect
> ratio and preserve transparent background if present.

각 이미지의 원래 크기, 투명 배경 여부, 스프라이트 위치 보존 조건을 추가했습니다.
AI 편집 특성상 재질과 미세한 디테일은 원본과 차이가 있을 수 있습니다.

## 메인 영상

사용자가 제공한 `visual_video.mp4`를 재인코딩 없이
`public/assets/visual-video.mp4`로 복사했습니다.
SHA-256: `3CB488A59DD305169A731932FC84DC00A26C28E16F5202F149AC72FF132ECDA9`

## GitHub Pages

- URL: https://leejinho970715-star.github.io/digital_ware_ver.2/
- 배포 방식: GitHub Actions, `main` 푸시 시 자동 배포
- 빌드 경로: `BASE_PATH=/digital_ware_ver.2/`
- 빌드 산출물: `out/`
- 원본 `digital_ware` 저장소와 기존 사이트의 배포 설정은 변경하지 않습니다.

로컬 개발: `npm ci` → `npm run dev`.
배포용 빌드는 `.github/workflows/pages.yml`에서 수행합니다.
