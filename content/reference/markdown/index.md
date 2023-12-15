---
title: 'Markdown Reference'
date: 2023-11-16T18:45:33-08:00
draft: true

description: 'Reference for the markdown specification'
author: 'Matthew Reese'
---

Here are examples of the basic syntax in code blocks, with the rendered versions following in quoted blocks.

## Headers

```markdown
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

> # H1
>
> ## H2
>
> ### H3
>
> #### H4
>
> ##### H5
>
> ###### H6

## Text Emphasis

### Bold

```markdown
**emboldened**
```

### Italic

```markdown
*italic*
```

### Bold and Italic

```markdown
***both***
```

> **emboldened**
>
> *italic*
>
> ***both***

## Paragraphs

Text will always be displayed in one paragraph unless it is separated by **two** newlines from previous content.

```markdown
This is paragraph 1.
This is also paragraph 1.

...And paragraph 2 at last.
```

> This is paragraph 1.
> This is also paragraph 1.
>
> ...And paragraph 2 at last.

## Links

```markdown
[link text](#links)

[wiki](https://wikipedia.org)
```

> [link text](#links)
>
> [wiki](https://wikipedia.org)

## Images

```markdown
![alt image text](example.jpg)
```

> ![alt image text](example.jpg)

## Code

### Blocked Code

````text
```language
Code goes here
```
````

````text
```python
def main():
    print("Hello World!")
```
````

````text
```cpp
#include <iostream>

int main() {
    std::cout << "Hello World!" << std::endl;
}
```
````

>    ```c++
>    #include <iostream>
>
>    int main() {
>        std::cout << "Hello World!" << std::endl;
>    }
>    ```
>
>  ```python
>  def main():
>    print("Hello World!")
>  ```

### Inline Code

```markdown
The variable `foo` is of type `Integer`.
```

> The variable `foo` is of type `Integer`.

## Miscellaneous

### Horizontal Rule

```markdown
Text
___
More text
```

> Text
> ___
> More Text

### Bulleted Lists

```markdown
- Fizz
- Buzz
- FizzBuzz
```

> - Fizz
> - Buzz
> - FizzBuzz

### Numbered Lists

```markdown
1. First Item
2. Second Item
3. Third Item
```

> 1. First Item
> 2. Second Item
> 3. Third Item

## External References

- [Official Markdown Specification](https://commonmark.org/)
- [Markdown Quick Reference](https://commonmark.org/help/)
