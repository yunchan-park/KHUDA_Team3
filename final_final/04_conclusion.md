# Step 4: 종합 결론 (합리적 vs 진단적 기대, 전달경로)

## 1. 기대 형성 판정
- **평균 편향**: OOS 평균오차 1.03, HAC p=0.565 → 평균은 0과 구분되지 않음.
- **지속성**: DW≈0.049, AR(1)≈0.975 (HAC p≈0) → 강한 양의 자기상관. 충격 후 오차가 한 방향으로 오래 지속 → **진단적 기대** 신호 우세.
- **가격충격→오차 IRF**: 모든 k에서 5% 유의는 아니나, k≥7 이후 음(-) 방향 확대 가능성. 통계적 유의는 확보 못함.
- **종합**: 평균은 합리적이나, 동태적 특성(지속성)이 진단적 기대에 가깝다. 추가 설명변수/모형 개선 필요.

## 2. 금리 인하 전달경로 (자산 vs 실물)
- **자산경로(주택가격)**: 금리 -0.25%p 시 k=3부터 유의한 양(+) 반응, 12개월 누적 +3.56. 빠르고 지속적.
- **실물경로(IP)**: k=2에서 단기 양(+) 반응 유의, 이후 불확실. 12개월 누적 +1.03. 속도·지속성 모두 제한적.
- **비교**: 전달 속도는 실물(k=2)이 더 빠르지만 일회성; 규모·지속성은 자산(k=3 이후 다수 유의, 누적 더 큼) 우세.

## 3. 정책 시사점
1) 금리 인하 시 자산시장(주택가격) 과열 리스크가 상대적으로 크고 지속적. 거시건전성/레버리지 관리 병행 필요.
2) 실물 경기 부양 효과는 작고 불확실하므로, 금리 인하만으로 성장 견인이 어려움. 재정/구조정책 보완 필요.
3) 기대 형성의 진단적 특성(오차 지속성) 때문에, 정책 신호 관리와 커뮤니케이션이 중요. 충격 이후 기대가 한 방향으로 고착되지 않도록 모니터링 필요.

## 4. 산출물 경로
- Step 1: [final_final/01_step1_results.md](final_final/01_step1_results.md)
- Step 2: [final_final/02_step2_oos_results.md](final_final/02_step2_oos_results.md)
- Step 3: [final_final/03_step3_lp_results.md](final_final/03_step3_lp_results.md)
- 변수 정의: [final_final/variable_definitions.md](final_final/variable_definitions.md)
- 그래프/표 원본: `final_final/materials/step1`, `final_final/materials/step2`, `final_final/materials/step3`
