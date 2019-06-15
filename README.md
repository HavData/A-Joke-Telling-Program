# A-Joke-Telling-Program
This is a tutorial that demonstrates some advanced ways to use strings with the print() function in Python. This short program tells a few jokes to the user, and shows simple output to the screen. 

## Sample Run of Jokes
Here's what the user sees when they run the Jokes program:

```
What do you get when you cross a snowman with a vampire?
Frostbite!

What do dentists call an astronaut's cavity?
A black hole!

Knock knock.
Who's there?
Interrupting cow.
Interrupting cow wh-MOO!
```

## Source Code for Jokes

```python
print('What do you get when you cross a snowman with a vampire?')
input()
print('Frostbite!')
print()
print('What do dentists call an astronaut\'s cavity?')
input()
print('A black hole!')
print()
print('Knock knock.')
input()
print("Who's there?")
input()
print('Interrupting cow.')
input()
print('Interrupting cow wh', end='')
print('-MOO!')
```

## How the Code Works
Let's start by looking at the first four lines of code:

```python
print('What do you get when you cross a snowman with a vampire?')
input()
print('Frostbite!')
print()
```

Lines 1 and 3 use the `print()` function call to ask and give the answer to the first joke. You don’t want the user to immediately read the joke’s punchline, so there’s a call to the `input()` function after the first `print()` instance. The user will read the joke, press ENTER, and then read the punchline.

The user can still type in a string and press ENTER, but this returned string isn’t being stored in any variable. The program will just forget about it and move to the next line of code.

The last `print()` function call doesn’t have a string argument. This tells the program to just print a blank line. Blank lines are useful to keep the text from looking crowded.

## Escape Characters
Lines 5 to 8 print the question and answer to the next joke:

```python
print('What do dentists call an astronaut\'s cavity?')
input()
print('A black hole!')
print()
```

On line 5, there’s a backslash right before the single quote: `\'`. (Note that \ is a backslash, and / is a forward slash.) This backslash tells you that the letter right after it is an escape character. An escape character lets you print special characters that are difficult or impossible to enter into the source code, such as the single quote in a string value that begins and ends with single quotes.

In this case, if we didn’t include the backslash, the single quote in `astronaut\'s` would be interpreted as the end of the string. But this quote needs to be part of the string. The escaped single quote tells Python that it should include the single quote in the string.

But what if you actually want to display a backslash?

Switch from your *jokes.py* program to the interactive shell and enter this `print()` statement:

```
>>> print('They flew away in a green\teal helicopter.')
They flew away in a green\teal helicopter.
```

This instruction didn’t print a backslash because the `t` in `teal` was interpreted as an escape character since it came after a backslash. The `\t` simulates pressing `TAB` on your keyboard.

This line will give you the correct output:

```
>>> print('They flew away in a green\\teal helicopter.')
They flew away in a green\teal helicopter.
```

This way the `\\` is a backslash character, and there is no `\t` to interpret as `TAB`.

The following table is a list of some escape characters in Python, including `\n`, which is the newline escape character that you have used before.

| Escape Character   | Printed Character |
| :---------: | :---------------- |
| \\        | Backslash (\)    |
| \'        | Single quote (') |
| \"        | Double quote (") |
| \n        | Newline          |
| \t        | Tab              |

There are a few more escape characters in Python, but these are the characters you will most likely need for creating games.

## Single and Double Quotes

While we’re still in the interactive shell, let’s take a closer look at quotes. Strings don’t always have to be between single quotes in Python. You can also put them between double quotes. These two lines print the same thing:

```
>>> print('Hello world')
Hello world
>>> print("Hello world")
Hello world
```

But you cannot mix quotes. This line will give you an error because it uses both quote types at once:

```
>>> print('Hello world")
SyntaxError: EOL while scanning single-quoted string
```

I like to use single quotes so I don’t have to hold down `SHIFT` to type them. They’re easier to type, and Python doesn’t care either way.

Also, note that just as you need the `\'` to have a single quote in a string surrounded by single quotes, you need the `\"` to have a double quote in a string surrounded by double quotes. Look at this example:

```
>>> print('I asked to borrow Abe\'s car for a week. He said, "Sure."')
I asked to borrow Abe's car for a week. He said, "Sure."
```

You use single quotes to surround the string, so you need to add a backslash before the single quote in `Abe\'s`. But the double quotes in `"Sure."` don’t need backslashes. The Python interpreter is smart enough to know that if a string starts with one type of quote, the other type of quote doesn’t mean the string is ending.

Now check out another example:

```
>>> print("She said, \"I can't believe you let them borrow your car.\"")
She said, "I can't believe you let them borrow your car."
```

The string is surrounded in double quotes, so you need to add backslashes for all of the double quotes within the string. You don’t need to escape the single quote in can't.

To summarize, in the single-quote strings, you don’t need to escape double quotes but do need to escape single quotes, and in the double-quote strings, you don’t need to escape single quotes but do need to escape double quotes.

## The print() Function’s end Keyword Parameter

Now let’s go back to jokes.py and take a look at the following lines:

```python
print('Knock knock.')
input()
print("Who's there?")
input()
print('Interrupting cow.')
input()
print('Interrupting cow wh', end='')
print('-MOO!')
```

Did you notice the second argument in line 15’s `print()` function? Normally, `print()` adds a newline character to the end of the string it prints. This is why a blank `print()` function will just print a newline. But `print()` can optionally have a second parameter: end.

Remember that an argument is the value passed in a function call. The blank string passed to `print()` is called a `keyword argument`. The `end` in `end=''` is called a keyword parameter. To pass a keyword argument to this keyword parameter, you must type `end=` before it.

When we run this section of code, the output is

```
Knock knock.
Who's there?
Interrupting cow.
Interrupting cow wh-MOO!
```

Because we passed a blank string to the `end` parameter, the `print()` function will add a blank string instead of adding a newline. This is why `'-MOO!'` appears next to the previous line, instead of on its own line. There was no newline after the `'Interrupting cow wh'` string was printed.

## Summary

This example explores the different ways you can use the print() function. Escape characters are used for characters that are difficult to type into the code with the keyboard. If you want to use special characters in a string, you must use a backslash escape character, `\`, followed by another letter for the special character. For example, `\n` would be a newline. If your special character is a backslash itself, you use `\\`.

The `print()` function automatically appends a newline character to the end of a string. Most of the time, this is a helpful shortcut. But sometimes you don’t want a newline character. To change this, you can pass a blank string as the keyword argument for `print()`’s end keyword parameter. For example, to print spam to the screen without a newline character, you would call `print('spam', end='')`.
