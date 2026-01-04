# Translation Quality Workshop

AWS Bedrock과 Claude를 활용한 번역 품질 평가 및 개선 실습 워크샵입니다.

## 워크샵 개요

이 워크샵은 AI 기반 번역의 품질을 체계적으로 평가하고 개선하는 방법을 학습합니다.

**핵심 사이클:** 번역 → 평가 → 피드백 → 재번역 → 품질 향상 확인

### 학습 목표

- Zero-shot, Few-shot, 용어집 적용 등 다양한 번역 기법 비교
- Claude를 평가자(Judge)로 활용한 번역 품질 평가
- 충실도, 용어 일관성, 문화/톤 관점의 다각도 평가
- 평가 피드백을 활용한 번역 품질 개선 사이클 구현

### 대상

- AI/ML 엔지니어
- 번역 품질 관리 담당자
- 다국어 서비스 기획자

## 워크샵 구성

| 세션 | 내용 |
|------|------|
| Lab 1: 환경 설정 | Bedrock 연결, 샘플 데이터 로드, 출력 구조 설정 |
| Lab 2: 번역 기법 비교 | Zero-shot → Few-shot → 용어집 적용 번역 비교 |
| Lab 3: 품질 평가 - 충실도 | 의미 손실/왜곡, 숫자/단위 보존 평가 |
| Lab 4: 품질 평가 - 용어 일관성 | 용어집 준수, 브랜드명 정확도 평가 |
| Lab 5: 품질 평가 - 문화/톤 | 존대/격식, 브랜드 보이스 일관성 평가 |
| Lab 6: 피드백 기반 재번역 | 평가 결과 활용, 개선 사이클 실행 |
| Lab 7: 종합 분석 | Before/After 비교, 품질 향상 시각화 |

## 사전 요구사항

### AWS 설정

- AWS 계정 및 Bedrock 접근 권한
- Claude 모델 활성화 (Sonnet 4, Haiku 4)
- AWS CLI 설정 완료

```bash
aws configure
aws bedrock list-foundation-models --region us-west-2
```

### Python 환경

- Python 3.11+
- Jupyter Notebook 또는 JupyterLab

### 필요 라이브러리

```bash
pip install boto3 pandas matplotlib
```

### 빠른 시작

1. 저장소 클론
```bash
 git clone <repository-url>
 cd translation-quality-workshop
``` 
2. AWS 자격 증명 확인
 ```bash
 aws sts get-caller-identity
 ```

## 평가 점수 체계

모든 평가는 0-5점 체계를 사용합니다:

| 점수 | 판정 | 설명 |
|------|------|------|
| 5 | Pass | 완벽함 |
| 4 | Pass | 경미한 수정으로 자동 치유 가능 |
| 3 | Review | 경계 - 인간 검수 필요 |
| 0-2 | Fail | 심각한 오류 - 재번역 필요 |

자동 발행 기준: 모든 평가 항목 점수 ≥ 4

## 핵심 개념

### 번역 기법

- Zero-shot: 예시 없이 바로 번역
- Few-shot: 좋은 번역 예시 3-5개 제공
- 용어집 적용: 필수 용어 매핑 주입

### 평가 관점

- 충실도: 원문 의미 보존, 숫자/단위 정확성
- 용어 일관성: 용어집 준수, 브랜드명 정확도
- 문화/톤: 존대/격식, 브랜드 보이스, 자연스러운 표현


## 참고 자료

- [Amazon Bedrock 문서](https://docs.aws.amazon.com/bedrock/)

### 라이선스

이 워크샵 자료는 내부 교육 목적으로 제작되었습니다.
