# Regular Expression Tutorial

Introductory paragraph (replace this with your text)

## Summary

This regex tutorial will give you basic knowledge on how to use regular expressions.  We will look at making sure an email address is formatted the way an email address should be.
The regular expression below is validating email addresses.

/^[a-zA-Z0-9_\-\.]+@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$/
It is broken down below:

- ^ asserts position at start of a line
- '+' matches the previous token between one and unlimited times, as many times as possible, giving back as needed (greedy)
- a-z matches a single character in the range between a and z (case sensitive)
- A-Z matches a single character in the range between A and Z (case sensitive)
- 0-9 matches a single character in the range between 0 and 9 (case sensitive)
- _ matches the character _ literally (case sensitive)
- '\-' matches the character - literally (case sensitive)
- '\.' matches the character . literally (case sensitive)
- @ matches the character @ literally (case sensitive)

There are also two capturing groups. 


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
Anchors match a postion in the string. For example if the string were 'RegularExpression2022@gmail.com' then /^R/ would match the beginning of the string and /m/$ would match the end of the string.

### Quantifiers
Quantifiers match a number of instances of a character, group, or character class in a string. For example, /\d\d\d\d\/ would be looking for 4 digits in a row, but /\d{4}/ does the exact samething. You can think of this as a shorthand notation. So if the string were still 'RegularExpression2022@gmail.com' and you wanted to do a string match for /\d{4}/ then it would return 2022.

### OR Operator
The OR operator allows you to use or logic when searching the string. If you were looking for 'RegularExpression2022@gmail.com' OR 'RegularExpression@gmail.com' then you could say {RegularExpression2022@gmail.com | RegularExpression@gmail.com}

### Character Classes
This tells the regex engine to only match one of several specified characters. For example, if you wanted to match a name that has two possible spellings. You could do R[ie]kayla and that would match Rikayla or Rekayla. 

### Flags
There are 6 flags that can affect searches:
i - search is not case sensitive 'A' and 'a' will match
g - this allows all matches to be returned, not just the first one found
m - Multiline mode only affects ^ and &. It will match not only at the beginning and the end of the string, but also at start/end of line.
s - enables dotall mode which allows a dot '.' to match newline characters.
u - enables full unicode support
y - sticky mode which searches at the exact postion in the string

these flags would go after your expression such as /\d{4}/gmi

### Grouping and Capturing
Using parentheses you can group part of the expression to apply a quantifier to the entire group. For example Reg(ular)ex(pression) would return Regularexpression or regex.

### Bracket Expressions
Square brackets define character classes. See this section above. 

### Greedy and Lazy Match
By default, greedy mode is enabled for matching. THis is when quantifiers try to match as many as possible and return the largest matches. Lazy mode the quaniifiers match their preceding elements as few as possible and return the smallest matches. 

### Boundaries
the word boundar '\b' matches positions where you may want one side a word, digit, or character, and the otherside would be a string or special character.

### Back-references
Uses the same text that was previously matched by a capturing group to match new text. An example may look something like:  ([a-c])x\1x\1 which would match axaxax, bxbxb, and cxcxcx.

### Look-ahead and Look-behind
Finds matches to a pattern that are followed or preceded by another pattern. This is also referred to as "lookaround". 

## Author

Rikayla Johnson
Email: Rikaylaj@gmail.com
Repo:https://github.com/RikRox/RegexTutorial
Gist Deployed:  
