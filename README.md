<div align="center">
    <p>بِسۡمِ اللَّه اِلرَّحۡمَٰنِ اِلرَّحِيمِ</p>
</div>

# Introduction

This guide will often demonstrate commands inside the python REPL (essentially the python shell), which can be accessed simply by running `python` and will be denoted with `>>>`. However, all excercises are expected to be completed by being written as a `.py` file and being executed using `python file.py`. For termux, I recommend installing `nano` (`pkg install nano`) as it is beginner friendly. You may exit once you are done by clicking CTRL once, then pressing x, or by holding the volume down key whikst pressing x (then pressing y to save).

It is recommended that you run the examples in the python shell yourself to maximise your ability to follow along.

# Input and Output

In order to make any interactive program, you need to be able to both display output and receive input. In python you can do these by:

• Using `print`, e.g:
    ```
    >>> print("Negus of Ethiopia")
    Negus of Ethiopia
    ```

• Using `input`, e.g:
    ```
    >>> input()
    ```

As you can (or maybe can't lmao) see, `input()` by itself is not very useful, as it does not display anything to indicate that the iser *should* give input. Instead we can try:

```
>>> input("Negus of:")
Negus of:Ethiopia
```

As you can see, while this does display a prompt, there is no space which frankly, is disgusting. To relieve this issue, we must add the space ourselves:

```
>>> input("Negus of: ")
Negus of: Ethiopia
```

# Variables

Variables are the bread and butter of programming.You are never going to write a "real" program without them. Variables store information which your program can later use. An example of this is:

```
>>> name = input("What is your name? ")
What is your name? Red
>>> print(name)
'Red'
```

# String concatenation

In order to combine strings that you already have, and strings you don't have - you need to concatenate them. In python you can do this in a few ways:

• Using the `+` operator

```
>>> title = input("Provide a title: ")
Provide a title: Negus of Ethiopia
>>> print("You have chosen the title: " + title)
You have chosen the title: Negus of Ethiopia
```

Another method you can use is `.format` - e.g:

```
>>> country = input("Name a country: ")
Name a country: Niger
>>> print("The country you have named is: {0}".format(country))
The country you have named is: Niger
```

Each successive string you'd like to add, you increase the number in the curly braces - for example:

```
>>> print("You have given the title '{0}' and the country '{1}'".format(title, country))
You have given the title 'Negus of Ethiopia' and the country 'Niger'
```

The final method I will specify are f-strings. Every language will probably have some form of this.

```
>>> print(f"You have selected the country of {country}")
You have selected the country of Niger
```

# Excercises I
    i) Write a script that takes a person's name, age, and country of residence and print it to them
    ii) Write a script that takes a person's name and then tells them: "Name, you have been promoted to the Negus of Ethiopia"

# Variable types

In programming languages, variables have types to distinguish the type of information they hold. While some languages are stringent by forcing all variables to be of 1 type ("Once you are the Negus of Ethiopia, you will always be the Negus of Ethiopia" ~kotlin), other languages allow you to change a variable's type as you go ("*I* gave you the Negus title, and I can take it away from you" ~python

In python the basic types are:
    • str (short for string) - this stores text
    • int (short for integer) - this stores whole number
    • boolean - this stores either a `True` or a `False`
    • list - this stores a list, i.e: [name, country]
    • float - this stores decimals and/or whole numbers
    • dict - stores key-value pair, e.g: {'EA': 'Sports'}

The type a variable is affects how you can use it. For example:

```
>>> 1 + 1
2
```

is perfectly valid, whereas:

