---
title: imaginary numbers
tags:
  - math
date created: 23.01.04, 11:21:31
date modified: 23.01.06, 10:42:48
---

## initial thoughts

> i remember learning this in high school, but it didn't really stick
>
> i think i had issues because there doesn't seem to be any real-world applications for this
>
> i may be wrong, but i think this exists because there exist roadblocks in some other branches of math and $i$ and $i^2$ help to cancel out $\sqrt{-1}$

## why do we need imaginary numbers?

[[solving equations by inventing a number system]]

> this reasoning helps me think about imaginary numbers in a useful way!

## imaginary unit

$$
i = \sqrt{-1}
$$

$$
i^2 = -1
$$

above: this is the crux of complex numbers

| $i^x$ | equals |
| ----- | ------ |
| $i^0$ | $1$    |
| $i^1$ | $i$    |
| $i^2$ | $-1$   |
| $i^3$ | $-i$   |
| $i^4$ | $1$    |
| $i^5$ | $i$    |
| $i^6$ | $-1$   |
| $i^7$ | $-i$   |

- if the exponent is even, it is equal to $1$ or $-1$
	- if the exponent is a multiple of 4, it is equal to 1
- if the exponent is odd, it is equal to $i$ or $-i$

finding the nearest exponent divisible by $4$:

$$
i^{138} = i^{136} \cdot i^2 = 1 \cdot -1 = -1
$$

above: we break it into $i^{136}$ and $i^2$. $136$ is divisible by $4$ so it equals $1$, and $i^2$ is equal to $-1$. easy peasy!

## simplifying

- *pure imaginary numbers* take the form $bi$ where $b$ is a nonzero real number
- examples:
	- $3i$
	- $i\sqrt{5}$
	- $-12i$

$$
\sqrt{-9} = \sqrt{-1} \cdot \sqrt{9} = i \cdot 3
$$

| simplified  | unsimplified   |
| ----------- | -------------- |
| $3i$        | $\sqrt{-9}$    |
| $i\sqrt{5}$ | $\sqrt{-5}$    |
| $-12i$      | $-\sqrt{-144}$ |

with $i$, and [[math glossary#simplifying radicals|simplifying radicals]]:

$$
\sqrt{-24} = \sqrt{-1} \cdot \sqrt{4} \cdot \sqrt{6} = i \cdot 2 \cdot \sqrt{6} =2i\sqrt{6}
$$

## the complex plane

![[graphing complex numbers.png]]

above: graphing $-3 + 3.5i$, $3 + 2i$, and $1 - 4i$; the x-axis becomes the real-number-axis, the y-axis becomes the imaginary-number-axis
