# 🎄 레스토랑 이벤트 플래너

> 고객이 식당에 방문할 날짜와 메뉴를 선택하면 이벤트에 맞는 플랜을 보여주는 서비스

<br/>

## 📍 목차

<!-- no toc -->
1. [프로젝트 개요](#👩🏻‍💻-프로젝트-개요)
2. [프로젝트 목표](#🥇-프로젝트-목표)
3. [신경썼던 점](#👣-신경썼던-점)
4. [전체적인 플로우](#🏄-전체적인-플로우)
5. [구현할 기능](#📝-구현할-기능)
6. [기능별 명세](#🛠️-기능별-명세)
7. [객체별 명세](#🛠️-객체별-명세)
8. [프로그래밍 요구 사항](#✅-프로그래밍-요구-사항)
9. [상황별 에러와 안내](#🥊-상황별-에러와-안내)
10. [리팩토링](#🧹-리팩토링)
11. [컨벤션](#📦-컨벤션)
12. [폴더 구조](#🗂️-폴더-구조)

<br/>

## 👩🏻‍💻 프로젝트 개요

- 진행기간: 2023.11.09 ~ 2023.11.15
- 회고기록: [프로젝트 배움과 회고 기록](https://devella.oopy.io/91b8bf6c-746d-47cd-84a6-6e2f7e0ab102)

<br/>

## 🥇 프로젝트 목표

1. 클래스의 역할과 책임을 생각하여 분리할 수 있다.
2. 클래스 작성 시 도메인 로직에 집중하는 방향으로 구현한다.
3. 도메인 로직에 대한 단위 테스트를 작성할 수 있다.

<br/>

## 👣 신경썼던 점

1. 예외 상황을 빈틈없이 처리하고자 했다.
2. 각 객체의 역할을 명확히 하여 분리하고자 했다.
3. 도메인 로직과 관련된 모든 메서드는 단위 테스트를 작성하고자 했다.
4. 요구 사항에 있는 내용을 놓치지 않고 반영하고자 했다.

<br/>

## 🏄 전체적인 플로우

> [상세 기능 요구사항 바로가기](https://github.com/woowacourse-precourse/javascript-christmas-6)

1. 고객에게 인사와 함께, 식당 예상 방문 날짜를 입력받는다.
2. 고객이 예상 방문 날짜를 입력한다.
3. 고객에게 메뉴와 각 메뉴당 개수를 입력받는다.
4. 고객이 메뉴와 각 메뉴당 개수를 입력한다.
5. 고객에게 이벤트 혜택 미리보기를 보여준다.

<br/>

## 📝 구현할 기능

1. 이벤트 플래너가 시작하는 기능
2. 고객으로부터 식당 예상 방문 날짜를 입력받는 기능
3. 고객이 입력한 예상 방문 날짜가 유효한 값인지 검사하는 기능
4. 고객으로부터 메뉴와 각 메뉴당 개수를 입력받는 기능
5. 고객이 입력한 메뉴와 각 메뉴당 개수가 유효한 값인지 검사하는 기능
6. 고객이 주문한 메뉴와 개수를 출력하는 기능
7. 할인 전 총 주문 금액을 계산해 출력하는 기능
8. 날짜마다 할인 금액이 증가하도록 계산하는 기능
9. 요일에 따라 메뉴당 할인 가격을 계산하는 기능
10. 이벤트 달력에 따라 총주문 금액 할인 가격을 계산하는 기능
11. 총 주문 금액에 따라 증정 이벤트를 하는 기능
12. 이벤트 기간에 따라 다른 프로모션을 적용하는 기능
13. 혜택 내역을 출력하는 기능
14. 총혜택 금액을 계산해 출력하는 기능
15. 할인 후 예상 결제 금액을 계산해 출력하는 기능
16. 총혜택 금액에 따라 다른 이벤트 배지를 부여하는 기능
17. 형식에 맞추어 이벤트 혜택 미리보기를 출력하는 기능
18. 예외 발생 시, 메시지 출력과 함께 해당 부분부터 다시 입력받는 기능

<br/>

## 🛠️ 기능별 명세

### 1. 이벤트 플래너 시작

- [x] `App.js`의 `run()`로 이벤트 플래너가 시작된다.

### 2. 예상 방문 날짜를 입력받는 기능

- [x] 이벤트 플래너 시작과 동시에 식당 예상 방문 날짜 입력을 유도하는 메시지가 출력된다.

### 3. 예상 방문 날짜 유효성 검사 기능

- [x] 방문 날짜는 양의 정수만 입력 가능하다. (음수, 소수, 공백, 특수문자, 문자열, 0으로 시작하는 숫자 불가)
- [x] 방문 날짜는 1 이상 31 이하의 범위로만 입력 가능하다.
- [x] 위의 조건을 하나라도 만족하지 않으면 에러 메시지가 출력되고, 다시 입력받는다.

### 4. 메뉴와 각 메뉴당 개수를 입력받는 기능

- [x] 고객이 방문 날짜를 입력하면 메뉴와 메뉴의 개수를 묻는 메시지가 출력된다.

### 5. 메뉴와 메뉴당 개수 유효성 검사 기능

- [x] 메뉴 이름 뒤에 공백 없이 하이픈과 함께 개수를 입력해야 한다.
- [x] 각 메뉴 간에는 공백 없이 쉼표로만 구분된다.
- [x] 메뉴의 개수는 1 이상의 양의 정수만 입력 가능하다. (음수, 소수, 공백, 특수문자, 문자열, 0으로 시작하는 숫자 불가)
- [x] 메뉴는 중복 없이 입력해야 한다. (메뉴 이름은 같지만 개수가 다른 경우도 포함)
- [x] 메뉴판에 있는 메뉴만 입력해야 한다.
- [x] 메뉴판에 없는 메뉴를 주문하면 메뉴판 안내 메시지가 출력된다.
- [x] 위의 조건을 하나라도 만족하지 않으면 에러 메시지가 출력되고, 다시 입력받는다.
- [x] 메뉴 개수가 20개를 초과할 경우 에러 메시지가 출력되고, 다시 입력받는다.
- [x] 음료만 주문할 경우 에러 메시지가 출력되고, 다시 입력받는다.

### 6. 주문 메뉴를 출력하는 기능

- [x] 각 메뉴와 개수는 `메뉴 N개\n` 형식으로 변환되어 출력된다.

### 7. 할인 전 총 주문 금액을 계산해 출력하는 기능

- [x] 총주문 금액 10,000원 이상부터 모든 이벤트가 적용되도록 한다.
- [x] 총주문 금액 10,000원 미만인 경우 `총주문 금액 10,000원 이상부터 이벤트가 적용됩니다.`가 출력된다.
- [x] 총주문 금액은 `메뉴 개수 * 메뉴당 가격`으로 계산한다.
- [x] 아래와 같이 메뉴당 가격을 반영한다.

```shell
<애피타이저>
양송이수프(6,000), 타파스(5,500), 시저샐러드(8,000)

<메인>
티본스테이크(55,000), 바비큐립(54,000), 해산물파스타(35,000), 크리스마스파스타(25,000)

<디저트>
초코케이크(15,000), 아이스크림(5,000)

<음료>
제로콜라(3,000), 레드와인(60,000), 샴페인(25,000)
```

### 8. 날짜마다 할인 금액이 증가하는 계산 기능

- [x] `2023.12.1 ~ 2023.12.25`은 크리스마스 디데이 할인을 적용한다.
  - [x] 1,000원으로 시작하여 크리스마스가 다가올수록 날마다 할인 금액이 100원씩 증가하도록 한다.
  - [x] 12월 1일에 1,000원, 2일에 1,100원, ..., 25일엔 3,400원 할인된다.
  - [x] 총 주문 금액에서 해당 금액만큼 할인이 적용되도록 한다.
- [x] 다만, `2023.12.26 ~ 2023.12.31`은 크리스마스 디데이 할인이 적용되지 않는다.

### 9. 요일에 따라 메뉴당 할인 가격 계산 기능

- [x] **평일**은 월요일-금요일이 아닌, **일요일-목요일**로 지정한다.
- [x] 평일에는 디저트 메뉴를 메뉴 1개당 2,023원 할인되도록 한다.
- [x] **주말**은 토요일/일요일이 아닌, **금요일/토요일**로 지정한다.
- [x] 주말에는 메인 메뉴를 메뉴 1개당 2,023원 할인되도록 한다.

### 10. 이벤트 달력에 따른 총주문 금액 특별 할인 가격 계산 기능

- [x] 이벤트 달력에 별이 있는 날에는 총주문 금액에서 1,000원 특별 할인되도록 한다.
- [x] 특별 할인 날짜는 `12/3(일), 12/10(일), 12/17(일), 12/24(일), 12/25(월), 12/31(일)`이다.

### 11. 총 주문 금액에 따른 증정 이벤트 기능

- [x] 할인 전 총주문 금액이 12만 원 이상일 때, 샴페인 1개가 증정되도록 한다.
- [x] 증정 이벤트에 해당하지 않는 경우, 증정 메뉴 `없음`으로 보여 준다.

### 12. 이벤트 기간에 따라 프로모션을 적용하는 기능

- [x] '크리스마스 디데이 할인'을 제외한 다른 이벤트는 2023.12.1 ~ 2023.12.31 동안 적용되도록 한다.

### 13. 혜택 내역을 출력하는 기능

- [x] 해당 고객에게 적용된 이벤트 내역만 보여준다.
- [x] 적용된 이벤트가 하나도 없다면 혜택 내역 `없음`으로 보여 준다.
- [x] 혜택 내역에 여러 개의 이벤트가 적용된 경우는 아래와 같이 출력된다.

```shell
<혜택 내역>
크리스마스 디데이 할인: -1,200원
평일 할인: -4,046원
특별 할인: -1,000원
증정 이벤트: -25,000원
```

### 14. 총혜택 금액을 계산해 출력하는 기능

- [x] `총혜택 금액 = 할인 금액의 합계 + 증정 메뉴의 가격`으로 계산된다.

### 15. 할인 후 예상 결제 금액을 계산해 출력하는 기능

- [x] `할인 후 예상 결제 금액 = 할인 전 총주문 금액 - 할인 금액`으로 계산된다.
- [x] 이때, 증정 메뉴의 가격은 할인 후 예상 결제 금액에 포함하지 않는다.

### 16. 총 혜택 금액에 따라 이벤트 배지를 부여하는 기능

- [x] 총 혜택 금액에 따라 다른 이벤트 배지를 부여되도록 한다.
- [x] 5천 원 이상: 별 배지를 부여한다.
- [x] 1만 원 이상: 트리 배지를 부여한다.
- [x] 2만 원 이상: 산타 배지를 부여한다.
- [x] 이벤트 배지가 부여되지 않는 경우, `없음`으로 보여 준다.
- [x] 적용된 이벤트가 하나도 없는 경우는 아래 예시와 같이 출력된다.

```shell
안녕하세요! 식당 12월 이벤트 플래너입니다.
12월 중 식당 예상 방문 날짜는 언제인가요? (숫자만 입력해 주세요!)
26 
주문하실 메뉴를 메뉴와 개수를 알려 주세요. (e.g. 해산물파스타-2,레드와인-1,초코케이크-1)
타파스-1,제로콜라-1 
12월 26일에 식당에서 받을 이벤트 혜택 미리 보기!
 
<주문 메뉴>
타파스 1개
제로콜라 1개

<할인 전 총주문 금액>
8,500원
 
<증정 메뉴>
없음
 
<혜택 내역>
없음
 
<총혜택 금액>
0원
 
<할인 후 예상 결제 금액>
8,500원
 
<12월 이벤트 배지>
없음
```

### 17. 이벤트 플래너 미리보기 기능

- [x] 고객이 메뉴와 메뉴의 개수를 입력하면 이벤트 플래너가 출력된다.
- [x] 아래와 같은 형식으로 이벤트 플래너가 출력된다.

```shell
안녕하세요! 식당 12월 이벤트 플래너입니다.
12월 중 식당 예상 방문 날짜는 언제인가요? (숫자만 입력해 주세요!)
26 
주문하실 메뉴를 메뉴와 개수를 알려 주세요. (e.g. 해산물파스타-2,레드와인-1,초코케이크-1)
타파스-1,제로콜라-1 
12월 26일에 식당에서 받을 이벤트 혜택 미리 보기!
 
<주문 메뉴>
타파스 1개
제로콜라 1개

<할인 전 총주문 금액>
8,500원
 
<증정 메뉴>
없음
 
<혜택 내역>
없음
 
<총혜택 금액>
0원
 
<할인 후 예상 결제 금액>
8,500원
 
<12월 이벤트 배지>
없음
```

### 18. 예외 및 종료

- [x] 예외 발생 시, `[ERROR]`로 시작하는 에러 메시지를 출력한다.
- [x] 에러 메시지 출력과 함께 해당 부분부터 입력을 다시 받는다.
- [x] 주문이 정상 처리 되면, 이벤트 혜택 내역과 동시에 이벤트 플래너가 종료된다.

<br/>

## 🛠️ 객체별 명세

> MVC 패턴 + Layered Architecture 적용

### Model

- 도메인 모델을 구현
- 도메인의 핵심 로직을 구현

### View

- 사용자의 입력과 출력을 담당
- 입력 및 출력한 값이 유효한지 검증

### Controller

- 입력 및 출력과 같은 사용자 인터페이스 로직을 담당
- 사용자 요청을 응용 영역이 필요로 하는 형식으로 변환해 응용 영역에 전달
- 응용 영역의 응답을 출력 형식에 맞게 변환하여 반환

### Service

- 비즈니스 로직을 담당
- 도메인 모델을 이용해 사용자에게 제공할 기능을 구현
- 실제 도메인 로직 구현은 도메인 모델에 위임

### common

- `constants` 출력 문자열과 관련 숫자들을 상수화
- `utils` 비즈니스 로직 외의 역할을 담당하는 함수
- `validator` 유효성을 검사하는 메서드

<br/>

## ✅ 프로그래밍 요구 사항

- [x] 순수 Vanilla JS로만 구현했는가?
- [x] [Airbnb 자바스크립트 스타일 가이드](https://github.com/airbnb/javascript)를 지키면서 프로그래밍 했는가?
- [x] 프로그램 종료 시 `process.exit()`를 호출하지 않도록 했나?
- [x] 프로그램 구현이 완료되면 `ApplicationTest`의 모든 테스트가 성공하나?
- [x] indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 2까지만 허용했는가?
- [x] 함수(또는 메서드)가 한 가지 일만 하도록 최대한 작게 만들었는가?
- [x] Jest를 이용하여 정리한 기능 목록이 정상 동작함을 테스트 코드로 확인했는가?
- [x] 함수(또는 메서드)의 길이가 15라인을 넘어가지 않도록 구현했는가?
- [x] else를 최대한 지양하였는가?
- [x] 도메인 로직에 단위 테스트를 구현했는가?
- [x] 핵심 로직을 구현하는 코드와 UI를 담당하는 로직을 구분했는가?
- [x] 사용자가 잘못된 값을 입력할 경우 `throw`문을 사용해 예외를 발생시키고, "[ERROR]"로 시작하는 에러 메시지를 출력하고 해당 부분부터 입력을 다시 받게 했는가?

<br/>

## 🥊 상황별 에러와 안내

### 예상 방문 날짜

- [x] 입력하지 않는 경우 → `[ERROR] 유효하지 않은 날짜입니다. 다시 입력해 주세요.`
- [x] 음수, 소수, 공백, 특수문자, 문자열, 0으로 시작하는 숫자로 입력할 경우 → `[ERROR] 유효하지 않은 날짜입니다. 다시 입력해 주세요.`
- [x] 1 이상 31 이하의 범위로 입력하지 않는 경우 → `[ERROR] 유효하지 않은 날짜입니다. 다시 입력해 주세요.`

### 메뉴와 메뉴당 개수

- [x] 입력하지 않는 경우 → `[ERROR] 유효하지 않은 주문입니다. 다시 입력해 주세요.`
- [x] 개수를 음수, 소수, 공백, 특수문자, 문자열, 0으로 시작하는 숫자로 입력할 경우 → `[ERROR] 유효하지 않은 주문입니다. 다시 입력해 주세요.`
- [x] 메뉴를 중복으로 입력한 경우 → `[ERROR] 유효하지 않은 주문입니다. 다시 입력해 주세요.`
- [x] 메뉴판에 없는 메뉴를 입력한 경우 → `[ERROR] 유효하지 않은 주문입니다. 다시 입력해 주세요.`
- [x] 메뉴 개수가 20개를 초과한 경우 → `[ERROR] 메뉴는 한 번에 최대 20개까지만 주문할 수 있습니다. 다시 입력해 주세요.`
- [x] 음료만 주문한 경우 → `[ERROR] 음료만 주문 시, 주문할 수 없습니다. 다시 입력해 주세요.`

### 총 주문 금액

- [x] 총주문 금액이 10,000원 미만인 경우 → `총주문 금액 10,000원 이상부터 이벤트가 적용됩니다.`

<br/>

## 🧹 리팩토링

- [x] 모든 출력 메시지와 값을 상수 처리했는가?
- [x] 에러 메시지를 상황에 따라 내용을 세분화 했는가?
- [x] 함수는 하나의 일만 하도록 여러 메서드로 세분화 했는가?
- [x] 불필요한 주석은 없는가?
- [x] 세미콜론, 괄호 간격, 공백 등 컨벤션이 일관적인가?

<br/>

## 📦 컨벤션

### 폴더 및 파일

#### **tests**

- Unit Test와 Application Test로 분리
- 폴더명은 `camelCase`, 파일명은 `PascalCase`로 작성

#### src

- MVC 패턴에 따라 model, service, controller, view로 분리
- 비즈니스 로직 외의 함수는 utils, 상수는 constants로 분리
- 파일명은 함수는 `camelCase`, 클래스는 `PascalCase`로 작성

### 함수 및 상수

- 함수명은 동사로 시작, 하나의 함수는 한 가지 일만 담당
- 함수(또는 메서드)의 길이가 15라인을 넘지 않도록 구현
- 코드 내 변수명과 클래스명은 영문만 사용
- 상수는 `snake_case`로 작성

### 커밋 메시지

- feat: 새로운 기능을 추가한 경우
- fix: 트러블 슈팅, 로직 변경, 오타 등으로 인해 코드를 수정한 경우
- docs: README.md 등 문서를 수정한 경우
- style: 코드 스타일, 포맷, 주석 등의 변경
- refactor: 코드를 리팩토링한 경우
- test: 테스트 코드를 추가한 경우
- chore: 코드 수정이 아닌, 단순 폴더명 파일명 등을 수정한 경우

<br/>

## 🗂️ 폴더 구조

```shell
🎄 christmas-promotion
📦__tests__
 ┣ 📂unit
 ┃ ┣ 📜BadgeTest.js
 ┃ ┣ 📜DiscountTest.js
 ┃ ┣ 📜EventDateTest.js
 ┃ ┣ 📜EventProcessorTest.js
 ┃ ┣ 📜MenuTest.js
 ┃ ┗ 📜OrderTest.js
 ┗ 📜ApplicationTest.js
📦src
 ┣ 📂common
 ┃ ┣ 📜constants.js
 ┃ ┣ 📜utils.js
 ┃ ┗ 📜validator.js
 ┣ 📂controller
 ┃ ┗ 📜EventPlanner.js
 ┣ 📂model
 ┃ ┣ 📜Badge.js
 ┃ ┣ 📜Discount.js
 ┃ ┣ 📜EventDate.js
 ┃ ┣ 📜Menu.js
 ┃ ┗ 📜Order.js
 ┣ 📂service
 ┃ ┗ 📜EventProcessor.js
 ┣ 📂view
 ┃ ┣ 📜InputView.js
 ┃ ┗ 📜OutputView.js
 ┣ 📜App.js
 ┗ 📜index.js
📜.eslintrc.cjs
📜.gitignore
📜.npmrc
📜.prettierrc.js
📜README.md
📜image.png
```
