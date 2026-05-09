---
title: "DBR 시스템 (Drum-Buffer-Rope)"
created: 2026-05-03
domain: "컨설팅 및 전략"
doc_type: "evergreen-note"
tags: [operations, theory-of-constraints, production-planning, evergreen]
evergreen: true
zettel_status: evergreen
atomic: true
---

# DBR 시스템 (Drum-Buffer-Rope)

## 핵심 정의
DBR 시스템은 제약 이론을 생산 일정과 재고 통제에 적용한 운영 방식이다. Drum은 병목이 정하는 생산 리듬, Buffer는 병목을 보호하는 시간이나 재고 완충, Rope는 병목 속도에 맞춰 앞 공정의 투입을 묶는 통제 장치다.

핵심은 전체 시스템의 속도가 병목에 의해 결정되므로, 병목을 기준으로 전체 흐름을 조정해야 한다는 점이다.

## 작동 방식
먼저 시스템의 제약, 즉 Drum이 되는 병목 공정을 찾는다. 전체 생산 일정은 이 병목이 처리할 수 있는 속도에 맞춰 정해진다.

Buffer는 병목이 멈추지 않도록 보호한다. 앞 공정의 변동이나 지연이 병목에 바로 영향을 주지 않도록 일정한 완충을 둔다. Rope는 병목 속도보다 더 빠르게 자재가 투입되어 재고가 쌓이는 것을 막는다.

## 실무적 의미
DBR은 생산 계획의 초점을 부서별 효율에서 전체 처리량으로 옮긴다. 비병목 공정이 더 빨리 일하는 것은 전체 성과를 높이지 못하고 재고만 늘릴 수 있다.

따라서 DBR은 처리량을 높이면서 불필요한 재고와 일정 혼란을 줄이는 데 유용하다.

## 주의할 점
DBR을 단순한 일정 관리 기법으로만 보면 효과가 약하다. 병목을 잘못 찾거나 Buffer를 정적으로만 설정하면 시스템은 다시 과잉 생산과 결품 사이를 흔들린다.

병목은 수요, 설비, 인력, 제품 믹스 변화에 따라 이동할 수 있으므로 주기적으로 재검토해야 한다.

## 연결된 생각
- [[제약 이론의 5단계 (Five Focusing Steps)]] | DBR은 제약 중심 개선을 운영 시스템으로 구현한다.
- [[종속적 사건과 통계적 변동 (Dependent Events & Statistical Fluctuations)]] | Buffer가 필요한 이유를 설명한다.
- [[운영 지표 (Throughput, Inventory, Operating Expense)]] | DBR의 성과를 처리량, 재고, 운영비로 판단한다.
- [[제약 이론 (TOC)]] | DBR이 속한 상위 운영관리 이론이다.
