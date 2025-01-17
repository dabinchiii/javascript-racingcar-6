# 🔗 원본 레포

https://github.com/woowacourse-precourse/javascript-racingcar-6

# 🎯 프로그래밍 요구 사항

- 프로그램 실행의 시작점은 App.js의 play 메서드이다. 아래와 같이 프로그램을 실행시킬 수 있어야 한다.

```js
const app = new App();
app.play();
```

- 순수 Vanilla JS로만 구현한다.
- 프로그램 종료 시 process.exit()를 호출하지 않는다.
- 프로그램 구현이 완료되면 ApplicationTest의 모든 테스트가 성공해야 한다.
- JavaScript 코드 컨벤션을 지키면서 프로그래밍 한다.

  - 아래의 네이밍 컨벤션 이외에는 [Airbnb 자바스크립트 스타일 가이드](https://github.com/airbnb/javascript)를 기준으로 한다.

  ```
  1. 소스의 변수명, 클래스명 등에는 영문 이외의 언어를 사용하지 않습니다.
  2. 클래스, 메서드 등의 이름에는 특수 문자를 사용하지 않습니다.
  3. 상수명은 SNAKE_CASE로 작성합니다.
  ```

- indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
- Jest를 이용하여 본인이 정리한 기능 목록이 정상 동작함을 테스트 코드로 확인한다.
- Random 값 추출은 Random.pickNumberInRange()를 활용한다.
- 사용자의 값을 입력 받고 출력하기 위해서는 Console.readLineAsync, Console.print를 활용한다.

# 🚀 구현할 기능 목록

- [x] 자동차의 이름을 입력을 위한 안내 메시지를 출력한다.
  ```
  경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
  ```
- [x] 사용자에게 자동차 이름 목록을 입력받는다.

  - 자동차 이름은 쉼표를 기준으로 구분된다.
  - 자동차 이름은 5자 이하이다.
  - 자동차 이름은 공백일 수 없다.
  - 경주에 참여하는 자동차는 1대 이상이다.
  - 자동차 이름은 중복될 수 없다.
  - 자동차 이름의 앞 뒤에 붙은 공백은 제거한다.

  ```
  경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
  pobi,woni,jun
  ```

- [x] 사용자에게 시도할 횟수를 입력받는 안내 메시지를 출력한다.

  ```
  시도할 횟수는 몇 회인가요?
  ```

- [x] 사용자에게 시도할 횟수(몇 번 이동할지) m을 입력받는다.

  - m은 1 이상의 정수이다.

  ```
  시도할 횟수는 몇 회인가요?
  5
  ```

- [x] 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- [x] 한 번의 시도에서 각 자동차 별로 전진 또는 멈춤을 한다.
  - 전진 조건 : 0~9의 무작위 값 구한후, 그 값이 4 이상일 경우 전진한다.
- [x] 각 시도 별로 실행 결과를 출력한다.

  - 첫 시도 전에 실행 결과를 알리는 메시지를 출력한다.

  ```
  실행 결과
  ```

  - 자동차 하나의 시도 결과는 `{자동차 이름} : {위치 표시}`의 형태이다.
  - 각 시도 별 실행 결과는 개행으로 구분한다.

  ```
  실행 결과
  pobi : -
  woni :
  jun : -

  pobi : --
  woni : -
  jun : --

  pobi : ---
  woni : --
  jun : ---

  pobi : ----
  woni : ---
  jun : ----

  pobi : -----
  woni : ----
  jun : -----
  ```

- [x] m 번의 시도가 끝나면 게임이 완료되고, 우승한 자동차의 이름을 출력한다.
  - 우승자는 한 명 이상일 수 있다.
  - 우승자가 2명 이상일 경우 쉼표를 이용하여 구분한다.
    - 단독 우승자일 경우 (우승자가 1명)
    ```
    최종 우승자 : pobi
    ```
    - 공동 우승자일 경우 (우승자가 2명 이상)
    ```
    최종 우승자 : pobi, jun
    ```
- [x] 사용자의 입력이 잘못된 형식일 경우, throw문으로 예외를 발생시키고 애플리케이션을 종료한다.
- [x] 에러 메시지는 `[ERROR]`로 시작한다.

  ```
  [ERROR] 숫자가 잘못된 형식입니다.
  ```

# ✏️ 구현할 테스트 코드 목록

- [x] 실행 결과 출력 함수 테스트
  - 전체 실행 결과
  - 한 번의 라운드의 대한 결과(state)
- [x] 우승자 출력 함수 테스트
  - 단독 우승자일 경우
  - 공동 우승자일 경우

# ✏️ 과제 진행 요구 사항

- Git의 커밋 단위는 앞 단계에서 docs/README.md에 정리한 기능 목록 단위로 추가한다.
- [커밋 메시지 컨벤션 가이드](https://gist.github.com/stephenparish/9941e89d80e2bc58a153)를 참고해 커밋 메시지를 작성한다.
- 과제 진행 및 제출 방법은 [프리코스 과제 제출 문서](https://github.com/woowacourse/woowacourse-docs/tree/main/precourse)를 참고한다.
