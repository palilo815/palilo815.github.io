---
title: rustling - functions
date: 2022-07-09 23:50:00 +0900
categories: [rust, rustling]
tags: [rust]     # TAG names should always be lowercase
---

# functions 1

```bash
⚠️  Compilation of exercises/functions/functions1.rs failed!, Compiler error message:

error[E0425]: cannot find function `call_me` in this scope
 --> exercises/functions/functions1.rs:7:5
  |
7 |     call_me();
  |     ^^^^^^^ not found in this scope

error: aborting due to previous error
```

`call_me`란 함수가 없다고 한다. 아무 기능을 갖는 함수를 하나 만들어주자.

<br>

**Solution**

```rust
fn call_me() {}

fn main() {
    call_me();
}
```

---

# functions 2

```bash
⚠️  Compilation of exercises/functions/functions2.rs failed!, Compiler error message:

error: expected type, found `)`
  --> exercises/functions/functions2.rs:10:16
   |
10 | fn call_me(num:) {
   |                ^ expected type

error[E0425]: cannot find value `num` in this scope
  --> exercises/functions/functions2.rs:11:17
   |
11 |     for i in 0..num {
   |                 ^^^ not found in this scope

error: aborting due to 2 previous errors
```

`num`의 타입이 필요하다고 말한다. `main`에서 호출할 때 `call_me(3)`으로 호출하므로, `num`에게 integer 타입 아무거나 넣어주자.

<br>

**Solution**

```rust
fn main() {
    call_me(3);
}

fn call_me(num: i32) {
    for i in 0..num {
        println!("Ring! Call number {}", i + 1);
    }
}
```

---

# functions 3

```bash
⚠️  Compilation of exercises/functions/functions3.rs failed!, Compiler error message:

error[E0061]: this function takes 1 argument but 0 arguments were supplied
  --> exercises/functions/functions3.rs:7:5
   |
7  |     call_me();
   |     ^^^^^^^-- supplied 0 arguments
   |     |
   |     expected 1 argument
   |
note: function defined here
  --> exercises/functions/functions3.rs:10:4
   |
10 | fn call_me(num: u32) {
   |    ^^^^^^^ --------

error: aborting due to previous error
```

인자 없이 호출했다고 한다. 적절한 값을 넣어주자.

<br>

**Solution**

```rust
fn main() {
    call_me(0);
}

fn call_me(num: u32) {
    for i in 0..num {
        println!("Ring! Call number {}", i + 1);
    }
}
```

---

# functions 4

```bash
⚠️  Compilation of exercises/functions/functions4.rs failed!, Compiler error message:

error: expected type, found `{`
  --> exercises/functions/functions4.rs:14:30
   |
14 | fn sale_price(price: i32) -> {
   |                              ^ expected type

error: aborting due to previous error
```

리턴 타입을 넣어주자. (너무 쉬워서 슬슬 질린다)

<br>

**Solution**

```rust
fn main() {
    let original_price = 51;
    println!("Your sale price is {}", sale_price(original_price));
}

fn sale_price(price: i32) -> i32 {
    if is_even(price) {
        price - 10
    } else {
        price - 3
    }
}

fn is_even(num: i32) -> bool {
    num % 2 == 0
}
```

---

# functions 5

```bash
⚠️  Compilation of exercises/functions/functions5.rs failed!, Compiler error message:

error[E0308]: mismatched types
  --> exercises/functions/functions5.rs:11:24
   |
11 | fn square(num: i32) -> i32 {
   |    ------              ^^^ expected `i32`, found `()`
   |    |
   |    implicitly returns `()` as its body has no tail or `return` expression
12 |     num * num;
   |              - help: remove this semicolon

error: aborting due to previous error
```

아무 값도 리턴하지 않고 있다. `return num * num;`라고 하거나 세미콜론을 빼고 `num * num`으로 고치면 된다.

<br>

**Solution**

```rust
fn main() {
    let answer = square(3);
    println!("The answer is {}", answer);
}

fn square(num: i32) -> i32 {
    num * num
}
```

---

# Summary

기초적인 함수 사용법을 알아봤다. 슬슬 질린다.
