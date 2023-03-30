# Notes on Regular Expressions (RegEx)

## Resource "2.1: Introduction to Regular Expressions - Programming with Text"
Link: https://www.youtube.com/watch?v=7DG3kCDx53c

### About regular expression
- Not exclusive to JavaScript, python, C## etc. Can be used in any text language 
- 

### What is a regular expression?
- Define a search pattern in a body of text
- Literal character match 
- OR a meta-character search

### RegEx Phone Number example
- Define the pattern
    - Searching for 3 numbers followed by dash or dot, then 3 numbers follwed by dash or dot, then 4 numbers followed by dash or dot
    - Also possible to have first 3 numbers in paranthesis
- `\d` = any digit 0-9
- a Phone number first 3 digits would look like `\d\d\d-`
- numbers only example:
    - `\d\d\d-\d\d\d-\d\d\d\d`


## RegEx JavaScript single meta-characters
- `\d` = any digit 0-9
- `.` = any character
- `*` = quanitfier = 0 or more
- `.*` any file that ends in _____.anything
- `\w` = any uppercase A-Z, lowercase a-z, and 0-9
- `\W` = anything that is NOT uppercase A-Z, lowercase a-z, or 0-9
- `\s` = whitespace such as a space or a tab
- `\S` = anything that is NOT whitespace

## RegEx JavaScript QUANTIFIERS
- Quanitifers are meta-characters that tell us HOW MANY of single meta-chacrcter we want
- `*` = 0 or more
- `+` = 1 or more
- `?` = 0 or 1
- `{min,max}` or `{n}` to determine min to max or number of n
- To find ALL 5 LETTER WORDS we would use `\w{5}`
- To find all 7 digit numbers we would use `\d{7}`
- To find a phone number with dashes `\d{3}-\d{3}-\d{4}`
## RegEx JavaScript POSITIONS
- `^` = beginning of line
- `$` = end of line
- `\b` = word boundary. FOR EXAMPLE: to only call 4 letter words use `\b\w{4}\`

## RegEx JavaScript CHARACTER CLASSES
- Character classes exist between square braackets `[]`
- Also functions as an "or"
- `[abc]` find a b or c
- to indicate a literal chacrter use `\`
- Phone number with dash or dots!  `\(?\d{3}[-.)]\d{3}[-.]\d{4}`
- if dash is NOT the first character it is NOT literal, it can mean 0-9 or a-z `[a-z0-9]`
- `[^0-5]` ANYTHING that is not 0-5 when carrot symbol is at the BEGINNING OF the character class. if it's in the middle of the chacracter class it is literal.
- `[abc]` positive character group. `[^abc]` anything but abc

## RegEx Alternation
- `(net|com)` net or come. this is another method of OR

### Email
= `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`


### Random
- When you search `command + f` you have the option to search with regular expression!

### Email notes to self 
- Any number of characters, at least 1 or more. maybe 2 or more?
- followed by an @ symbol
- followed by any number of chacrters
- followed by peiod
- followed by 3 letters `\w{3}`

### Hex Value
= `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

### Email
= `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
= at least one chacracter either a-z or 0-9 
= `/^` at beginning and `$/` at end
= `()` distinguish the difference between sections
= `[]` sections within section

### URL
= `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

### HTML Tag
= `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`