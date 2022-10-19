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

A general rule is thar a letter that is explicitly described will be matched unless it is a special character or token or modified by a token. In an URL, the http cannot be anything else (htrp or gttp, etc) in order to match.

### Quantifiers
The question mark is used as a quantifier several times in this RegEx. The ? quantifier translates that there can be either 0 or 1 of the preceding item or group. In the first instance ``` https? ``` , the ? means that the s is optional but cannot occur more than once in this group of characters. Ergo, it can be http or https. In the second instance the ? appears after a parenthesis. ``` (https?:\/\/)? ``` This means the entire group is optional. 

For example it could be either http://www.hotmail.com, https://www.hotmail.com or www.hotmail.com. But not httpss... or http://http://... because the ? quantifier specifies only 0 or 1 instance can be matched and no more. Oddly the gist RegEx at work behind the scenes of this Markdown Document is getting a little confused, lol.

Another quantifier used in this RegEx is the curly braces. They are used to specify the length of the preceeding segment. ``` ([a-z\.]{2,6}) ``` refers to the domain suffix and limits it to between 2 and 6 characters long. Think .com .net or .ca or .live

### OR Operator
Obviously Or operators are an important part of any system of logic. In RegEx, the | pipe is the or operator and is means that items immediately to the left or right are interchangeable. for example 3|three means either 3 or the number written "three" are considered a match 

### Character Classes
Classes make things a little easier because they can describe a group of related characters such as a word or just numbers. In this RegEx a few are used. \d matches any digit. \w mathces any word. They can get quite specific as well. Hyphens are used here to describe everything in between. a-z means abcdefghijklmnopqrstuvwxyz. This could also be more specific 1-3 means 1,2 or 3 only. 

The class is further desribed by the [] brackets which means all if its contents are may be included. Such as in or RegEx ``` [\da-z\.-] ``` means any digit or alpha character a-z . (periods) and - (dashes) can be matched. So, hello, hello-dolly, hell00, hell.00 and so on would all match. However anything else not described with in the bracket would fail to match, such as "hel@lo"...

### Flags

A flag is an optional parameter to a regex that modifies its behavior of searching. A common one is the i flag which ignores casing. for example a is considered the same as A.

https://www.codeguage.com/courses/regexp/flags

### Grouping and Capturing
The parentheses are used to demark substrings within the RegEx. Many are use and described in the context above

### Bracket Expressions
[] Brackets are used to group item, essentially form a class as descrided in the class section above. Every thing within the brackets is interchangable [a-z] means a, ab, abc, abcde and so forth are all matches.
### Greedy and Lazy Match

A greedy match, essential means that the algorithm will search for as many matches as possible by searchin the entire string. A lazy match with search for the smallest number of occurrences. This can lead to different results based on the context. For more information on this, visit this website. https://javascript.info/regexp-greedy-and-lazy

### Boundaries
\b amd \B are common uses of boundaries in RegEx. In the context of words \b can be either on the left or right of the substring describing where the word ends. \bice would find icey but not nice because the boundary is on the left and vice versa with ice\b. The capital \B tells the RegEx to ignore the boundary. For more info, visit this website. https://www.rexegg.com/regex-boundaries.html#anchors  

### Back-references
Back-references are used to reference a previously defined group. There are none in this RegEx however, for more information, visit this website. https://javascript.info/regexp-backreferences 


### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)

## Works Cited

https://regexr.com/

various google searches...
