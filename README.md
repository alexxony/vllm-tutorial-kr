# vllm-tutorial-kr

[vLLM](https://github.com/vllm-project/vllm) 공식 튜토리얼을 한국어로 번역하고,
Google Colab(L4 GPU)에서 직접 실행한 결과와 유의점을 덧붙인 Jupyter 노트북 모음입니다.

원문 기준: [`vllm-project/vllm` v0.30.0](https://github.com/vllm-project/vllm/tree/v0.30.0) (Apache-2.0)

## 노트북

| 파일 | 내용 | Colab |
|---|---|---|
| [`notebooks/01_quickstart.ipynb`](notebooks/01_quickstart.ipynb) | Offline 추론 + OpenAI 호환 서버 기동 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alexxony/vllm-tutorial-kr/blob/main/notebooks/01_quickstart.ipynb) |

## 실행 환경

- **GPU**: L4 권장(Colab Pro/Pro+, 메뉴 → 런타임 유형 변경 → 하드웨어 가속기 → L4).
  T4는 최근(2026년 9월 기준) 관련 오픈 버그가 다수 있어 배제했습니다
  ([#43576](https://github.com/vllm-project/vllm/issues/43576),
  [#36589](https://github.com/vllm-project/vllm/issues/36589),
  [#36802](https://github.com/vllm-project/vllm/issues/36802)).
- **vLLM 버전**: `0.30.0`으로 고정. 이후 vLLM이 업데이트되어도 이 튜토리얼의 코드·설명은
  이 버전 기준입니다.

## 유의점

- offline 추론 인스턴스(`LLM(...)`)와 온라인 서버를 같은 커널에서 연속 실행하면 GPU 메모리가
  해제되지 않아 OOM이 발생합니다. 노트북 안에 이 지점을 명시했습니다.
- 서버는 백그라운드 프로세스로 띄우고 `/health`를 폴링해야 합니다 — 포그라운드로 띄우면
  `nbconvert` 자동 실행이 끝나지 않습니다.
- 실습이 끝나면 반드시 런타임을 종료하세요. L4는 켜져 있는 동안 계속 컴퓨트 유닛을 소모합니다.

## 라이선스

이 저장소의 코드·설명은 [MIT License](LICENSE)로 배포합니다.
원문 발췌 부분의 출처·라이선스는 [NOTICE](NOTICE)를 참고하세요.
