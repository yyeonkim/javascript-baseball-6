## 구현할 기능

1. boolean 낫싱 = false, number 스트라이크 = 0, number 볼 = 0 변수를 생성한다.
2. 컴퓨터가 1에서 9까지 서로 다른 임의의 수 3개를 선택한다. (**라이브러리**)
3. '숫자 야구 게임을 시작합니다.'을 출력한다. (**라이브러리**)
4. 게임 플레이어의 입력을 받는다. (**라이브러리**)
   ```
   숫자를 입력해주세요 : 123
   ```
5. 컴퓨터와 게임 플레이어의 숫자를 비교한다.
   - 게임 플레이어가 입력한 숫자를 차례대로 컴퓨터의 숫자 3개와 비교한다.
   - 같은 자리에 같은 숫자가 있으면, 스트라이크 + 1
   - 다른 자리에 같은 숫자가 있으면, 볼 + 1
   - 숫자를 모두 비교했는데도 스트라이크와 볼이 0이면, 낫싱 true
6. 결과를 문자로 출력한다. (**라이브러리**)
   - 낫싱이 true면, '낫싱' 출력
   - 낫싱이 false고, 스트라이크와 볼이 0보다 크면 출력
     ```
     m볼 m스트라이크
     ```
7. 스트라이크 != 3이면, 변수를 초기화하고, 4번부터 반복한다.
8. 스트라이크 == 3이면, 변수를 초기화하고, 다음을 출력한다. (**라이브러리**)
   ```
   3개의 숫자를 모두 맞히셨습니다! 게임 종료
   ```
9. 게임 플레이어에게 게임 재시작 여부를 묻는다. (**라이브러리**)
   ```
   게임을 새로 시작하려면 1, 종료하려면 2를 입력하세요.
   1
   ```
   - 새로 시작(1)을 선택하면 2부터 반복한다.
   - 종료(2)를 선택하면, 종료한다. (**요구사항 1** 참고)

## 요구 사항

1. 프로그램 종료 시 process.exit()를 호출하지 않는다.
2. 프로그램 구현이 완료되면 ApplicationTest의 모든 테스트가 성공해야 한다. 테스트가 실패할 경우 0점 처리한다.

### 라이브러리

- @woowacourse/mission-utils의 Random 및 Console API를 사용하여 구현해야 한다.
  - Random 값 추출은 Random.pickNumberInRange()를 활용한다.
  - 사용자의 값을 입력 받고 출력하기 위해서는 Console.readLineAsync, Console.print를 활용한다.

#### 사용 예시

```javascript
const computer = [];
while (computer.length < 3) {
  const number = MissionUtils.Random.pickNumberInRange(1, 9);
  if (!computer.includes(number)) {
    computer.push(number);
  }
}
```