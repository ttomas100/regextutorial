# Title (Regex Tutorial)

In this tutorial we can find a quick view of how Regular Expession work, and how extrac information from any text by searchen for matches of a pattern.

## Summary

Regular expressions (regex or regexp) are extremely useful in extracting information from any text by searching for one or more matches of a specific search pattern. 

An example code snippet of regex shows as following:

\b[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}\b

It describes a series of letters, digits, dots, underscores, percentage signs and hyphens, followed by an at sign, followed by another series of letters, digits and hyphens, finally followed by a single dot and two or more letters. In other words: this pattern describes an email address.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
Anchors are characters within the regular expression that allow the user to match strings that begin with or ends with (or both) certain characters. 

^The        matches any string that starts with The 
end$        matches a string that ends with end
^The end$   exact string match (starts and ends with The end)
roar        matches any string that has the text roar in it

### Quantifiers

Quantifiers are characters within the regular expression that specify how many instances a character, group, or character class must be represented in the input to be matched.


abc*        matches a string that has ab followed by zero or more c 
abc+        matches a string that has ab followed by one or more c
abc?        matches a string that has ab followed by zero or one c
abc{2}      matches a string that has ab followed by 2 c
abc{2,}     matches a string that has ab followed by 2 or more c
abc{2,5}    matches a string that has ab followed by 2 up to 5 c
a(bc)*      matches a string that has a followed by zero or more copies of the sequence bc
a(bc){2,5}  matches a string that has a followed by 2 up to 5 copies of the sequence bc

### Grouping Constructs
Grouping unifies a pattern or string so that it is matched in a complete block

a(bc)           parentheses create a capturing group with value bc 
a(?:bc)*        using ?: we disable the capturing group 
a(?<foo>bc)     using ?<foo> we put a name to the group 

### Bracket Expressions
Bracket Expressions are characters enclosed by a bracket `[]` matching any single character within the brackets. 
*note: if the first character within the brackets is a `^` then it signifies any chracter not in the list, and is unspecified whether it matches an encoding error. 


[abc]            matches a string that has either an a or a b or a c -> is the same as a|b|c 
[a-c]            same as previous
[a-fA-F0-9]      a string that represents a single hexadecimal digit, case insensitively 
[0-9]%           a string that has a character from 0 to 9 before a % sign
[^a-zA-Z]        a string that has not a letter from a to z or from A to Z. In this case the ^ is used as negation of the expression 

### Character Classes
Character Classes tells the regex engine to match only one out serveral specific characters, such as digits, words, or whitespace


\d         matches a single character that is a digit 
\w         matches a word character (alphanumeric character plus underscore) 
\s         matches a whitespace character (includes tabs and line breaks)
.          matches any character 

### The OR Operator

R Operators matches on of a choice of regular expressions: if you put the character representing the alternation operator between any two characters in the regular expression, the result matches the union of the strings that those two characters match.


a(b|c)     matches a string that has a followed by b or c (and captures b or c)
a[bc]      same as previous, but without capturing b or c

### Flags
A regex usually comes within this form /abc/, where the search pattern is delimited by two slash characters /. At the end we can specify a flag with these values (we can also combine them each other):

g (global) does not return after the first match, restarting the subsequent searches from the end of the previous match
m (multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string
i (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC)

### Character Escapes
To use a special character as a regular one, prepend it with a backslash: \..

That’s also called “escaping a character”.

alert( "Chapter 5.1".match(/\d\.\d/) ); // 5.1 (match!)
alert( "Chapter 511".match(/\d\.\d/) ); // null (looking for a real dot \.)

Parentheses are also special characters, so if we want them, we should use \(. The example below looks for a string "g()":

alert( "function g()".match(/g\(\)/) ); // "g()"

## Author

Tomas Utreras is a Junior Full Stack Developer, Senior Project-Product Manager with experience handling digital project of new web developments. 



[GitHub Profile](https://github.com/ttomas100)