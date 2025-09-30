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
`6174` is known as [Kaprekar's Constant](https://en.wikipedia.org/wiki/6174_(number)) after the Indian mathematician D. R. Kaprekar. This number can be obtained using Kaprekar’s routine:

1. Take any four-digit number that has at least two different digits (add leading zeros to numbers with fewer than four digits)
2. Sort the digits in descending and then in ascending order to get two four-digit numbers, adding leading zeros if necessary
3. Subtract the smaller number from the bigger number to get a new four-digit number
4. Go back to step 2 and repeat

Kaprekar's routine will always reach its fixed point, `6174`, in at most 8 iterations. Once `6174` is reached, the process will continue to yield `7641 – 1467 = 6174`.

For example, choose `3524`:<br/>
5432 – 2345 = 3087<br/>
8730 – 0378 = 8352<br/>
8532 – 2358 = `6174`

For example, choose `137` (add a leading zero):<br/>
7310 – 0137 = 7173<br/>
7731 – 1377 = 6354<br/>
6543 – 3456 = 3087<br/>
8730 – 0378 = 8352<br/>
8532 – 2358 = `6174`

The only four-digit numbers for which Kaprekar's routine does not reach `6174` are repdigits (numbers where all digits are the same, such as `1111`) which give `0000` after a single iteration. All other four-digit numbers eventually reach `6174`, as long as leading zeros are used to keep the number of digits at four.

Write a program named `kaprekars_constant.py` that takes in an integer from the user between `0` and `9999` and implements Kaprekar's routine. Have your program output the sequence of numbers to reach `6174` and the number of iterations to get there. Format your output as shown below.

Example output (using input `2029`):
```
Enter a four-digit integer: 2029
2029 > 8991 > 8082 > 8532 > 6174
2029 reaches 6174 via Kaprekar's routine in 4 iterations
```

Hints: 
- Consider converting numbers to strings for sorting, and back to numbers for calculating
- Pad the number with 0s when it has fewer than four digits (remember string concatenation?)
- The `list()`, `<listname>.sort()`, and `<string>.join()` methods may be helpful


### Kaprekar's Constant Challenge (optional 2 bonus points)
Modify your program from Activity 3 to compute the sum of the number of iterations required to reach `6174` (or `0000`) using Kaprekar's routine for all four-digit numbers, from `0000` to `9999`. Name your file `kaprekars_challenge.py`. If your program calculates the total number of iterations correctly, you will receive 2 bonus points on this assignment.

Example output:
```
Kaprekar's routine takes ????? total iterations for all four-digit numbers
```


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
