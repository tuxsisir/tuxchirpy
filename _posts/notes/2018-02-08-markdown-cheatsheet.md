---
title: "Markdown Cheatsheet"
date: 2018-02-08
draft: false
tags: ["markdown", "cheatsheet"]
---


### Basic Syntax

| Markdown Element | Syntax                                             |
| ---------------- | -------------------------------------------------  |
| Heading          | # Heading 1 <br/> ## Heading 2 <br/> ### Heading 3 |
| Bold             | `**bold_text**`                                    |
| Italic           | `***Italic_text***`                                |
| Blockquote       | ` > blockquote `                                   |
| Ordered List     | 1. First <br/> 2. Second <br/> 3. Third            |
| Unordered List   | - First <br/> - Second <br/> - Third               |
| Code             | ``` `code` ```                                     |
| Horizontal Rule  | `---`                                             |
| Image            | `![alt text](image.jpg)`                           |
| Link             | `[tuxsisir](https://www.tuxsisir.com)`             |

### Extended Syntax

#### Table
```markdown
| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |

```

#### Fenced Code Block
```json
{
  "name": "John",
  "age": "Smith"
}
```
#### Footnote

```
This is a footnote sentence. [^1]
[^1]: And, this is footnote.
```

#### Heading ID
```
### My Custom Heading ID {#custom-id}
```
#### Definition List
```
term
: definition
```

#### Strikethrough
```
~~Love yourself.~~
```
~~Love yourself.~~

#### Task Lists
```
- [x] Go to Work
- [ ] Write Code
- [ ] Return home
```
Output:

- [x] Go to Work
- [ ] Write Code
- [ ] Return home

[Further Markdown Reference: https://www.markdownguide.org/cheat-sheet/](https://www.markdownguide.org/cheat-sheet/)

