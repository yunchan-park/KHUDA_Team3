# 최종 분석 수행 계획 (Execution Plan)

본 계획은 `variable_definitions.md`에 정의된 변수와 수식을 바탕으로, 발표 자료(Notion) 요구사항에 맞추어 분석을 순차적으로 수행하고 그 결과를 `final_final` 폴더에 정리하기 위한 로드맵입니다.

## 1. Step 1: 기대가 합리적인지 검정 (OOS 회귀)
* **목적**: 기대인플레이션($Expectation_t$)이 1년 뒤 실제 인플레이션($\Delta P_{t+12}$)을 설명하는지, 합리적 기대 조건을 OOS에서 평가합니다.
* **분석 방법**: 초기 60개월 학습 후 1개월씩 확장(Expanding Window)하며 OOS 회귀 $\Delta P_{t+12}=\alpha+\beta Expectation_t+\epsilon_t$ 추정. 다양한 윈도우 사이즈 민감도 체크. 잔차 HAC(Newey-West) SE.
* **산출물**: `01_step1_results.md` (윈도우별 계수/유의성, 회귀 그래프, 검정 통계량, 합리적 기대 vs 진단적 기대 해석 틀 포함)

## 2. Step 2: 잔차(예측오차) 구조 분석 (OOS)
* **목적**: 예측오차 $\epsilon_t$가 평균 0이고 빠르게 소멸하는지(합리적) vs 한 방향 지속(진단적)인지 평가. 가격충격 후 오차의 동태 확인.
* **분석 방법**:
    1. OOS 예측오차 계산(Step 1 잔차). 평균=0 검정, Durbin-Watson, AR(1) 추정.
    2. Local Projection: 가격충격($PriceShock_t$)이 $\epsilon_{t+k}$에 미치는 효과 $\epsilon_{t+k}=\alpha_k+\beta_k PriceShock_t+u_t$ (k=1~12).
* **산출물**: `02_step2_oos_results.md` (평균/지속성 통계, 가격충격→잔차 IRF 그래프, 유의 시작 시점·부호 표, 합리적 vs 진단적 분류)

## 3. Step 3: 금리 인하 전달 경로 비교 (Local Projection)
* **목적**: 기준금리 -0.25%p 충격이 실물(IP 성장)과 자산가격(주택가격 상승률)에 어떻게, 얼마나 빠르게, 얼마나 크게 누적 전달되는지 비교.
* **분석 방법**:
    1. 두 개의 Y 트랙: (a) IP 성장률, (b) 주택가격 상승률. 회귀식 $Y_{t+k}=\alpha_k+\beta_k \Delta r_t+\gamma_k Z_t+u_t$, k=1~12, 통제 $Z_t$=CPI, IP, CSI, HPI.
    2. 스케일링: $\beta_k \times (-0.25)$로 0.25%p 인하 충격 변환. 누적 반응 $Cum_k$ 계산.
* **산출물**: `03_step3_lp_results.md` (성장 vs 자산 반응 그래프, 최초 유의 시점, 피크/누적 비교 표, 0.25%p 스케일 반응값)

## 4. Step 4: 종합 결론 (합리적 vs 진단적 기대 + 전달경로)
* **목적**: 기대 형성 메커니즘 판정(합리적 vs 진단적)과 통화정책 전달경로(실물 vs 자산) 핵심 메시지 정리.
* **산출물**: `04_conclusion.md` (판정표, 정책 시사점 요약, 발표용 스크립트 초안)

---
**진행 순서**: 위 계획에 따라 `01_step1_results.md`부터 순차 실행·기록합니다. Notion 요구사항(윈도우 민감도, OOS, 가격충격→잔차 IRF, 금리 전달경로 비교)을 모두 포함합니다.
