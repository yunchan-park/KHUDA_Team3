# Step 2 결과: OOS 예측오차 구조 분석

- **OOS 설정**: 초기 24개월 학습(2013-02~2015-01) 후 확장 윈도우. OOS 구간 2015-02~2024-12, 관측 119개 ([final_final/materials/step2/step2_oos_error_test.csv](final_final/materials/step2/step2_oos_error_test.csv#L1-L2)).
- **예측오차 통계 (OOS)**:
  - 평균오차 1.03, HAC p=0.565 → 평균 편향 근거 약함.
  - DW=0.0489, AR(1)=0.9749 (HAC p≈0) → 강한 양의 지속성.
  - MAE=4.55, RMSE=6.74, 양/음 비율 0.639/0.361.
- **해석 (합리적 vs 진단적 기대)**:
  - 평균은 0과 통계적으로 구분 안 되지만, 매우 낮은 DW와 AR(1)≈1은 충격 후 오차가 한 방향으로 오래 지속됨을 시사 → **진단적 기대** 신호 우세.
  - 단순 OLS 기반 기대모형이 충격 반영 속도를 설명하지 못함. 구조적 모형 개선 필요.
- **가격충격 → 예측오차 LP (k=1~12)** ([final_final/materials/step2/step2_lp_error_response.csv](final_final/materials/step2/step2_lp_error_response.csv#L1-L13)) — PriceShock은 HPI_gr(주택가격 상승률)로 정의:
  - 모든 horizonte에서 5% 유의 없음 (최소 p≈0.079 @ k=12, 음(-) 방향).
  - 계수는 k≥7 이후 일관되게 음(-)이며 크기 확대(약 -2.77 @ k=12), 신뢰구간은 0 포함.
  - **시사점**: 가격충격이 누적될수록 오차가 음(-)쪽으로 기울 가능성은 보이나, 표본 크기·불확실성 탓에 통계적 유의는 확보 못함.
- **필수 산출물 위치**:
  - OOS 오차 시계열: [final_final/materials/step2/step2_oos_errors.csv](final_final/materials/step2/step2_oos_errors.csv).
  - 평균/지속성 통계: [final_final/materials/step2/step2_oos_error_test.csv](final_final/materials/step2/step2_oos_error_test.csv#L1-L2), [final_final/materials/step2/step2_oos_error_ar1.csv](final_final/materials/step2/step2_oos_error_ar1.csv#L1-L3).
  - LP 결과 표/그래프: [final_final/materials/step2/step2_lp_error_response.csv](final_final/materials/step2/step2_lp_error_response.csv#L1-L13), [final_final/materials/step2/step2_lp_error_response.png](final_final/materials/step2/step2_lp_error_response.png).
- **다음 단계**: Step 3에서 금리 -0.25%p 충격에 대한 실물(IP)·주택가격 동태 비교 LP 수행 및 누적 반응 정리.
