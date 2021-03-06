# 데이터 타입
JavaScript에는 총 8개의 데이터 타입이 존재한다. 


## 1. Number
- 정수(integer) 및 부동 소수점(floating point number)를 나타낸다.
- `(2^53-1)`와 `-(2^53-1)` 사이의 숫자만 나타낼 수 있다.
- 일반적인 숫자 외에 `"특수 숫자 값(special numeric values)"`이 있다: `Infinity`, `-Infinity`, `Nan`

### `Infinity`
- 수학적 무한대를 나타내고 그 어떤 숫자보다 큰 특수 값을 가진다.
- 0으로 나눈 결과값으로 `Infinity` 값을 얻을 수 있다:
  ```JavaScript
  alert( 1 / 0 ); // Infinity
  ```
- 또는 값을 직접 사용할 수 있다:
  ```JavaScript
  alert( Infinity ); // Infinity
  ```

  
### `Nan`
- 계산 오류를 나타내는 값이다. 부정확하거나 정의되지 않은 수학 연산의 결과이다:
  ```JavaScript
  alert( "not a number" / 2 ); // NaN, such division is erroneous
  ```
- `NaN`으로 진행한 모든 수학적 연산은 `NaN`을 반환한다. 따라서 연산에 `NaN`이 하나라도 나타난다면 결과는 `NaN`이 된다:
  ```JavaScript
  alert( Nan + 1 ); // NaN
  alert( 3 * NaN ); // NaN
  alert( "not a number" / 2 - 1 ); // NaN
  ```
  - **예외): `NaN ** 0은 1이다`**

  
> **수학적 연산은 안전하다**<br>
> JavaScript에서 수학을 하는 것은 "안전하다". 0으로 나누기, 숫자로 구성되지 않은 문자열을 숫자로 간주하기, 등등. <br>
> 이러한 "틀린" 수학적 오류로 인해서 스크립트는 치명적인 오류("프로그램 실행이 죽는것")와 함께 멈추지 않을 것이다. 최악의 경우 결과로 `NaN`을 반환받게 된다. 


## 2. BigInt
- `(2^53-1)`와 `-(2^53-1)`보다 큰 숫자를 나타내기 위해서 사용된다.
- 숫자 끝에 `n`을 붙여서 `BigInt`를 만들 수 있다. 
  ```JavaScript
  // 끝에 있는 "n"이 해당 숫자가 BigInt 라는 것을 나타낸다
  const BigInt = 1234567890123456789012345678901234567890n;
  ```


## 3. String
- JavaScript의 문자열은 따옴표로 묶어 있어야 한다:
    - 큰 따옴표: `"Hello"`
    - 작은 따옴표: `'Hello'`
    - 백틱: ``Hello``
- 큰 따옴표랑 작은 따옴표는 일반 따옴표이다. 둘의 차이는 없고 단순 취향 차이다. 
- 백틱은 "확장 기능" 따옴표이다. 변수와 식을 ${...}으로 감싸서 문자열에 포함시킬 수 있다:
  ```JavaScript
  let name = "John";
  
  // 변수 포함하기
  alert(`Hello, ${name}!`); // Hello, John!
  
  // 식 포함하기
  alert(`the result is ${1+2}`); // the result is 3
  ```

## References
- [Data Types](https://javascript.info/types)
