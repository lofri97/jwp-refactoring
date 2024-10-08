# 키친포스

## 요구 사항
### Product
- [ ] Product 를 생성한다
  - [ ] 가격이 null 일 경우 거부한다
  - [ ] 가격이 음수일 경우 거부한다.
- [ ] Product 전체 목록을 조회한다.

### Menu Group
- [ ] Menu Group 을 생성한다.
- [ ] Menu Group 전체 목록을 조회한다.

### Menu
- [ ] Menu 를 생성한다.
  - [ ] 가격이 null 일 경우 거부한다.
  - [ ] 가격이 음수일 경우 거부한다.
  - [ ] Menu 가 Menu Group 에 포함되지 않을 경우 거부한다.
  - [ ] Menu 에 존재하지 않는 Product 가 있을 경우 거부한다.
  - [ ] Menu 의 가격이 포함 Product 들의 가치 합보다 클 경우 거부한다.
- [ ] 전체 Menu 전체 목록을 조회한다.

### Order
- [ ] Order 를 생성한다.
  - [ ] Order 의 LineItems 가 비어있을 경우 거부한다.
  - [ ] Order 한 Menu 가 하나라도 존재하지 않을 시 거부한다.
  - [ ] Order 의 Id 는 서비스 재량으로 둔다.
  - [ ] Order Table 이 존재하지 않으면 거부한다.
  - [ ] Order Table 이 비어있으면 거부한다.
- [ ] Order 전체 목록을 조회한다.
- [ ] Order 상태를 변경한다.
  - [ ] Order id 에 해당하는 Order 가 없을 경우 거부한다.
  - [ ] Order 의 상태가 COMPLETION 일 경우 거부한다.

### Table
- [ ] Table 을 생성한다.
  - [ ] 생성 Table 의 Id 는 서비스의 재량으로 둔다.
  - [ ] 생성 Table 의 Table Group 은 지정되지 않는다.
- [ ] Table 전체 목록을 조회한다.
- [ ] Table 을 빈 상태로 변경한다.
  - [ ] 요청 Table 의 id 에 매칭되는 Table 이 존재하지 않을 경우 거부한다.
  - [ ] 요청 Table 의 Table Group id 가 존재할 경우 거부한다.
  - [ ] 요청 Table 의 상태가 COOKING 이거나 MEAL 일 경우 거부한다.
- [ ] Table 의 Guest 인원을 변경한다
  - [ ] 변경 인원이 0명 미만일 경우 거부한다.
  - [ ] 대상 Table 이 존재하지 않을 경우 거부한다.
  - [ ] 대상 Table 이 Empty 상태일 경우 거부한다.

### Table Group
- [ ] Table Group 을 생성한다.
  - [ ] 요청 Order Table 이 2개 미만일 경우 거부한다.
  - [ ] 요청 Order Table 들중 하나라도 존재하지 않을 경우 거부한다.
  - [ ] 요청 Order Table 이 빈 상태이거나 이미 TableGroup 에 속해있는 경우 거부한다.

## 용어 사전

| 한글명 | 영문명 | 설명 |
| --- | --- | --- |
| 상품 | product | 메뉴를 관리하는 기준이 되는 데이터 |
| 메뉴 그룹 | menu group | 메뉴 묶음, 분류 |
| 메뉴 | menu | 메뉴 그룹에 속하는 실제 주문 가능 단위 |
| 메뉴 상품 | menu product | 메뉴에 속하는 수량이 있는 상품 |
| 금액 | amount | 가격 * 수량 |
| 주문 테이블 | order table | 매장에서 주문이 발생하는 영역 |
| 빈 테이블 | empty table | 주문을 등록할 수 없는 주문 테이블 |
| 주문 | order | 매장에서 발생하는 주문 |
| 주문 상태 | order status | 주문은 조리 ➜ 식사 ➜ 계산 완료 순서로 진행된다. |
| 방문한 손님 수 | number of guests | 필수 사항은 아니며 주문은 0명으로 등록할 수 있다. |
| 단체 지정 | table group | 통합 계산을 위해 개별 주문 테이블을 그룹화하는 기능 |
| 주문 항목 | order line item | 주문에 속하는 수량이 있는 메뉴 |
| 매장 식사 | eat in | 포장하지 않고 매장에서 식사하는 것 |
