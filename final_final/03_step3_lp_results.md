# Step 3 결과: 금리 -0.25%p 충격의 전달 경로 (Local Projection)

- **모형**: $Y_{t+k} = \alpha_k + \beta_k \Delta r_t + \gamma_k Z_t + u_t$, k=1~12, 통제 $Z_t$=CPI, IP, CSI, 및 shock/target 래그 3개. HAC(maxlags=k).
- **스케일링**: 금리 인하 0.25%p → $\beta_k \times (-0.25)$, 누적 $Cum_k$ 계산.
- **산출물**: 원본 계수 [final_final/materials/step3/step3_lp_bir.csv](final_final/materials/step3/step3_lp_bir.csv#L1-L25), 스케일·신뢰구간 [final_final/materials/step3/step3_lp_bir_scaled_025cut.csv](final_final/materials/step3/step3_lp_bir_scaled_025cut.csv#L1-L25), 누적 [final_final/materials/step3/step3_lp_cumulative.csv](final_final/materials/step3/step3_lp_cumulative.csv#L1-L25), 그래프 [final_final/materials/step3/step3_lp_HPI_gr.png](final_final/materials/step3/step3_lp_HPI_gr.png), [final_final/materials/step3/step3_lp_IP_gr.png](final_final/materials/step3/step3_lp_IP_gr.png).

## 1) 자산가격 트랙: 주택가격 상승률 (HPI_gr)
- 유의 시작: k=3 (p≈0.0058), 이후 다수 월에서 음(-) 반응 유의.
- 단기~중기 효과(스케일 -0.25 기준):
  - k=3: +0.208 (CI 0.060~0.356)
  - k=4: +0.378 (CI 0.195~0.560)
  - k=5: +0.476 (CI 0.239~0.713)
  - k=6: +0.505 (CI 0.200~0.809)
  - k=7: +0.370 (CI 0.028~0.713)
  - k=8: +0.445 (CI 0.158~0.732)
  - k=9: +0.353 (CI 0.158~0.547)
  - k=11: +0.259 (CI 0.038~0.479)
  - k=12: +0.304 (CI 0.103~0.505)
- 누적 반응(스케일 -0.25): k=6 시점 약 +1.64, k=12 시점 약 +3.56 ([final_final/materials/step3/step3_lp_cumulative.csv](final_final/materials/step3/step3_lp_cumulative.csv#L1-L13)).
- 해석: 금리 0.25%p 인하가 3~6개월 시점부터 주택가격 상승을 유의하게 견인하며, 1년 누적효과도 플러스 → 자산시장 경로가 빠르고 크다.

## 2) 실물 트랙: 산업생산 성장률 (IP_gr)
- 유의 반응: k=2에서 음(-) 반응 유의 (p≈0.0058, 스케일 +2.99). 그 외 구간은 신뢰구간이 0을 포함.
- 스케일 -0.25 기준:
  - k=2: +2.99 (CI 0.864~5.117) — 단기 1회성 양(+) 반응.
  - 나머지 월은 0 포함, 방향 혼재.
- 누적 반응(스케일 -0.25): k=2 시점 +1.60에서 이후 진폭이 축소·진동, k=12 시점 +1.03 ([final_final/materials/step3/step3_lp_cumulative.csv](final_final/materials/step3/step3_lp_cumulative.csv#L13-L25)).
- 해석: 실물경로는 초기 2개월 반짝 양(+) 반응 외에는 명확한 패턴이 약함. 자산 대비 속도·지속성이 낮다.

## 3) 전달 경로 비교 (Notion 요구 반영)
- 최초 유의 시점: 자산 k=3, 실물 k=2. 그러나 자산은 이후 다수 월에서 유의/지속, 실물은 1회성.
- 누적 크기: 12개월 누적 자산 +3.56 vs 실물 +1.03 → 자산경로 우세.
- 정책 시사점: 금리 인하는 자산시장(주택가격)에 더 빠르고 크게 전달되어 과열 위험 가능. 실물 부양 효과는 상대적으로 작고 불확실.

## 4) 다음 단계
- Step 4에서 합리적 vs 진단적 기대 판정과 본 전달경로 비교를 통합해 발표 결론 정리.
