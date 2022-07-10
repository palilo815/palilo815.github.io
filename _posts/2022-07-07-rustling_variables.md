---
title: rustling - variables
date: 2022-07-07 23:00:00 +0900
categories: [rust, rustling]
tags: [rust]     # TAG names should always be lowercase
---

# variables 1

```bash
⚠️  Compilation of exercises/variables/variables1.rs failed!, Compiler error message:

error[E0425]: cannot find value `x` in this scope
 --> exercises/variables/variables1.rs:8:5
  |
8 |     x = 5;
  |     ^ not found in this scope

error[E0425]: cannot find value `x` in this scope
 --> exercises/variables/variables1.rs:9:36
  |
9 |     println!("x has the value {}", x);
  |                                    ^ not found in this scope

error: aborting due to 2 previous errors
```

두 에러 모두 `cannot find value 'x'`라고 한다. `x`란 변수를 만들지도 않고 대입과 출력을 하고 있다. 처음에 `x`를 선언함과 동시에 5로 초기화하면 된다.

<br>

**Solution**

```rust
fn main() {
    let x = 5;
    println!("x has the value {}", x);
}
```

---

# variables 2

```bash
⚠️  Compilation of exercises/variables/variables2.rs failed!, Compiler error message:

error[E0282]: type annotations needed
 --> exercises/variables/variables2.rs:7:9
  |
7 |     let x;
  |         ^ consider giving `x` a type

error: aborting due to previous error
```

`x`의 타입이 필요하다고 말한다. 아랫줄에서 `x`와 10을 비교하고 있으므로 `x`의 타입은 `i32`일 것이다. `let x: i32`처럼 타입을 알려주자.

cpp에선`int x; std::cout << x;`처럼 변수 초기화를 하지 않아도 사용할 수 있지만 (물론 컴파일러가 경고할 것이다), rust에선 변수를 사용하려면 초기화를 반드시 해야 한다. 그리고 초기값을 주면 컴파일러는 `x`의 타입을 추론할 수 있으므로 굳이 타입을 적지 않아도 된다.

<br>

**Solution**

```rust
fn main() {
    let x = 0;
    if x == 10 {
        println!("Ten!");
    } else {
        println!("Not ten!");
    }
}
```

---

# variables 3

```bash
⚠️  Compilation of exercises/variables/variables3.rs failed!, Compiler error message:

error[E0384]: cannot assign twice to immutable variable `x`
 --> exercises/variables/variables3.rs:9:5
  |
7 |     let x = 3;
  |         -
  |         |
  |         first assignment to `x`
  |         help: consider making this binding mutable: `mut x`
8 |     println!("Number {}", x);
9 |     x = 5; // don't change this line
  |     ^^^^^ cannot assign twice to immutable variable

error: aborting due to previous error
```

`x`가 mutable하지 않은데 값을 변경했다고 알려준다. 친절하게 어떻게 바꿔야 하는지 help로 알려준다. 그대로 따라하면 된다.

<br>

**Solution**

```rust
fn main() {
    let mut x = 3;
    println!("Number {}", x);
    x = 5; // don't change this line
    println!("Number {}", x);
}
```

---

# variables 4

```bash
⚠️  Compilation of exercises/variables/variables4.rs failed!, Compiler error message:

error[E0381]: borrow of possibly-uninitialized variable: `x`
 --> exercises/variables/variables4.rs:8:27
  |
8 |     println!("Number {}", x);
  |                           ^ use of possibly-uninitialized `x`
  |
  = note: this error originates in the macro `$crate::format_args_nl` (in Nightly builds, run with -Z macro-backtrace for more info)

error: aborting due to previous error
```

초기화하지 않은 변수 `x`를 사용했다고 한다. Variable 2에서도 알아봤듯 rust에선 선언과 동시에 변수 초기화를 무조건 하는 게 편하다.

<br>

**Solution**

```rust
fn main() {
    let x = 0;
    println!("Number {}", x);
}
```

---

# variables 5

```bash
⚠️  Compilation of exercises/variables/variables5.rs failed!, Compiler error message:

error[E0308]: mismatched types
 --> exercises/variables/variables5.rs:9:14
  |
7 |     let number = "T-H-R-E-E"; // don't change this line
  |                  ----------- expected due to this value
8 |     println!("Spell a Number : {}", number);
9 |     number = 3;
  |              ^ expected `&str`, found integer

error[E0369]: cannot add `{integer}` to `&str`
  --> exercises/variables/variables5.rs:10:48
   |
10 |     println!("Number plus two is : {}", number + 2);
   |                                         ------ ^ - {integer}
   |                                         |
   |                                         &str

error: aborting due to 2 previous errors
```

`number` 타입이 `&str`인데 여기에 3을 대입하고 있다. 심지어 `number`는 mutable도 아니다. 변수를 같은 이름으로 새로 선언하는 shadowing 기법으로 해결할 수 있다.

<br>

**Solution**

```rust
fn main() {
    let number = "T-H-R-E-E"; // don't change this line
    println!("Spell a Number : {}", number);
    let number = 3;
    println!("Number plus two is : {}", number + 2);
}
```

---

# variables 6

```bash
⚠️  Compilation of exercises/variables/variables6.rs failed!, Compiler error message:

error: missing type for `const` item
 --> exercises/variables/variables6.rs:6:7
  |
6 | const NUMBER = 3;
  |       ^^^^^^ help: provide a type for the constant: `NUMBER: i32`

error: aborting due to previous error
```

const 변수의 경우 타입을 반드시 명시해야 한다. help 메시지로 친절히 안내도 해준다.

<br>

**Solution**

```rust
const NUMBER: i32 = 3;
fn main() {
    println!("Number {}", NUMBER);
}
```

---

# Summary

기초적인 변수 사용법을 알아봤다. 아직까지는 전혀 어려운 점이 없다.
