# Regex Tutorial

The purpose of this Regex (Regular Expression) tutorial is to provide a more comprehensive guide for developers to learn and understand the concepts of Regular Expressions in programming languages like JavaScript. Regex is a powerful tool that can help developers to search, match, and manipulate text strings efficiently. By learning how to use Regex, developers can improve their coding skills and make their code more efficient and effective. This tutorial aims to provide a clear understanding of a specific Regex string and its application in JavaScript.

## Summary

In this tutorial we will be look at this sepcific Regex: 

Matching a Hex Color Value – /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/

This regular expression matches a hex color value in the form of a string that starts with an optional # symbol, followed by either a six-digit or three-digit hexadecimal value consisting of the characters [a-f0-9]. The entire string must match the pattern, hence the use of the start and end anchor characters ^ and \$.


## Table of Contents
- [What are HEX values](#what-are-hex-values)
- [Regex Components](#regex-components)
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
- [Further Reading about Regex](#further-reading-about-regex)
- [About the Author](#about-the-author)

## What are HEX values?

Hex color values are a way to represent colors in digital media, including web design and image editing software. The term "hex" comes from the fact that the values are represented in hexadecimal format, which is a base-16 numbering system that uses sixteen distinct symbols: 0-9 and A-F (where A-F represent the decimal values 10-15).

In a hex color value, colors are represented by a combination of red, green, and blue (RGB) values. Each RGB value is represented by a two-digit hex number, ranging from 00 to FF. The first two digits represent the red value, the next two digits represent the green value, and the last two digits represent the blue value.

For example, the hex color value #FF0000 represents the color red, because the red value is set to the maximum value of FF (equivalent to decimal value 255), while the green and blue values are set to 0. Similarly, the hex color value #00FF00 represents the color green, with the green value set to the maximum value of FF, and the red and blue values set to 0.

In addition to the six-digit format, there is also a three-digit format for hex color values, which represents each RGB value with a single hex digit instead of two. For example, the hex color value #F00 is equivalent to #FF0000, since the F represents the maximum value of FF for the red value, while the other digits are set to 0.

Hex color values are widely used in web design, where they can be specified in CSS stylesheets or inline styles to set the background color, text color, border color, and other visual properties of a webpage. They are also used in image editing software, where they can be used to specify the color of individual pixels or entire sections of an image.


## Regex Components
Here's a breakdown of the individual components in the given regular expression:

    In JavaScript and many other programming languages, forward slashes (/) are used to delimit regular expressions. The forward slashes indicate the beginning and end of a regular expression pattern, and any characters between them are interpreted as a regular expression. For example, the regular expression /abc/ matches any string that contains the characters "abc" in sequence.

    ^: The caret symbol (^) is an anchor that matches the beginning of a line/string.

    #?: This part of the expression matches an optional hash symbol (#). The question mark (?) makes the preceding hash symbol optional.

    ([a-f0-9]{6}|[a-f0-9]{3}): This is the core of the expression, which matches a six-digit or three-digit hexadecimal color value. The [a-f0-9] character class matches any letter between a and f (case-insensitive) and any digit between 0 and 9. The {6} and {3} quantifiers specify the length of the color value.

    \$: The dollar symbol (\$) is an anchor that matches the end of a line/string.

This regular expression matches a hex color value in the form of a string that starts with an optional # symbol, followed by either a six-digit or three-digit hexadecimal value consisting of the characters [a-f0-9]. The entire string must match the pattern, hence the use of the start and end anchor characters ^ and \$.


### Anchors

The anchor used in the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/ is a combination of two anchors: the caret symbol (^) and the dollar symbol (\$).

The caret symbol (^) is a start of line anchor that matches the beginning of a string. When used in a regular expression, it indicates that the pattern being matched must start at the beginning of the string. In the given regular expression, ^ is placed at the very beginning of the pattern, ensuring that the string being matched starts with the specified pattern.

The dollar symbol (\$) is an end of line anchor that matches the end of a string. When used in a regular expression, it indicates that the pattern being matched must end at the end of the string. In the given regular expression, \$ is placed at the very end of the pattern, ensuring that the string being matched ends with the specified pattern.

Together, these anchors ensure that the entire string being matched must conform to the specified pattern, and that no additional characters are allowed before or after the pattern. This is useful in cases where we want to match a specific pattern in a string and don't want any other characters to interfere with the match.

### Quantifiers

In the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/, there are two quantifiers used: {6} and {3}.

The {6} quantifier indicates that the preceding character or character set ([a-f0-9] in this case) must be repeated exactly six times in order to match. This means that the regular expression will match any string that contains a sequence of six hexadecimal characters after the optional # symbol.

The {3} quantifier works in a similar way, indicating that the preceding character or character set must be repeated exactly three times in order to match. This means that the regular expression will match any string that contains a sequence of three hexadecimal characters after the optional # symbol.

#### OR Operator

The | character between the two quantified expressions is an alternation or "OR" operator, which allows either of the expressions to match. So, the regular expression will match either a six-digit or a three-digit hexadecimal value.

Together, the quantifiers and alternation provide flexibility to the pattern matching by allowing for different length of the hexadecimal color values.

### Character Classes

In the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/, the character class [a-f0-9] is used to match hexadecimal digits. Here's a breakdown of what that character class means:

    [a-f0-9]: This is a character class that matches any character that is a lowercase letter between a and f, an uppercase letter between A and F, or a digit between 0 and 9. This character class is case-insensitive, meaning that it will match both uppercase and lowercase letters.

The character class is used inside the quantified expressions {6} and {3} to match exactly six or three characters of the given class, respectively. This means that the regular expression will match any string that contains a sequence of six or three hexadecimal characters (depending on the case), after the optional # symbol.

Overall, the character class [a-f0-9] provides a concise way to match hexadecimal digits in the regular expression.

### Flags

In the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/, no flags are used. Flags are optional parameters that can be added to a regular expression to modify its behavior. Here are some commonly used flags in JavaScript:

    g (global): This flag allows a regular expression to match multiple occurrences of a pattern in a string, rather than just the first occurrence. For example, /abc/g would match all occurrences of "abc" in a string, rather than just the first occurrence.

    i (ignore case): This flag makes the regular expression case-insensitive, meaning that it will match both uppercase and lowercase letters. For example, /abc/i would match "abc", "AbC", "ABC", and so on.

    m (multiline): This flag changes the behavior of the ^ and \$ anchors to match the beginning and end of each line in a multiline string, rather than just the beginning and end of the entire string.

Since the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/ is not using any flags, it will match the pattern at the beginning and end of the string only once. However, if the g flag were added to the expression, it would match all occurrences of the pattern in the string. If the i flag were added, it would make the expression case-insensitive, allowing it to match both uppercase and lowercase hexadecimal characters. The m flag would have no effect on this particular regular expression since it doesn't involve multiline matching.

### Grouping and Capturing

In the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/, grouping and capturing are used to capture the matched hexadecimal values.

The parentheses ( ) in the regular expression create a capture group around the two alternatives, separated by the alternation operator |. This means that the regular expression will capture either the six-digit or three-digit hexadecimal value that matches the pattern.

Here's a breakdown of how the grouping and capturing works:

    ([a-f0-9]{6}|[a-f0-9]{3}): This is the capture group that matches either a sequence of six or three hexadecimal digits, depending on the input string. The alternation operator | allows either of the expressions to match, while the quantifiers {6} and {3} specify the length of the matched string.

When a string matches the regular expression, the entire matched string is captured by the regular expression engine. However, since we've defined a capture group using parentheses, the engine also stores the matched hexadecimal value inside that capture group. This allows us to access the matched value separately from the full matched string.

To access the captured hexadecimal value in JavaScript, we can use the match() method on a string with the regular expression as its argument. This method returns an array of all the matches, including any capture groups. In this case, the first item in the array will be the full matched string, while the second item will be the captured hexadecimal value. For example:

```
const str = "#3f1";
const regex = /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/;
const match = str.match(regex);
console.log(match[0]); // "#3f1"
console.log(match[1]); // "3f1"
```

Here, we're capturing the three-digit hexadecimal value 3f1 from the input string #3f1 and storing it in the second item of the match array. We can access the full matched string using the first item of the array.

### Bracket Expressions

In the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/, the bracket expression [a-f0-9] is used to define a character class.

A character class is a way to specify a set of characters that can match a single character in a regular expression. In this case, the character class matches any lowercase letter between a and f or any digit between 0 and 9. The [a-f0-9] character class is used twice in the regular expression, once for the {6} quantifier and once for the {3} quantifier.

The {6} and {3} quantifiers are used to specify that the character class should match either six or three characters, respectively. This is because hex color values can be represented by either six or three characters. If the color value is represented by six characters, each color component (red, green, and blue) is represented by two characters. If the value is represented by three characters, each color component is represented by a single character, which is then doubled to represent the full value.

So, in summary, the [a-f0-9] character class is used to match a set of characters (lowercase letters a-f and digits 0-9), and the {6} and {3} quantifiers are used to specify that the character class should match either six or three characters, respectively. This allows the regular expression to match both six-digit and three-digit hex color values.


### Greedy and Lazy Match

In the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/, the quantifiers used for the character class [a-f0-9] are greedy by default. This means that they will match as many characters as possible while still allowing the overall regular expression to match.

For example, if the input string is "#abcdef", the greedy quantifiers will match all six characters in the character class [a-f0-9], even though the regular expression only requires six characters if the "#" symbol is present. Similarly, if the input string is "#abc", the greedy quantifiers will match all three characters in the character class, even though the regular expression only requires three characters if the "#" symbol is present.

Greedy matching can sometimes result in unexpected behavior, especially when used in combination with other regular expression components like anchors or other quantifiers. In cases where greedy matching is not desired, it is possible to use lazy quantifiers instead.

Lazy quantifiers are denoted by appending a "?" to the end of a regular expression quantifier. For example, the greedy {6} quantifier can be replaced with a lazy {6} quantifier, denoted as {6}?. This will match as few characters as possible while still allowing the overall regular expression to match.

In the case of the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/, however, using a lazy quantifier is not necessary, as the input string will always contain either six or three characters in the character class [a-f0-9], and the "#" symbol is optional. Therefore, the default greedy quantifiers used in the regular expression are appropriate and will match the desired patterns in the input string.

### Boundaries

In the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/, there is one boundary used: the beginning and end of the string. These boundaries are implicit and are denoted by the caret (^) and dollar sign (\$) characters respectively.

The caret character (^) is an anchor that matches the beginning of the string, while the dollar sign (\$) is an anchor that matches the end of the string. When both anchors are used in combination, as in this regular expression, they indicate that the entire string must match the pattern defined by the regular expression.

In this case, the regular expression requires that the input string begin with an optional "#" character, followed by either six or three hexadecimal digits. If any other characters are present in the input string, the regular expression will not match.

For example, the input string "#123abc" would match the regular expression, because it begins with an optional "#" character, followed by six hexadecimal digits. However, the input string "123abc" would not match the regular expression, because it does not begin with an optional "#" character.

Using boundaries in regular expressions is important because it allows you to precisely define where a match should begin and end, rather than just matching a pattern within a larger string. This can be especially useful when working with complex or ambiguous data formats, where it is important to ensure that only valid patterns are matched.

### Back-references

There are no back-references used in the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/.

Back-references are a feature of regular expressions that allow you to refer back to a previously matched group within the pattern. They are typically used in situations where you want to match a pattern that contains a repeated subpattern.

### Look-ahead and Look-behind

The regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})\$/ does not use look-ahead or look-behind assertions.

Look-ahead and look-behind assertions are advanced regular expression features that allow you to match patterns only if they are followed by or preceded by certain other patterns, respectively.

## Further Reading about Regex

Here are some links to further detailed reading on Regular Expressions (Regex) in JavaScript:

1. MDN Web Docs: Regular Expressions: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions
2. Regular Expressions in JavaScript: https://www.w3schools.com/jsref/jsref_obj_regexp.asp
3. Regular Expressions in JavaScript Demystified: https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285
4. Learn Regular Expressions - JavaScript: https://regexone.com/lesson/javascript
5. Mastering Regular Expressions, Third Edition: https://www.oreilly.com/library/view/mastering-regular-expressions/9780596528126/

These resources cover a range of topics, from basic to advanced, and provide practical examples to help you learn and understand Regex in JavaScript.

## About the Author

My name is Jacob and I am  fullstack web developer familiar with the LAMP and MERN stack.
* Portfolio Page: http://jeffries.info
* Github Page: https://github.com/Jacob-Jeffries
