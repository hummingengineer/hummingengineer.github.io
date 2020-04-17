---
title: "[Rust] 0. 시작하기, 출력"
excerpt: "러스트에 대한 설명과 Hello World 출력하기"
categories:
  - Rust
tags:
  - rust
  - introduction
last_modified_at: 2020-04-12T23:48:12+09:00
---
{{ page.excerpt }}
* * *

## 러스트란? (What is Rust?)
- 러스트는 현대적인 시스템 프로그래밍 언어로 안전성, 속도, 그리고 동시성에 주안점을 두고 있습니다.
- 또한, 러스트는 가비지 콜렉션을 사용하지 않고 메모리 안전을 달성했습니다.

## Hello World! 출력하기
```rust
fn main() {
  // Print text to the console
  println!("Hello World!");
}
```
### @main
- `main` 함수는 모든 실행 가능한 러스트 프로그램 내에서 첫번째로 실행되는 코드입니다.
- C언어와 비슷한 구조를 가지고 있다.

### @println!
- `println!` 는 러스트 *매크로(macro)* 라고 불립니다.  만일 대신에 함수라고 불리려면, (`!` 없이) println으로 입력되었어야 할 것입니다.  지금은 !이 보통의 함수 대신 매크로를 호출하고 있음을 의미한다는 것만 알아두면 됩니다.
- `println!` 매크로는 스크린에 텍스트를 출력합니다.
- 문자열(string)을 `println!`의 인자로 넘기고, 이 스트링이 화면에 출력됩니다.
- 라인은 세미콜론 `;`으로 끝냅니다.  이는 이 표현식이 끝났고 다음 것이 시작될 준비가 되었음을 나타냅니다.

## 참고 자료
<https://pubul.tistory.com/86?category=809823>
<https://doc.rust-lang.org/stable/rust-by-example/hello.html>
<https://rinthel.github.io/rust-lang-book-ko/ch01-02-hello-world.html>
