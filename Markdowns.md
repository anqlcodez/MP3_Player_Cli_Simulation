# GitHub Markdown Cheat Sheet

A quick reference for the Markdown syntax GitHub uses to render README.md files and other .md documents. Markdown is just plain text with symbols that tell GitHub how to format it

---

### Headings
# Title
## Subtitle
### Heading 1
#### Heading 2

### Bold, Italic, and combinations
**bold -	Two asterisks on each side**

*italic -	One asterisk on each side*

***bold italic -	Three asterisks on each side***

~~strikethrough	- Two tildes on each side~~ (squiggly lines ~)

### Bullet Points
- Item one
* Item two
+ Item three
  - Indented sub-item (tab before the dash)
 
### Horizontal Line (divider)

---

Three (or more) dashes on their own line creates a horizontal divider — useful for separating sections visually, like the ones in this document.

### Number list
1. First step
2. Second step
3. Third step

### Checklist
- [ ] Not done yet
- [x] Done

### Code
`code`	code	Inline code — a single command, variable, or filename
```
code block
```

### Links
[link text](https://example.com)	Clickable link

![alt text](image-url-or-path.png)	Embedded image

### Table
| Column 1 | 
|---|
| Row 1, Col 1 |

| Column 1 | Column 2 |
|---|---|
| Row 1, Col 1 | Row 1, Col 2 |
| Row 2, Col 1 | Row 2, Col 2 |


The row of |---|---| right after the header is what tells GitHub "this is a table" it must be there even though it doesn't display any text itself.

###Blockquotes
> This is a quote or callout note.
