# 2026-08-20 논문 추천

## 검색 정보

- **연구 기준일**: 2026-08-20 (REQUESTED_DATE 사용)
- **실제 검색 창**: 2026-08-20 (당일) → 결과 없음 → 2026-08-14~2026-08-20 (7일) → 결과 없음 → **2026-07-22~2026-08-20 (30일, 채택)**
- **검색 쿼리**: `chest X-ray multi-institution generalization deep learning`

## 코호트 요약 (환자 단위 값 없음, 집계만)

- 총 272건 영상 판독, 고유 환자 153명 (합성/비식별 데이터, `is_synthetic = true`)
- 성별: 남 136 (평균 연령 48.7세), 여 136 (평균 연령 54.3세)
- 촬영 자세: PA 184건, AP 88건
- 수집 기관: INST01(62), INST02(56), INST03(54), INST05(52), INST04(48) — 5개 기관
- 진료과: radiology(57), internal_medicine(57), cardiology(53), emergency(53), pulmonology(52)
- 판독 상태: final(76), addendum(70), preliminary(68), amended(58)
- 소견 라벨: No Finding 145건, 나머지는 Infiltration(21), Atelectasis(16), Nodule(7), Fibrosis(6), Effusion(6), Cardiomegaly(5) 등 단일·복합 소견 다수 (예: Effusion|Infiltration 5건, Atelectasis|Consolidation|Effusion|Infiltration 2건)
- 추적 방문 수(followup_no): 평균 6.4회, 최대 63회
- 전 건에 판독문(report_text) 및 임상 정보(clinical_info) 텍스트 존재

## 검토 결과: 30일 창에서 6편 검색, 3편 채택

30일 창에서 검색된 6편 중 순수 방법론 리뷰나 우리 코호트의 영상 모달리티(단일 시점 흉부 X-ray)와 직접 관련이 낮은 논문(복부 CT 응급 분류, ECG/PPG 리뷰, 방법론 총론 리뷰)은 제외했습니다. 아래 3편은 다기관 흉부 영상 데이터의 일반화·감사 가능성이라는 주제에서 우리 코호트와 맞물리는 정도가 높아 채택했습니다.

### 채택 기준 (axes)

1. **기관 간 일반화** — 여러 병원/사이트에서 수집된 데이터에 대한 모델의 전이·일반화 성능을 다루는가
2. **다중 소견 라벨링** — 단일 영상에 여러 소견이 동시에 존재하는 복합 라벨 문제를 다루는가

## 채택 논문

### 1. Grounding Radiology Report Findings into Medical Image Segmentation (CF2Seg)
- **venue**: npj Digital Medicine · **axes**: 기관 간 일반화, 다중 소견 라벨링
- 판독문 서술만으로 병변 분할을 학습하는 CF2Seg는, 우리 코호트처럼 전 건에 판독문이 존재하고 다기관·다중 라벨 소견이 흔한 데이터에서 별도 픽셀 주석 없이 정량화를 시도할 수 있다는 아이디어를 준다.
- 우리 데이터에는 픽셀 단위 병변 경계 주석이 없어 분할 정확도 자체를 검증할 수는 없다.
- 링크: https://doi.org/10.1038/s41746-026-03051-0

### 2. CLEAR: an auditable foundation model for radiology grounded in clinical concepts
- **venue**: Nature Biomedical Engineering · **axes**: 기관 간 일반화, 다중 소견 라벨링
- 4개국 외부 데이터에서 검증된 개념 기반 감사 가능 모델로, 우리의 5개 기관·복합 소견 구조와 맞닿아 있다.
- 사전학습 규모(87만 건)와 우리 코호트(272건) 간 격차가 커서 보고된 성능 수치를 직접 재현할 수는 없다.
- 링크: https://doi.org/10.1038/s41551-026-01741-4

### 3. QoQ-Med3: a multimodal reasoning foundation model for clinical analysis
- **venue**: npj Digital Medicine · **axes**: 기관 간 일반화
- 여러 임상 사이트 간 이질성에 대한 일반화 평가 방법론이, 우리의 5개 기관·5개 진료과 구조의 일반화 점검 설계에 참고가 된다.
- 흉부 X-ray 단일 모달리티 특화 성능이 아니므로 우리 데이터로 71.3% 균형정확도 등 수치를 검증할 수 없다.
- 링크: https://doi.org/10.1038/s41746-026-02945-3

## 주의사항

본 추천은 자동 검색·집계 결과이며, 임상적 채택 여부는 반드시 담당 의료진의 검토를 거쳐야 합니다.
