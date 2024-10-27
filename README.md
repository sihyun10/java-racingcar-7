# 자동차 경주🚗🚕

### 기능 요구사항

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하여 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
- 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생시킨 후 애플리케이션은 종료되어야 한다.

### 기능 목록

#### 사용자에게 각 자동차의 이름을 입력받는 기능

- [x] 사용자에게 자동차 이름을 부여받는다.
- [ ] 이름은 5자 이하만 가능하다.
    - [ ] 5자 초과되면 **예외처리**한다.
- [ ] `,`를 기준으로 구분하며 입력받아야한다.
    - [ ] `,`를 기준으로 구분하여 입력하지않으면 **예외처리**한다.

#### 사용자에게 몇번 이동할지 입력받는 기능

- [x] 몇 번 이동할지 입력 받는다. (`int`)
    - [ ] **[조건]** 0번 이상은 이동해야한다.
    - [ ] [예외처리] **음수**는 입력할 수 없다.
    - [ ] [예외처리] 숫자 외의 값은 입력할 수 없다.
- [ ] 입력 받은 값을 통해 전진하는 기능을 실행한다.

#### 자동차 기능 (`Car`클래스)

각각의 자동차마다 자동차 이름과 현재 위치값을 알아야 경주 게임 진행가능

- [x] 자동차 이름, 현재 위치값 변수
- [x] 전진이면 현재 위치값 `+1` 증가
- [x] 무작위 값이 4 이상이면 전진한다.

#### 자동차 경주 게임 기능 (`RacingGame` 클래스)

- [x] 자동차 이름 배열 리스트, 시도 횟수를 통해 게임 진행
- [x] 자동차 이동시키기
    - [x] 0 ~ 9 사이에서 무작위 값을 구한 뒤, `Car.move(int randomValue)` `randomValue`값에 넣어주기
- [x] 최종 우승자(들) 선별하기
    - [x] 가장 많이 이동한 위치(`maxPosition`)를 구한다.
    - [x] 그 위치에 해당하는 자동차(들)은 우승자(들)이다.

#### 결과 알려주는 기능

누가 우승했는지 출력한다.

- [ ] 각 자동차의 최종 직진한 횟수에서 최댓값을 구한다.
- [ ] 최댓값을 가진 자동차를 모두 출력한다.
- [ ] 공동 우승자이면 모두 출력해주며, 쉼표(`,`)를 이용하여 구분해준다.

---------------------------

### 입출력 요구 사항

#### 입력

- 경주할 자동차 이름(이름은 쉼표(,) 기준으로 구분)

```dtd
pobi,woni,jun
```

- 시도할 횟수

```dtd
5
```

#### 출력

- 차수별 실행 결과

```dtd
pobi : --
        woni : ----
        jun : ---
```

- 단독 우승자 안내 문구

```dtd
최종 우승자 : pobi
```

- 공동 우승자 안내 문구

```dtd
최종 우승자 : pobi, jun
```

#### 실행 결과 예시

```dtd
경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
        pobi,woni,jun
        시도할 횟수는 몇 회인가요?
        5

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

        최종 우승자 : pobi, jun
```