---
title: Rustling - Intro
date: 2022-07-07 23:00:00 +0900
categories: [rust, rustling]
tags: [rust]     # TAG names should always be lowercase
---

# Rustling

rust를 재밌는 퀴즈와 같이 배울 수 있는 튜토리얼이다. 에러가 있는 rust 코드가 주어지면 올바르게 고쳐야 한다. 아래 링크에서 설치할 수 있다.

[GitHub - rust-lang/rustlings](https://github.com/rust-lang/rustlings)

rustup만 있다면 명령어 한 줄로 설치가 된다. 나는 rust를 arch repository에서 받았기에 rustup을 따로 설치해야 했는데... rust가 설치된 상태에선 rustup을 설치 못하더라... 귀찮게 기존 rust를 지우고 진행해야 했다.

설치된 `rustling` 디렉토리로 가서 우리가 풀어야 할 퀴즈를 알아보자.

```bash
rustlings list
```

이 명령어를 치면 문제 목록이 나온다. 이건 난이도 순으로 정렬되어 있으므로 아래 순서대로 풀면 된다.

```bash
Name                 Path                                              Status 
intro1               exercises/intro/intro1.rs                         Pending
intro2               exercises/intro/intro2.rs                         Pending
variables1           exercises/variables/variables1.rs                 Pending
variables2           exercises/variables/variables2.rs                 Pending
variables3           exercises/variables/variables3.rs                 Pending
variables4           exercises/variables/variables4.rs                 Pending
variables5           exercises/variables/variables5.rs                 Pending
variables6           exercises/variables/variables6.rs                 Pending
functions1           exercises/functions/functions1.rs                 Pending
functions2           exercises/functions/functions2.rs                 Pending
functions3           exercises/functions/functions3.rs                 Pending
functions4           exercises/functions/functions4.rs                 Pending
functions5           exercises/functions/functions5.rs                 Pending
if1                  exercises/if/if1.rs                               Pending
if2                  exercises/if/if2.rs                               Pending
quiz1                exercises/quiz1.rs                                Pending
move_semantics1      exercises/move_semantics/move_semantics1.rs       Pending
move_semantics2      exercises/move_semantics/move_semantics2.rs       Pending
move_semantics3      exercises/move_semantics/move_semantics3.rs       Pending
move_semantics4      exercises/move_semantics/move_semantics4.rs       Pending
move_semantics5      exercises/move_semantics/move_semantics5.rs       Pending
move_semantics6      exercises/move_semantics/move_semantics6.rs       Pending
primitive_types1     exercises/primitive_types/primitive_types1.rs     Pending
primitive_types2     exercises/primitive_types/primitive_types2.rs     Pending
primitive_types3     exercises/primitive_types/primitive_types3.rs     Pending
primitive_types4     exercises/primitive_types/primitive_types4.rs     Pending
primitive_types5     exercises/primitive_types/primitive_types5.rs     Pending
primitive_types6     exercises/primitive_types/primitive_types6.rs     Pending
structs1             exercises/structs/structs1.rs                     Pending
structs2             exercises/structs/structs2.rs                     Pending
structs3             exercises/structs/structs3.rs                     Pending
enums1               exercises/enums/enums1.rs                         Pending
enums2               exercises/enums/enums2.rs                         Pending
enums3               exercises/enums/enums3.rs                         Pending
modules1             exercises/modules/modules1.rs                     Pending
modules2             exercises/modules/modules2.rs                     Pending
modules3             exercises/modules/modules3.rs                     Pending
vec1                 exercises/collections/vec1.rs                     Pending
vec2                 exercises/collections/vec2.rs                     Pending
hashmap1             exercises/collections/hashmap1.rs                 Pending
hashmap2             exercises/collections/hashmap2.rs                 Pending
strings1             exercises/strings/strings1.rs                     Pending
strings2             exercises/strings/strings2.rs                     Pending
quiz2                exercises/quiz2.rs                                Pending
errors1              exercises/error_handling/errors1.rs               Pending
errors2              exercises/error_handling/errors2.rs               Pending
errors3              exercises/error_handling/errors3.rs               Pending
errors4              exercises/error_handling/errors4.rs               Pending
errors5              exercises/error_handling/errors5.rs               Pending
errors6              exercises/error_handling/errors6.rs               Pending
generics1            exercises/generics/generics1.rs                   Pending
generics2            exercises/generics/generics2.rs                   Pending
generics3            exercises/generics/generics3.rs                   Pending
option1              exercises/option/option1.rs                       Pending
option2              exercises/option/option2.rs                       Pending
option3              exercises/option/option3.rs                       Pending
traits1              exercises/traits/traits1.rs                       Pending
traits2              exercises/traits/traits2.rs                       Pending
tests1               exercises/tests/tests1.rs                         Pending
tests2               exercises/tests/tests2.rs                         Pending
tests3               exercises/tests/tests3.rs                         Pending
quiz3                exercises/quiz3.rs                                Pending
box1                 exercises/standard_library_types/box1.rs          Pending
arc1                 exercises/standard_library_types/arc1.rs          Pending
iterators1           exercises/standard_library_types/iterators1.rs    Pending
iterators2           exercises/standard_library_types/iterators2.rs    Pending
iterators3           exercises/standard_library_types/iterators3.rs    Pending
iterators4           exercises/standard_library_types/iterators4.rs    Pending
iterators5           exercises/standard_library_types/iterators5.rs    Pending
threads1             exercises/threads/threads1.rs                     Pending
macros1              exercises/macros/macros1.rs                       Pending
macros2              exercises/macros/macros2.rs                       Pending
macros3              exercises/macros/macros3.rs                       Pending
macros4              exercises/macros/macros4.rs                       Pending
quiz4                exercises/quiz4.rs                                Pending
clippy1              exercises/clippy/clippy1.rs                       Pending
clippy2              exercises/clippy/clippy2.rs                       Pending
using_as             exercises/conversions/using_as.rs                 Pending
from_into            exercises/conversions/from_into.rs                Pending
from_str             exercises/conversions/from_str.rs                 Pending
try_from_into        exercises/conversions/try_from_into.rs            Pending
as_ref_mut           exercises/conversions/as_ref_mut.rs               Pending
advanced_errs1       exercises/advanced_errors/advanced_errs1.rs       Pending
advanced_errs2       exercises/advanced_errors/advanced_errs2.rs       Pending
Progress: You completed 0 / 84 exercises (0.00 %).
```

---

# Intro 1

```bash
Hello and
       welcome to...                      
                 _   _ _                  
  _ __ _   _ ___| |_| (_)_ __   __ _ ___  
 | '__| | | / __| __| | | '_ \ / _` / __| 
 | |  | |_| \__ \ |_| | | | | | (_| \__ \ 
 |_|   \__,_|___/\__|_|_|_| |_|\__, |___/ 
                               |___/      

This exercise compiles successfully. The remaining exercises contain a compiler
or logic error. The central concept behind Rustlings is to fix these errors and
solve the exercises. Good luck!

✅ Successfully ran exercises/intro/intro1.rs
```

intro 1은 단순한 환영 인사다. 바로 다음으로 넘어가면 된다.

다음 문제로 넘어가기 위해서는 해당 문제의 Rust 코드 안의 주석 중 `I AM NOT DONE`을 제거하면 된다.

따라서 우리가 intro 1번 문제에서 해야 할 것은 아래 있는 코드에서 `I AM NOT DONE`이란 주석을 지우는 것 뿐이다.

<br>

**Solution**

```rust
fn main() {
    println!("Hello and");
    println!(r#"       welcome to...                      "#);
    println!(r#"                 _   _ _                  "#);
    println!(r#"  _ __ _   _ ___| |_| (_)_ __   __ _ ___  "#);
    println!(r#" | '__| | | / __| __| | | '_ \ / _` / __| "#);
    println!(r#" | |  | |_| \__ \ |_| | | | | | (_| \__ \ "#);
    println!(r#" |_|   \__,_|___/\__|_|_|_| |_|\__, |___/ "#);
    println!(r#"                               |___/      "#);
    println!();
    println!("This exercise compiles successfully. The remaining exercises contain a compiler");
    println!("or logic error. The central concept behind Rustlings is to fix these errors and");
    println!("solve the exercises. Good luck!");
}
```

---

# Intro 2

```bash
⚠️  Compilation of exercises/intro/intro2.rs failed!, Compiler error message:

error: 1 positional argument in format string, but no arguments were given
 --> exercises/intro/intro2.rs:8:21
  |
8 |     println!("Hello {}!");
  |                     ^^

error: aborting due to previous error
```

어떤 언어든 처음으로 할 일은 `Hello world!`를 출력하는 프로그램을 작성하는 것이다. 그런데 `World`가 와야 할 자리에 placeholer인 중괄호만 딸랑 있다. 이에 대응되는 argument가 없다는 컴파일러의 메시지다.

단순히 `{}`를 `world`로 바꿔도 되지만, `{}`에 `world`를 전달해보자.

<br>

**Solution**

```rust
fn main() {
    println!("Hello {}!", String::from("World"));
}
```

---

# Summary

rustling을 설치하고 간단히 사용법을 알아봤다.
