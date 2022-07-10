---
title: rustling - move_semantics
date: 2022-07-10 17:30:00 +0900
categories: [rust, rustling]
tags: [rust]     # TAG names should always be lowercase
---

# move_semantics 1

```bash
⚠️  Compilation of exercises/move_semantics/move_semantics1.rs failed!, Compiler error message:

error[E0596]: cannot borrow `vec1` as mutable, as it is not declared as mutable
  --> exercises/move_semantics/move_semantics1.rs:13:5
   |
9  |     let vec1 = fill_vec(vec0);
   |         ---- help: consider changing this to be mutable: `mut vec1`
...
13 |     vec1.push(88);
   |     ^^^^^^^^^^^^^ cannot borrow as mutable

error: aborting due to previous error
```

mutable 문제다. `mut`만 추가해주면 된다. 아마 `vec`가 함수로 전달되는 예시를 보여주기 위해 넣은 문제같다.

<br>

**Solution**

```rust
// move_semantics1.rs
// Make me compile! Execute `rustlings hint move_semantics1` for hints :)

fn main() {
    let vec0 = Vec::new();

    let mut vec1 = fill_vec(vec0);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}

fn fill_vec(vec: Vec<i32>) -> Vec<i32> {
    let mut vec = vec;

    vec.push(22);
    vec.push(44);
    vec.push(66);

    vec
}
```

---

# move_semantics 2

```bash
⚠️  Compilation of exercises/move_semantics/move_semantics2.rs failed!, Compiler error message:

error[E0382]: borrow of moved value: `vec0`
  --> exercises/move_semantics/move_semantics2.rs:13:57
   |
8  |     let vec0 = Vec::new();
   |         ---- move occurs because `vec0` has type `Vec<i32>`, which does not implement the `Copy` trait
9  |
10 |     let mut vec1 = fill_vec(vec0);
   |                             ---- value moved here
...
13 |     println!("{} has length {} content `{:?}`", "vec0", vec0.len(), vec0);
   |                                                         ^^^^^^^^^^ value borrowed here after move

error: aborting due to previous error
```

아까 문제와 비슷하지만, `vec1`을 만든 이후에 `vec0`을 사용한다. `vec0`은 함수 호출로 인해 *이동*했기 때문에 `main` 함수에서는 사용할 수 없다. `vec0`의 복사본을 전달하는 것으로 해결할 수 있다.

<br>

**Solution**

```rust
// move_semantics2.rs
// Make me compile without changing line 13 or moving line 10!
// Execute `rustlings hint move_semantics2` for hints :)

fn main() {
    let vec0 = Vec::new();

    let mut vec1 = fill_vec(vec0.clone());

    // Do not change the following line!
    println!("{} has length {} content `{:?}`", "vec0", vec0.len(), vec0);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}

fn fill_vec(vec: Vec<i32>) -> Vec<i32> {
    let mut vec = vec;

    vec.push(22);
    vec.push(44);
    vec.push(66);

    vec
}
```

---

# move_semantics 3

```bash
⚠️  Compilation of exercises/move_semantics/move_semantics3.rs failed!, Compiler error message:

error[E0596]: cannot borrow `vec` as mutable, as it is not declared as mutable
  --> exercises/move_semantics/move_semantics3.rs:21:5
   |
20 | fn fill_vec(vec: Vec<i32>) -> Vec<i32> {
   |             --- help: consider changing this to be mutable: `mut vec`
21 |     vec.push(22);
   |     ^^^^^^^^^^^^ cannot borrow as mutable

error[E0596]: cannot borrow `vec` as mutable, as it is not declared as mutable
  --> exercises/move_semantics/move_semantics3.rs:22:5
   |
20 | fn fill_vec(vec: Vec<i32>) -> Vec<i32> {
   |             --- help: consider changing this to be mutable: `mut vec`
21 |     vec.push(22);
22 |     vec.push(44);
   |     ^^^^^^^^^^^^ cannot borrow as mutable

error[E0596]: cannot borrow `vec` as mutable, as it is not declared as mutable
  --> exercises/move_semantics/move_semantics3.rs:23:5
   |
20 | fn fill_vec(vec: Vec<i32>) -> Vec<i32> {
   |             --- help: consider changing this to be mutable: `mut vec`
...
23 |     vec.push(66);
   |     ^^^^^^^^^^^^ cannot borrow as mutable

error: aborting due to 3 previous errors
```

1번과 같은 mutable 문제다. `mut`만 추가해주면 된다.

<br>

**Solution**

```rust
// move_semantics3.rs
// Make me compile without adding new lines-- just changing existing lines!
// (no lines with multiple semicolons necessary!)
// Execute `rustlings hint move_semantics3` for hints :)

fn main() {
    let vec0 = Vec::new();

    let mut vec1 = fill_vec(vec0);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}

fn fill_vec(mut vec: Vec<i32>) -> Vec<i32> {
    vec.push(22);
    vec.push(44);
    vec.push(66);

    vec
}
```

