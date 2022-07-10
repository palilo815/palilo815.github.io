---
title: Rustling - 벼ㅑ
date: 2022-07-10 14:35:00 +0900
categories: [rust, rustling]
tags: [rust]     # TAG names should always be lowercase
---

# quiz 1

```bash
// Mary is buying apples. One apple usually costs 2 Rustbucks, but if you buy
// more than 40 at once, each apple only costs 1! Write a function that calculates
// the price of an order of apples given the quantity bought. No hints this time!
```

위에서 요구한대로 사과 개수에 따른 가격을 리턴해주는 함수 `fn calculate_apple_price`를 만들면 된다. 백준 브론즈 5급의 난이도 문제다.

<br>

**Solution**

```rust
fn calculate_apple_price(apple: i32) -> i32 {
    if apple > 40 {
        apple
    } else {
        apple * 2
    }
}

#[test]
fn verify_test() {
    let price1 = calculate_apple_price(35);
    let price2 = calculate_apple_price(40);
    let price3 = calculate_apple_price(65);

    assert_eq!(70, price1);
    assert_eq!(80, price2);
    assert_eq!(65, price3);
}
```

---

# Summary

처음 언어를 배울 때 배우는 가장 기초적인 내용을 지금까지 다뤘다. 다음부터는 좀 더 심오한 내용의 퀴즈가 나오길 바란다.
