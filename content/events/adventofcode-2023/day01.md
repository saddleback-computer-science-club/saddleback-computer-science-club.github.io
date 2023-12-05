---
title: 'Day 01'

author: 'Matthew Reese'
summary: 'Day 01 solutions and explanations'
---


The problem for day 1 can be found [here](https://adventofcode.com/2023/day/1). Be sure to read through this thoroughly in order to understand the problem well.

If you would just like to read the code I wrote and figure out how it works yourself, here's a link to my [github repo](https://github.com/Terracom12/advent-of-code/blob/main/2023/day1/solution.cpp), and the code itself at the bottom of the page. Note that the implementations under the Part 1 and Part 2 explanations are slightly modified from the complete program for clarity. This explanation will be the most verbose out of the 25, as I will make very few assumptions on the reader's knowledge.

## Part 1

Each of these problems always involve two steps: parsing, then solving. Since this problem was so simple, I combined these two steps. Below is my implementation for part 1 in C++:

```cpp
int part1(std::vector<std::string> input) {
    int firstDigit, lastDigit, number, sum = 0;

    for(std::string line : input) {
        firstDigit = lastDigit = 0;
        for(char c : line) {
            if(isdigit(c)) {
                lastDigit = c - '0';
            }

            if(!firstDigit) {
                firstDigit = lastDigit;
            }
        }

        number = firstDigit * 10 + lastDigit;
        sum += number;
    }

    return sum;
}
```

Assume that `input` contains strings representing each line of the given input file. To start off, we use a range based for loop to iterate through each line in `input`. If you do not understand how this works, please read [this article](https://www.geeksforgeeks.org/range-based-loop-c/).

Next, since we only care about individual *digits*, one-characters items, we iterate through each of the characters in the current line. Within the body of this loop, two actions are taken:

1) Check if `c` is a digit character (i.e. `'0'` - `'9'`). If so, set `lastDigit = c - '0'`. This will convert the digit into a number, as can be seen by `'0' - '0' = 0`, `'1' - '0' = 1`, `'2' - '0' = 2`, ...
2) If `firstDigit` has not yet been set, assign it to the value of `lastDigit`. This works because it only allows `firstDigit` to be set **once**, to the first instance of a digit found in the line.

After the inner loop finishes, the outer loop sets the number for the current line using simple base-10 arithmetic. Then, that number is added to sum. Finally, after this has been done for every input line, the function returns the sum.

## Part 2

Here is my implementation of part 2. You should note that much of this code is copied directly from [part 1](#part-1), as the problem has only changed slightly. The changes are highlighted, and are the only parts I will be going over.

```cpp {hl_lines=["2-4", 9, 10,"13-19"]}
int part2(std::vector<std::string> input) {
    std::vector<std::string> numToWord = 
        { "one", "two", "three", "four", "five", "six", 
          "seven", "eight", "nine" };
    int firstDigit, lastDigit, number, sum = 0;

    for(const auto& line : input) {
        firstDigit = lastDigit = 0;
        for(int i = 0; i < line.size(); i++) {
            char c = line[i];
            if(isdigit(c)) {
                lastDigit = c - '0';
            } else {
                for(int j = 0; j < numToWord.size(); ++j) {
                    if(line.substr(i, numToWord[j].size()) == numToWord[j]) {
                        lastDigit = j + 1;
                    }
                }
            }

            if(!firstDigit) {
                firstDigit = lastDigit;
            }
        }

        number = firstDigit * 10 + lastDigit;
        sum += number;
    }

    return sum;
}
```

The first thing I did was create a vector for the purpose of converting words to numbers. Part 2 requires that word representations of numbers are found (i.e. "one" - "nine"), and having a data structure to hold all of these possible representations allows for clean-ish code.

Nextly, the inner loop was changed from range based to the more traditional for loop with an iterator variable, `i`. The reason being that the *position* in the current line is needed later to get a substring of the line, in order to check for the word representations of each digit ("one" - "nine").

An `else` clause is added to the `if` statement so that we may check whether the characters at the current position form one of the words in the `numToWord` vector. This check is done by iterating through `numToWord` and comparing each word to a substring of `line` at position `i`. The length of this substring is the same as the length of the current word. If a match is found, the digit is set to the number representation of the word, being `j + 1` (since `numToWord[0] = "one"`, `numToWord[1] = "two"`, and so on).

## Complete Program

`"../../utils.hpp"` is an file I'm using to concisely include standard library headers. You may view it [here](https://github.com/Terracom12/advent-of-code/blob/main/utils.hpp) if you'd like.

{{< remoteCode "https://raw.githubusercontent.com/Terracom12/advent-of-code/main/2023/day1/solution.cpp" >}}

## References

If you do not understand any part of the syntax I used, please consult the resources below. If you find these inadequet and still have questions or any other type of feedback, feel free to message me **@Matt** on discord.

- [Range Based For-Loops](https://en.cppreference.com/w/cpp/language/range-for)
  - [Auto keyword (as a placeholder type specifier)](https://en.cppreference.com/w/cpp/language/auto)
- [Vector Type](https://en.cppreference.com/w/cpp/container/vector)
- [Substring method](https://en.cppreference.com/w/cpp/string/basic_string/substr)