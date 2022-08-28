---
layout: post
title:  "Vacuous truth"
date:   2022-08-28 19:21:00 +0300
---
# Vacuous truth

In logic, a vacuous truth is a conditional statement that is true because the condition is false or logically unrelated to the assertion.

For example, the statement "all cats in the room are *black*" will be true when no cats are in the room. At the same time, the statement "all cats in the room are *white*" would also be vacuously true, because it does not really say anything.

> Alice: Which way should I go?<br>
> Cat: That depends on where you are going.<br>
> Alice: I don’t know.<br>
> Cat: Then it doesn’t matter which way you go.<br>
> *― Lewis Carroll, Alice in Wonderland*

It's all good until your condition says otherwise.

 This logic described as the [material condition](https://en.wikipedia.org/wiki/Material_conditional) (also known as material implication) P → Q, which is true unless P is true and Q is false:

| P   | Q   | P → Q |
|:---:|:---:|:-----:|
| ✅  | ✅   | ✅    |
| ✅  | ❌   | ❌    |
| ❌  | ✅   | ✅    |
| ❌  | ❌   | ✅    |

For example:

| P                  | Q                     | P → Q |
| ---               | ---                  | :---: |
| If it's a duck     | it quacks        | ✅    |
| If it's a duck     | it doesn't quack | ❌    |
| If it's not a duck | it quacks        | 🤔    |
| If it's not a duck | it doesn't quack | 🤯    |

If the premise is false or unrelated (3rd and 4th cases), then any further (even absurd) conclusions seem valid.

In Ruby [Enumeration#all?](https://ruby-doc.org/core-3.1.2/Enumerable.html#method-i-all-3F) of empty collection returns `true`:
```
[].all? # => true
```
You can pass anything you want in the block, and it will always return `true` and the block will not be executed:
```
[].all?(&:absurd?) # => true
```

On the other hand, [#any?](https://ruby-doc.org/core-3.1.2/Enumerable.html#method-i-any-3F) of empty collection returns `false`, however the passed block will not be executed either:
```
[].any?            # => false
[].any?(&:absurd?) # => false
```

[Vacuous truth @ Wikipedia](https://en.wikipedia.org/wiki/Vacuous_truth)
