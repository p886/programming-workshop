# Programming Workshop

## Contents

- [Basics](#basics)
- [Data Types](#data-types)
- [Variables](#variables)
- [Arrays](#arrays)
- [Methods](#methods)

# Basics

Hello! Let's learn how to write software a.k.a programming. We will be using the language Ruby. However, the concepts you'll learn here are applicable to all other programming languages.

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

## Tools

[repl.it](https://repl.it/languages/ruby) provides you with an online ruby development enviroment. There is no need to install anything on your computer.

## Comments

In Ruby everything after `#` will be ignored and can be used for documenting your code.

```
# this is a comment
```

In this guide I will use `# ->` to indicate what a piece of code evaluates to.

# Data Types

There are few different ways you can store data in your program.

## Integers

### Example

```
1+1
# -> 2
```

Integers are just simple numbers without any decimal part.

## Floats

Unlike integers, floats do have a decimal part.

```
42.0
165.4344
3.23 + 54.2 # -> 57.43
```

Sometimes the conversion from binary to decimal numbers can lead to unexpected results:

```
0.2 + 0.1
# -> 0.30000000000000004
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
true  && true  # -> true
true  && false # -> false
false && true  # -> false
false && false # -> false
```

The logical AND returns `true` only if both sides evaluate to `true`.

### Logical OR

```
true  || true  # -> true
true  || false # -> true
false || true  # -> true
false || false # -> false
```

The logical OR returns `true` if at least one of the two sides evaluate to `true`.

### Equality

You can use `==` to check whether two values are equal to each other. Be careful with the syntax: A single equal sign (`=`) has a completely different meaning (see below [Arrays](#arrays) and [Variables](#variables)). So be sure to use a double equal sign to test for equality.

```
"foo" == "foo" # -> true
    1 == 2     # -> false
```

## nil

In Ruby the value `nil` denotes no value at all. It can be explicitly returned from code you write. `nil` will pop up in code every time no "real" value can be given and it is treated like `false` by logical operators:

```
nil && true # -> nil
nil || true # -> true
```

# Variables

Variables store data to be referenced at a later point in time.

```
# defining two variables (aka declarating)
my_variable = "hello"
another_variable = [true]

# referencing those variables
my_variable # -> "hello"
another_variable # -> [true]
```

Trying to reference a variable that is not defined (or not in scope, see below) will give you an error, that will look something like this:

```
asdf
# -> NameError: undefined local variable or method `asdf' for main:Object
```

That also happens if you have a typo either in the declaration or reference of your variable. In Ruby it is convetion to use underscores in variable names:

```
thisIsMyVariable    = true # -> not following convetion
thisismyvariable    = true # -> not following convetion
this_is_my_variable = true # -> following convetion
```

# Arrays

You can think of arrays like a list of other data. The elements of these lists can be of any data type.

```
['This', 'is', 'an', 'array', 'of', 'strings']
[1, 2 , 3, 2, 1]
```

You can have as much or as little space between the elements as you want. It is generally recommended to have one space after the comma:

```
[1,2,2,2,2    3,          4] # works but looks weird
[1, 2, 2, 2, 2, 3, 4]        # better
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
['first', 'second', 'third'][0] # -> 'first'
['first', 'second', 'third'][1] # -> 'second'
['first', 'second', 'third'][2] # -> 'second'
```

Two things to note here:

1. You put the position of the element you want to have in square brackets after the array: `[0]`
2. You start counting at zero. So the first element is at position zero.

Accessing a position that is not in the array will give you back `undefined`. In other programming languages this might result in a hard error that could crash your program.

```
[1,2,3][10] # -> nil
```

## Updating Arrays

If you want to update an array you can use the assignment operator (`=`):

```
my_array = [1,2,3]
my_array[1] = "updated"
my_array # -> [1, "updated", 3]
```

# Methods

Methods hold code that can be executed by calling the method from a different place in the code. This simple concept is very powerful and the backbone of programming. Here's how you define a method:

```
def my_method()
  # code…
end
```

First we have the `def` keyword, then the name of the method. This name has to be unique, like for variables. Then an opening and closing parantheses `()`. After a newline you would provide code in what is called the **body** of a method. In this example we just have a comment in the body. By convetion the body of the method is preceded by two spaces. This is called **indentation** and really helps the readability of your code. Finally, you close the body by providing the `end` keyword.

Here's a method that calculates `1+1`:

```
def one_plus_one()
  1+1
end
```

We can verify that it works by calling the method:

```
one_plus_one() # -> 2
```

Calling a method works by appending the opening and closing parentheses after the method name: `one_plus_one()`. As you can see (or try for yourself) calling the method evaluates to the integer `2`. In programming terms we can say that the method `one_plus_one` *returned* the value `2`. In some programming languages you have to explicitly add a `return` keyword, or the method will return `nil` or some other not-that-useful value:

```
def one_plus_one()
  return 1+1
end
```

While you can explicitly add a `return`, this is not necessary in Ruby. Any method will return the value of the last line it evaluated.

Of course always calculating the result of `1+1` is not that helpful. It would be more helpful if we could add any two numbers together. This can be achieved by providing so called **arguments** to your method:

```
def add(first, second)
  first + second
end
```

When calling this method you need to provide these arguments (i.e. the numbers you want to add):

```
add(1, 100) # -> 101
```

If you don't provide the arguments you'll get an error:

```
add()
# -> ArgumentError: wrong number of arguments (given 0, expected 2)
```

## Exercises

- Write a method that checks whether two values are equal to each other and store the result in a variable.
- Write a method that calls another method.
- Write a method that calls another method that calls another method.
- Write a method that adds "hello" to any name given as argument. Hint: You can combine two strings like this: `"first string" + "second string"`. Make sure there is a space between "Hello" and the name.
- Write a method that takes a single argument but always returns `nil` no matter what you give as argument.