```
>>> 1 + "1"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

is not. In order to use a variable that is of one type but *should* be another - you need to "cast" it to another type. In python you do this like so:

```
>>> int("1")
1
```

Since all inputs are strings ('str'), this could be useful for performing maths on the input:

```
>>> age = input("How old are you? ")
How old are you? 69
>>> remaining = 420 - int(age)
>>> print(f"That's {remaining} years less than 420!")
That's 351 years less than 420!
>>> print("Also, niiiiiiiice")
Also, niiiiiiiice
```

# Excercises II

    i) Write a script to calculate the year a user was born based on their age
    ii) Ask the user for the current year, and then subtract 2020 from that year. Then tell them they are off by x years (ie. y - 2020)

# Error handling

Ah yes, errors - the bane of every programmer. In programs, it is very easy to get an error - you can get an error because:
  • You're an idiot
  • The programming language you are using is complete unintuitive and absolutely terrible (applicable for js)

Based on what you *should* have learnt (and if you haven't, either go back or request my help), there are some ways you could already produce an error, such as casting user input:

```
>>> age = input("Enter your age: ")
Enter your age: Negus of Ethiopia
>>> int(age)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'Negus of Ethiopia'
```

This is pain because the error completely kills your program. However, do not fret - we are ready to learn how to try and catch thw Negus of Ethiopia. In python, we use what is known as a `try-except` clause (typically `try-catch` in other languages):

```
>>> try:
...   int(age)
... except:
...   print("No you brain-dead moron, I asked for your age!!!!1!!!1!")
...
No you brain-dead moron, I asked for your age!!!!1!!!1!
```

# Excercises III
    i) Write a script that asks for the user's age, and tells them what year they were born in (probably - don't account for them being born in a month we haven't reached) - defend against errors

# If statements

If you know how to code, you know that code is truth. We do not run falsehoods. In that spirit, the following code *always* runs:

```
>>> if True:
...   print(1)
...
1
```

and the following code *never* runs:

```
>>> if False:
...   print(2)
...
```

Obviously, you'll never actually write an if statement for code that you always want to run in all situations, nor will you ever write code that you specifically want to *never* happen - however if statements are good for when you need to run different code in different situations. You can get a boolean by comparing two variables of the same type using the following operators:
    • ==, are the two variables equal - True if yes, False if no
    • !=, are the two variables unequal - True if they are unequal
    • >, is variable 1 greater than variable 2
    • <, is variable 1 less than variable 2
    • >=, is variable 1 greater than or equal to variable 2
    • <= is variable 1 less than or equal to variable 1

Side-Note: If the variables are of different types, but have the same "value", an equality check (==) will return `False` (i.e: "69" == 69).

Example of an if statement:

```
>>> age = input("Enter your age: ")
Enter your age: 69
>>> if age == "69"
...   print("Nice!")
...
Nice!
```

To cover two cases we can do the following:

```
>>> age = input("Enter your age: ")
Enter your age: 76
>>> if age == "69":
...   print("Nice!")
... else:
...   print(f"Your age is {age}")
...
Your age is 76
```

To cover more than two cases you can do the following:

```
>>> age = input("Enter your age: ")
>>> if age == "69":
...   print("Nice!")
... elif age > 150:
...   print("Why are you lying?")
... else:
...   print(f"Your age is {age}")
```

Else statements are optional, and you do not ever *have* to use them. Else statements cannnot come before elif statements (else if in some languages).

In an if/elif's statements condition block (i.e: age == 69), you can have multiple conditions. These can be split using:
    • and (usually && in coding languages) - returns True if both conditions (condition before and condition after) return True
    • or (usually || in coding languages) - returns True if either (1 or both) of the conditions (before and after symbol) return True

Examples:

```
>>> title = "Negus of Ethiopia"
>>> country = "Niger"
>>> country == "Niger" and title == "Queen of England":
False
```

```
>>> title = "Negus of Ethiopia"
>>> country = "Niger"
>>> country == "Nigeria" || title == "Queen of England"
False
```

```
>>> title = "Negus of Ethiopia"
>>> country = "Niger"
>>> country == "Nigeria" || title == "Negus of Ethiopia"
True
```

```
>>> title = "Negus of Ethiopia"
>>> country = "Niger"
>>> country == "Niger" || title == "Negus of Ethiopia"
True
```

If multiple statements are true, only the first one will run - for example:

```
>>> if 1 == 1:
...   print(1)
... elif 2 == 2:
...   print(2)
...
2
```

Some useful tips for conditions:
    • len - checks the length of something - for example: `len(name)` will show how many characters there are in the string `name`.
    • % - modulus operator, returns remainder if two numbers were to be divided by each other, e.g: `5 % 2` would return 2. This is especially usefully for checking if two numbers are divisible by each other such as: `6 % 3 == 0`

# Excercises IV
    i) Ask the user for a number, tell them whether the number was positive or negative [defend against errors]
    ii) Take two numbers from the user, tell the user if they entered the same number or a different one

# Loops

Often-times, you will have to repeat a task again and again. To make this easier (and safer to code), higher level languages have implemented loops. In python we have two types of loops: for loops and while loops.

While loops run based on a condition. For example:

```
>>> while True:
...   print(1)
1
1
```

this checks the condition loop, and if it is `True` it runs the code again. Because the condition is `True` and never changes - this statement runs forever. Conversely:

```
>>> while False:
...   print(1)
...
```

never runs. Typically you wouldn't actually write these two conditions - instead, you would use a variable, which you would change inside the loop. For example:

```
>>> age = input("Enter your age: ")
Enter your age: 10000000
>>> while int(age) > 150:
...   print(f"You ain't {age}, why you lying")
...   age = input("Enter your actual age: "
...
```

In the above example, because age changes inside the loop - the loop may or may not run again, depending on whether the new age is greater than 150.

The other type of loop we have in python are for loops. For loops, rather than working based on conditions, work by iterating over objects such as lists - for example:

```
>>> countries = ["Somalia", "Sudan", "Saudi Arabia", "Niger", "Nigeria", "Ethiopia"]
>>> for country in countries:
...   print(country)
...
Somalia
Sudan
Saudi Arabia
Niger
Nigeria
Ethiopia
```

in this example, `country` is a variable that holds the current item in the list for each iteration.

For loops are also useful if you want to run the loop a specific number of times - you can do this by using `range`. For example:

```
>>> for i in range(10):
...   print(i)
...
0
1
2
3
4
5
6
7
8
9
```

As you can see, the loop has run 10 times. However the value of the variable `i` started at 0, and ended at 9. Usually this doesn't matter - but if it does, you can use `range(1, 11)` instead, which goes from 1 - 10.

If the item you are iterating is empty, then the for loop will simply never run. For example:

```
>>> a = []
>>> for i in a:
...   print(i)
...
```

# Excercises V
    i) Make a script that loops 100 times, make it say "Negus of Ethiopia" each time, but on the 70th iteration (where `i` is 69) make it say "Nice!"
    ii) Ask someone for their age, and make the script count up to it
    iii) Ask someone for a title, and keep asking until they give "Negus of Ethiopia"
    iv) The classic: FizzBuzz - loop through the numbers 1 - 100. If the number is divisible by 3, print "Fizz". If it is divisible by 5, print "Buzz". If it is divisible by both - print "FizzBuzz". If it is divisible by neither print the number itself.

# Methods

Often-times you will find yourself writing code for one reason, and then writing the same or almost exactly the same code again for another reason. This is just terrible, and instead methods should be used.

So what are methods? Methods are essentially self-contained bits of code that can be re-used.

Methods may have an input they take, and/or an output they give. These are completely optional. Usually, in programming languages, you would specify the return (output) type, and the input type(s) - but in python we typically don't. The return type can usually not something you can change in most languages, but python is very lax about that.

An example method (completely useless other than being an example):

```
>>> def doubleNumber(number):
...   return number * 2
...
>>> doubleNumber(50)
100
```

You can also have multiple inputs:

```
>>> def multiply(number, factor):
...   return number * factor
...
>>> multiply(50, 10)
500
```

# Excercise VI

In this section, I will have a single excercise. Write a method named "fibonnaci", that takes in a number. This method should then generate that many values of the fibonnaci sequence.

The fibonacci sequence starts at 0 and 1, and works by adding them together to get the next number. Example:

0, 1

0 + 1 = 1, so 0, 1, 1

1 + 1 = 2, so 0, 1, 1, 2

1 + 2 = 3, so 0, 1, 1, 2, 3

2 + 3 = 5, so 0, 1, 1, 2, 3, 5

and so on.


# THE REST HAS NOT YET BEEN WRITTEN
