# Understanding the email string regular expression:  A brief tutorial

The wonderful thing about RegEXs, is RegExs are wonderful things! Regular expressions are often used to enforce data validation in nearly any application imaginable. First developed in the early days of computing, they exist in nearly all coding languages often using very similar syntax. Regular expressions have probably improved your life in more ways than you realize. Not just through data validations (think email/password verification) but through common search and find features in many apps. The patterns can be strictly or loosely defined based on the desired purpose.

## Summary

This tutorial breaks down each component of a simple URL (Uniform Resource Locator) regular expression while breifly introducing each tool in the RegEx toolbox. Below is the exact syntax of the RegEx we will examine:

```
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```

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
```
/^ ... $/
```
The caret ^ and the dollar sign $ taken from the beginning and the end of the RegEx are anchors. Anchors belong to the family of regex tokens that don't match any characters, but that assert something about the string or the matching process. The ^ and $ anchors describe the beginning and the end of the expression. Implied above, is the principle that most of the characters describe which characters are to be matched.

A quick note about tokens. Tokens are use to describe the structure of the RegEx. There are many tokens in RegEx such as the \ backslash. The backslash is often used to tell the RegEx not to ignore the succeeding token and to actually try to match it. For example the / forward slash is used to mark the boundaries of the RegEx in JS. Because / forward slashes appear often in URLs the back slash has to be employed to tell the RegEx to match or else it might think it is the end of the line.  

### Quantifiers
The question mark is used as a quantifier several times in this RegEx. The ? quantifier translates that there can be either 0 or 1 of the preceding item or group. In the first instance ``` https? ``` , the ? means that the s is optional but cannot occur more than once in this group of characters. Ergo, it can be http or https. In the second instance the ? appears after a parenthesis. ``` (https?:\/\/)? ``` This means the entire group is optional. 

For example it could be either http://www.hotmail.com, https://www.hotmail.com or www.hotmail.com. But not httpss... or http://http://... because the ? quantifier specifies only 0 or 1 instance can be matched and no more.

### OR Operator


### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
