---
title: "[Rust] 1. 변수와 가변성"
excerpt: "러스트의 변수에 대한 설명"
categories:
  - Rust
tags:
  - rust
  - variable
  - mutability
---
{{ page.excerpt }}
* * *

## 변수 (Variables)
- 러스트에서 기본 변수는 `불변`(불변성) 입니다.
- 변수가 불변성인 경우, 일단 값이 이름에 bound되면 해당 값을 변경할 수 없습니다.
- 변수는 기본적으로 불변성이지만 우리는 변수명의 접두어로 `mut`을 추가하는 것을 통해 `가변성 변수`를 선언할 수 있습니다.
```rust
fn main() {
  let mut x = 5;
  println!("The value of x is: {}", x);
  x = 6;
  println!("The value of x is: {}", x);
}
```
위의 프로그램을 수행하면 다음과 같은 결과를 얻게 됩니다:
```
The value of x is: 5
The value of x is: 6
```
mut를 사용하여, x에 bind된 값을 5에서 6으로 변경할 수 있습니다.

> `let` 으로 선언한 변수는 값이 `불변` 이다.  
`let mut` 으로 선언한 변수는 값이 `변할 수` 있다.

## 변수와 상수 간의 차이점들
- 상수에 대해서는 mut을 사용하는 것이 허용되지 않습니다.
- 상수를 사용하고자 하면 let키워드 대신 `const`키워드를 사용해야 하고, `값의 유형`(자료형)을 선언해야 합니다.
- 상수는 함수의 반환값처럼, 런타임시 달라질 수 있는 동적인 값은 불가능합니다.

아래의 MAX_POINTS라는 이름을 갖는 상수를 선언하는 예제에서는 값을 100,000으로 설정합니다. (Rust의 상수 명명 규칙에 따라 모든 단어를 대문자로 사용합니다.)
```rust
const MAX_POINTS: u32 = 100_000;
```

> `const` 으로 `상수` 값을 선언할 수 있다.  
단, 선언시 `자료형`도 선언해주어야한다.

## 섀도잉 (Shadowing)
```rust
let a = 1;
let a = 2;
let a = 3;
```
이런식으로 같은 이름의 변수를 여러번 정의하면, 이후 코드에서 a를 참고할때 가장 마지막에 선언된 3을 참조합니다.
> 마지막에 선언한 변수로 앞서 선언된 변수를 가리는 것,  
이를 `섀도잉`이라고 합니다.

```rust
fn main() {
  let a = 1;  // block scope 밖에서는 a의 값이 1
  println!("The value of a is: {}", a);
  {
    let a = 2;  // block scope 안에서는 a의 값이 2로 유지된다.
    println!("The value of a is: {}", a);
  }
  println!("The value of a is: {}", a);
}
```
위의 프로그램을 수행하면 다음과 같은 결과를 얻게 됩니다:
```
The value of a is: 1
The value of a is: 2
The value of a is: 1
```
> 이처럼 지역 변수로 전역 변수를 섀도잉하여,  
똑같은 해당 변수명을 지역변수로 안전하게 사용할수 있도록 해줍니다.

- 섀도잉을 이용하여, **이름이 같은 변수를 다른 자료형으로 활용할수 있습니다.**  
C에서 다음과 같은 코드가 있다고 칩시다.
```c
int a = 1;
float a = 1.0;  // Compile Error
```
같은 스코프내에서는 중복정의가 불가능하다면서, 컴파일러가 에러를 뿜습니다.  
반면, 러스트에서는 문제가 없습니다.
```rust
let a = 1;
let a = 1.0;  // OK
```

## 주의할 점
- 기본적으로 러스트는 `정적 타이핑`을 합니다.
```rust
let mut a = 1;
a = 2;  // OK
a = "hi";  // Compile Error
```
1행에서 정의될때, `정수`가 들어갔기 때문에, `문자열`을 대입하려고하면 에러가 납니다.
```rust
let a = 1;
let a = "hi";  // OK
a = 5;  // Compile Error
```
2행에서 섀도잉을 한 후에는 문자열 변수 a를 참조하게 되므로, 3행에서 정수를 대입하려고 하면 에러가 납니다.

## 참고 자료
<https://rinthel.github.io/rust-lang-book-ko/ch03-01-variables-and-mutability.html>
<https://pubul.tistory.com/87>
