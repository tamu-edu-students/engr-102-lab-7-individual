# ENGR 102 Lab Topic 7 (individual)

## Activities
There are three deliverables for this individual assignment. Please submit the files described below to Gradescope. Check out the [Frequently Asked Questions](#frequently-asked-questions) below. **Please include the individual header in your ~.py files.**

1. [Name Game](#name-game)
2. [Split List](#split-list)
3. [Kaprekar's Constant](#kaprekars-constant)

## Name Game
Write

## Split List
Write

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
