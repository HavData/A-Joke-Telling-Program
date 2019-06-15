# A-Joke-Telling-Program
This program tells a few jokes to the user and demonstrates more advanced ways to use strings with the print() function. This will demonstrate simple output to the screen.

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

### How the Code Works
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

### Escape Characters
Lines 5 to 8 print the question and answer to the next joke:

```
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
| --------- | ---------------- |
| \\        | Backslash (\)    |
| \'        | Single quote (') |
| \"        | Double quote (") |
| \n        | Newline          |
| \t        | Tab              |

There are a few more escape characters in Python, but these are the characters you will most likely need for creating games.
