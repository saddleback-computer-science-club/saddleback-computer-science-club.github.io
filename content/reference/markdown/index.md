---
title: 'Markdown Reference'
date: 2023-11-16T18:45:33-08:00
draft: true

description: 'Reference for the markdown specification'
author: 'Matthew Reese'
---

[Official Markdown Specification](markdown-spec)

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

## Bulleted Lists

```markdown
- First Item
- Second Item
- Third Item
```

> - First Item
> - Second Item
> - Third Item

## Code Syntax Highlighting

````markdown
```language
Code goes here
```
````

````markdown
```python
def main():
    print("Hello World!")
```
````

````markdown
```cpp
#include <iostream>

int main() {
    std::cout << "Hello World!" << std::endl;
}
```
````

```c++
#include <iostream>

int main() {
    std::cout << "Hello World!" << std::endl;
}
```

```python
def main():
    print("Hello World!")
```