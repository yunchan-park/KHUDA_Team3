# Step 1 결과: 기대가 합리적인지 검정 (OOS 회귀)

- **모형**: $\Delta P_{t+12} = \alpha + \beta\,Expectation_t + \epsilon_t$ (CSI_idx로 기대, HPI_12m_ahead_gr로 향후 물가) — HAC(Newey-West) 표준오차.
- **OOS 설정**: 초기 24개월 학습(2013-02~2015-01) 후 확장 윈도우로 2015-02~2024-12까지 119개 OOS 예측.
- **주요 수치** (세부는 파일 참조):
  - In-sample: $\beta=0.301$ (p≈2.8e-14), $R^2=0.337$ ([final_final/materials/step1/step1_regression.csv](final_final/materials/step1/step1_regression.csv#L1-L3)).
  - In-sample 잔차: 평균≈0 (p≈1), DW=0.103, AR(1)=0.948 (p≈0) → 잔차 고도 자기상관 ([final_final/materials/step1/step2_residual_diagnostics.csv](final_final/materials/step1/step2_residual_diagnostics.csv#L1-L2)).
  - OOS 예측오차(초기창 24개월): 평균 1.03 (HAC p=0.565), DW=0.0489, AR(1)=0.9749 (HAC p≈0), MAE=4.55, RMSE=6.74, 양/음 오차 비율 0.639/0.361 ([final_final/materials/step2/step2_oos_error_test.csv](final_final/materials/step2/step2_oos_error_test.csv#L1-L2), [final_final/materials/step2/step2_oos_error_ar1.csv](final_final/materials/step2/step2_oos_error_ar1.csv#L1-L3)).
- **해석 (합리적 vs 진단적 기대 틀)**:
  - 평균오차는 0과 통계적으로 구분되지 않음 → 평균 편향 증거는 약함.
  - 그러나 DW≈0.05, AR(1)≈0.98로 오차가 강하게 지속 → 충격 후 한 방향으로 끌려가는 **진단적 기대** 신호가 뚜렷함.
  - 잔차 자기상관이 높아 단순 OLS 모형이 기대 형성을 완전히 설명하지 못함. 추가 설명변수/비선형 또는 다른 기대 지표 검토 필요.
- **시각화**: 회귀 적합도/잔차 산점 [final_final/materials/step1/step1_regression_plot.png](final_final/materials/step1/step1_regression_plot.png). OOS 오차 시계열은 [final_final/materials/step2/step2_oos_errors.csv](final_final/materials/step2/step2_oos_errors.csv)로 확인.
- **다음 조치**:
  - (필수) 본 결과는 초기창 24개월 OOS 기준이며, 발표 시 이 기준을 명시.
  - Step 2에서 가격충격→오차 IRF(LP) 수행하여 지속성의 방향·시점 확인 예정.
