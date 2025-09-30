# ENGR 102 Lab Topic 7 (individual)

## Activities
There are three deliverables for this individual assignment. Please submit the files described below to Gradescope. Check out the [Frequently Asked Questions](#frequently-asked-questions) below. **Please include the individual header in your ~.py files.**

1. [Name Game](#name-game)
2. [Split List](#split-list)
3. [Kaprekar's Constant](#kaprekars-constant)

## Name Game
This program is meant to help give you practice with string manipulation. [The Name Game](https://en.wikipedia.org/wiki/The_Name_Game) is a rhyming game that creates variations on a person’s name. Using a person’s name, the first syllable is replaced with various sounds in the pattern below.

```
(X), (X), Bo-B(Y)
Banana-Fana Fo-F(Y)
Me Mi Mo-M(Y)
(X)!
```

`X` is the full name and `Y` is the name without the first consonant sound. Write a program named `name_game.py` that reads in a name from the user, then prints the rhyme using the output shown below. For names that begin with a vowel sound, the first syllable is **not** dropped, but is converted to a lowercase letter.

Example output (using input `Niki`):
```
What is your name? Niki
Niki, Niki, Bo-Biki
Banana-Fana Fo-Fiki
Me Mi Mo-Miki
Niki!
```


## Split List
This program is meant to give you practice with lists and looping on them. Write a program named `split_list.py` that takes as input from the user one string of a sequence of integers, with each value separated by a space. Have your program convert the input string to a list of integers, and determine where to split the list so that the sum of the numbers in the left portion is equal to the sum of the numbers in the right portion. If such a split can be made, print the contents of the left and right portions of the list after the split along with their sum. You may **NOT** reorder the numbers; use them in the given order. If the list cannot be split with equal sums, print a message to the screen according to the example below. You may assume the user enters valid input, but it is an arbitrary number of whole numbers.

**Note**: You should use **lists** (and loops) when solving this problem. You may **NOT** use the `sum()` function. You may **NOT** use `sympy` or `numpy`.

Example output (using input `3 1 8 4 3 0 5`):
```
Enter numbers: 3 1 8 4 3 0 5
Left: [3, 1, 8]
Right: [4, 3, 0, 5]
Both sum to 12
```

Example output (using input `8 3 4 6 3 2 9 0 1 8 3 5 8 3 2 6`):
```
Enter numbers: 8 3 4 6 3 2 9 0 1 8 3 5 8 3 2 6
Cannot split evenly
```

## Kaprekar's Constant
Write

## Frequently Asked Questions
1. **How do I convert a string of numbers into a list?** If you use the `list(mystr)` command, it puts each character (including spaces) into it's own element in a list. Try using the `mystr.split()` method instead. See the [string methods example video](https://mediasite.tamu.edu/Mediasite/Play/8a3a9b890cdb456e8e53a3b90d4c43f91d) for an explanation.

2. **Now I have a list of strings. How do I get numbers?** Now that you have a list of strings, you need to convert each element into an int or float. You can't just apply `int()` or `float()` directly to a list; instead loop through the elements and convert each value to the data type you want. If you're still struggling, look out for hints in class on how to do this.

3. **Activity 1 (The Name Game) what do I do if a name starts with 2 consonants?** Your code will need to identify the first vowel in the name, no matter where it is. One suggestion is to examine one by one the letters of the name until you find a vowel. Remember you can check if a character is in a string or list like this:
```
myletter = "a"
if myletter in "abc":  # or use ["a", "b", "c"] for a list
    print("yes")
```
4. **Activity 3 (Kaprekar's constant) how do I sort numbers?** The easy way is to use `mylist.sort()`. You need a list of numbers (or strings), and that one command will sort it for you. Then you can print / concatenate / whatever to put it back into a single int or string. See the [list methods example video](https://mediasite.tamu.edu/Mediasite/Play/5e303a579dab4a769cb7ed9e732f68491d) for an explanation. Here's another suggestion: store each digit in it's own variable. How do you get each digit? `num // 1000` will give you the first digit of a four-digit number. Then you can create an `if-elif-else` block to determine which digit is largest/smallest. You can use string concatenation to put the digits back together: `newnum = str(num1) + str(num2)`

5. **Activity 3 (Kaprekar's constant) how do I not print the `>` at the end again?** Review the FAQ on [Lab Topic 6 (individual)](https://github.com/tamu-edu-students/engr-102-lab-6-individual) for an example.

Have a question you don't see here? Email your instructor!

Based upon Dr. Keyser’s Original<br/>
Revised Summer 2025 SNR
