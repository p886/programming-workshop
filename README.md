# Programming Workshop

## Contents

- [Basic][#basics]
- [Data Types][#data-types]
- [Arrays][#arrays]

# Basics

Hello! Let's learn Javascript. It's a great and easy-to-learn language that is used all over the web and on servers. The concepts you'll learn here are applicable to all other programming languages though.

## What is programming all about?

Programming means giving your computer instructions. Computers think in 0s and 1s (also known as binary code or just binary). It's possible but really hard to program in binary. Therefore people came up with programming languages that are an abstraction of binary and make it easier for humans to program.

Very simplified a programming langue sits between your idea of what your computer should do and the binary code:

```
Your task                                  Binary code
------------------------------------------------------------
calculate 1+1   --programming language-->  0100101101010011010...
open that file  --programming language-->  0111101110111011111...
export as PDF   --programming language-->  0100010100111100000...
```

## REPL

To get started with programming we'll be using the Javascript console that is built in your browser. You can type code directly into the console. When you hit `Enter` it will be evaluated and the result will be printed to the screen. That's why this kind of interaction is called a `Read, Evaluate, Print, Loop` or `REPL` for short.

## Comments

In Javascript everything after `//` will be ignored and can be used for documenting your code.

```
// this is a comment
```

In this guide I will use `// ->` to indicate what a piece of code evaluates to.

# Data Types

There are few different ways you can store data in your program.

## Integers

### Example

```
1+1
// -> 2
```

Integers are just simple numbers without any decimal part.

## Floats

Unlike integers, floats do have a decimal part.

```
42.0
165.4344
3.23 + 54.2 // -> 57.43
```

Sometimes the conversion from binary to decimal numbers can lead to unexpected results:

```
0.2 + 0.1
// -> 0.30000000000000004
```

The reason for that is that `0.3` in base 2 is a repeating decimal just like 1/3 = 0.333.... is in decimal. There are libraries to handle proper decimal arithmetic.

## Strings

Strings are delimited by double quotes `"` or single quotes `'`. They are useful for storing textual data. Some data that consists of numbers should also be treated as string, like phone numbers.

```
"this is a string"
'this is another string'
"A 3rd string"
```

If you want to use single-quotes in a string you should use double quotes as delimiter, and vice-versa.

```
"Philipp's PC"
'He said: "Thank you"'
```

Strings can also span mutliple lines:

```
"Stars shining bright above you,
Night breezes seem to whisper 'I love you'"
```

## Boolean

The boolean data type consists of the values `true` and `false`. Some helpful operations on these data types are:

### Logical AND

```
true  && true  // -> true
true  && false // -> false
false && true  // -> false
false && false // -> false
```

The logical AND returns `true` only if both sides evaluate to `true`.

### Logical OR

```
true  || true  // -> true
true  || false // -> true
false || true  // -> true
false || false // -> false
```

The logical OR returns `true` if at least one of the two sides evaluate to `true`.

# Arrays

You can think of arrays like a list of other data. The elements of these lists can be of any data type.

```
['This', 'is', 'an', 'array', 'of', 'strings']
[1, 2 , 3, 2, 1]
```

You can have as much or as little space between the elements as you want. It is generally recommended to have one space after the comma:

```
[1,2,2,2,2    3,          4] // works but looks weird
[1, 2, 2, 2, 2, 3, 4]        // better
```

If you have really long arrays you can span them over mutliple lines:

```
[
  "my very long list of favorite foods",
  "spaghetti",
  "apples",
  "steak",
  "peanut butter"
]
```

## Accessing Elements in Arrays

Creating arrays is fine but how do you get data out of them? This way

```
['first', 'second', 'third'][0] // -> 'first'
['first', 'second', 'third'][1] // -> 'second'
['first', 'second', 'third'][2] // -> 'second'
```

Two things to note here:

1. You put the position of the elemnt you want to have in square brackets after the array: `[0]`
2. You start counting at zero. So the first element is at position zero.

Accessing a position that is not in the array will give you back `undefined`. In other programming languages this might result in a hard error that could crash your program.

```
[1,2,3][10] // -> undefined
```
