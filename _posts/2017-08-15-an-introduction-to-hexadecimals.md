---
layout: post
title:  "An Introduction to Hexadecimals"
description: "An article explaining the basics of hexadecimals"
date:   2017-08-15 19:53:00 +0800
categories: comp-sci-concepts
---

Hexadecimals are an important concept in computing, especially in low-level programs. Essentially, hexidecimal (or hex) is a numerical system of base 16, whereby the numbers 0 to 9 are represented as usual but the numbers 10, 11, 12, 13, 14 and 15 are represented by a, b, c, d, e and f respectively. In most programming languages, the prefix for hex numbers is denoted by '0x'. For example, the number 255 is `0xff` in hex. While it may not be immediately apparent how hex numbers work, we need to go to the register-level to understand their application.

Imagine the computer registers consisting of four boxes arranged in a row. Two of these arrangements would make eight boxes: a byte of data. Let's focus on half a byte for now. To represent some form of value, the boxes must either be `1` or `0`. From right to left, the value held by each box would be `2^n`, where `n` is 0 to 3:

![Empty registers with labels](/img/posts/2017-08-15-an-introduction-to-hexadecimals/emptyregisters.png)

Let's say we want to store an `int`-type variable with a value of 13. To obtain the binary equivalent of that value, we simply set to `1` the boxes that will sum up to 13 and set the remaining boxes (if any) to `0`:

![13 in binary](/img/posts/2017-08-15-an-introduction-to-hexadecimals/13inhex.png)

In hex, this value would be written as `0xd`. Now, you could argue that it would be more straightforward if we simply wrote 13 as, well... 13! However, it may not make sense to use decimals when representing larger numbers in certain applications, whereby the positions of the `1`'s and `0`'s actually matter!

Let's move on to a practical example. Let's say we have an array of eight LEDs attached to a microcontroller. To switch on the LEDs, we have to set an 8-bit integer as output on the LED port. To achieve a pattern as shown bellow, we need to determine the equivalent number representation.

![LED array showing 0101 1100](/img/posts/2017-08-15-an-introduction-to-hexadecimals/LEDarray.png)

Calculating the sum of values represented by the lit up LEDs, we get: 

```
2^6 + 2^4 + 2^3 + 2^2 = 64 + 16 + 8 + 4 = 92
```

Simple enough. But is there an easier way to represent the value? The answer is to represent it in hex. First, treat the LEDs like boxes and split them up into groups of four. Then, relabel the values to match only the first case, ie `2^n` where `n` is 0 up to 3:

![LEDs grouped in boxes](/img/posts/2017-08-15-an-introduction-to-hexadecimals/LEDinboxes.png)

By adding up the values from each group, we get 5 from the group on the left side (`L7` to `L4`) and 12 from the group on the right side (`L3` to `L0`). In hex, 5 is still 5 but 12 is represented by the letter 'c'. Therefore, we can simply combine the two groups and obtain `0x5c` as the value, which is equivalent to 92! By using hex, we can easily identify the value represented in the registers without having to do extensive sums.