---

# move_semantics 4

```bash
⚠️  Compilation of exercises/move_semantics/move_semantics4.rs failed!, Compiler error message:

error[E0423]: expected value, found macro `vec`
  --> exercises/move_semantics/move_semantics4.rs:23:19
   |
23 |     let mut vec = vec;
   |                   ^^^ not a value

error[E0061]: this function takes 0 arguments but 1 argument was supplied
  --> exercises/move_semantics/move_semantics4.rs:12:20
   |
12 |     let mut vec1 = fill_vec(vec0);
   |                    ^^^^^^^^ ---- supplied 1 argument
   |                    |
   |                    expected 0 arguments
   |
note: function defined here
  --> exercises/move_semantics/move_semantics4.rs:22:4
   |
22 | fn fill_vec() -> Vec<i32> {
   |    ^^^^^^^^

error: aborting due to 2 previous errors
```

불필요한 `vec0`은 없애고, `fill_vec` 함수에서 벡터를 만들어서 전달받으면 된다.

<br>

**Solution**

```rust
// move_semantics4.rs
// Refactor this code so that instead of having `vec0` and creating the vector
// in `fn main`, we create it within `fn fill_vec` and transfer the
// freshly created vector from fill_vec to its caller.
// Execute `rustlings hint move_semantics4` for hints!

fn main() {
    let mut vec1 = fill_vec();

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}

// `fill_vec()` no longer takes `vec: Vec<i32>` as argument
fn fill_vec() -> Vec<i32> {
    let mut vec = Vec::new();

    vec.push(22);
    vec.push(44);
    vec.push(66);

    vec
}
```

---

# move_semantics 5

```bash
⚠️  Compilation of exercises/move_semantics/move_semantics5.rs failed!, Compiler error message:

error[E0499]: cannot borrow `x` as mutable more than once at a time
  --> exercises/move_semantics/move_semantics5.rs:11:13
   |
10 |     let y = &mut x;
   |             ------ first mutable borrow occurs here
11 |     let z = &mut x;
   |             ^^^^^^ second mutable borrow occurs here
12 |     *y += 100;
   |     --------- first borrow later used here

error: aborting due to previous error
```

mutable borrow는 한 번에 하나만 있어야 한다.

<br>

**Solution**

```rust
// move_semantics5.rs
// Make me compile only by reordering the lines in `main()`, but without
// adding, changing or removing any of them.
// Execute `rustlings hint move_semantics5` for hints :)

fn main() {
    let mut x = 100;
    let y = &mut x;
    *y += 100;
    let z = &mut x;
    *z += 1000;
    assert_eq!(x, 1200);
}
```

--- 

# move_semantics 6

```bash
⚠️  Compilation of exercises/move_semantics/move_semantics6.rs failed!, Compiler error message:

error[E0382]: borrow of moved value: `data`
  --> exercises/move_semantics/move_semantics6.rs:12:22
   |
8  |     let data = "Rust is great!".to_string();
   |         ---- move occurs because `data` has type `String`, which does not implement the `Copy` trait
9  |
10 |     get_char(data);
   |              ---- value moved here
11 |
12 |     string_uppercase(&data);
   |                      ^^^^^ value borrowed here after move

error[E0716]: temporary value dropped while borrowed
  --> exercises/move_semantics/move_semantics6.rs:22:13
   |
21 | fn string_uppercase(mut data: &String) {
   |                               - let's call the lifetime of this reference `'1`
22 |     data = &data.to_uppercase();
   |     --------^^^^^^^^^^^^^^^^^^^- temporary value is freed at the end of this statement
   |     |       |
   |     |       creates a temporary which is freed while still in use
   |     assignment requires that borrow lasts for `'1`

error: aborting due to 2 previous errors
```

reference만 추가/삭제해서 풀어야 한다. `get_char`는 소유권을 가지지 말고 `string_uppercase`에겐 소유권을 줘야 한다. 전자는 reference를 주고, 후자는 value를 주게끔 하면 된다.

**Solution**

```rust
// move_semantics6.rs
// Make me compile! `rustlings hint move_semantics6` for hints
// You can't change anything except adding or removing references

fn main() {
    let data = "Rust is great!".to_string();

    get_char(&data);

    string_uppercase(data);
}

// Should not take ownership
fn get_char(data: &String) -> char {
    data.chars().last().unwrap()
}

// Should take ownership
fn string_uppercase(mut data: String) {
    data = data.to_uppercase();

    println!("{}", data);
}
```

---

# Summary

c++에서 머리를 터뜨리는 주범 중 하나가 move와 copy를 효율적으로 쓰는 법인데, Rust에선 효율적인 코드를 쉽게 작성할 수 있다.
