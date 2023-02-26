# Regex Tutorial for Matching Emails





## Table of Contents

1. [Introductory Paragraph](https://github.com/gato365/gato365-regex#Introductory-Paragraph)
2. [Summary](https://github.com/gato365/gato365-regex#Summary)
3. [You say you want emails, huh????](https://github.com/gato365/gato365-regex#You-say-you-want-emails-huh)
   1. [The Breakdown of Process](https://github.com/gato365/gato365-regex#Part-1:-The-Breakdown-of-Process)
   2. [Text of solution](https://github.com/gato365/gato365-regex#Part-2:-Text-of-solution)
   3. [Connectors](https://github.com/gato365/gato365-regex#Part-3:-Connectors)
   4. [Putting everything together](https://github.com/gato365/gato365-regex#Part-4:-Putting-everything-together)
4. [Conclusion](https://github.com/gato365/gato365-regex#Conclusion)
5. [About Author](https://github.com/gato365/gato365-regex#About-Author)


-----------
## Introductory Paragraph

Are you interested in getting your hands dirty with regular expressions? Do you want to learn how to match emails? If so, this post is for you. This post provides a solution to creating a regular expression to match emails, which consists of three parts. The first part explains that the username, the '@' symbol, the company name, the '.' symbol, and a uniform resource locator can all contain letters, numbers, periods, underscores, and dashes. The second part explains the use of the escape key for the period and that the '@' symbol does not need it. The third part provides the final code, which includes using the forward slash, parentheses, plus sign, and "gi" at the end of the expression.

## Summary
This post provides a solution to creating a regular expression to match emails, which consists of three parts. The first part explains that the user name, the '@' symbol, the company name, the '.' symbol and a uniform resource locator can all contain letters, numbers, periods, underscores, and dashes. The second part explains the use of the escape key for the period and that the '@' symbol does not need it. The third part provides the final code, which includes using the forward slash, parentheses, plus sign, and "gi" at the end of the expression.



-----------

## You say you want emails huh
You want to get emails from a potential client’s website. It would be best if you addressed of the following questions:

1. What is the format of the website?
2. What is the general format of an email?
3. How many people’s emails are you trying to extract?
4. What other types of information are you looking for? (i.e., name, position, phone number)

This post will primarily focus on question 2., however, when using regex (regular expression), you might as well know these other parameters so that you are not redoing work.



-----------

### Part 1: The Breakdown of Process

We know that emails are strings that have 3 pieces of information in the following order

1. username  **then**
2. the '@' symbol **then**
3. name of the company **then**
4. the '.' symbol **then**
5. a uniform resource locator (i.e. com, edu, or org)

The following **sections** is a breakdown of code that will be used to match emails:

#### Section A: Letters, numbers, periods, underscores, and dashes

a-zA-Z0-9._- : denotes any letter (upper and/or lower) and/or number as well as periods '.', underscore '_' or dash '-'

#### Section B: The '@' symbol
@ : denotes the '@' symbol

#### Section C: Company name
Same as Section A

#### Section D: The '.' symbol

\. : denotes the '.' symbol

#### Section E: Connectors

+ : denotes the '+' symbol is used to concatenate the searches.

In the following parts, we will go into more detail about each section.

-----------

### Part 2: Text of solution
1, 3, 5 have to be any letter (upper and/or lower) and/or number as well as periods '.', underscore '_' or dash '-'. Let's assume no special character can be selected (i.e., ?, /, or  \ ). This is not bad to create.

We will inclose out search to be within '[]' so that we can match other components of the email. This can be statisfied with the following code:

```
[a-zA-Z0-9._-]
```

- a-z: denotes any lower case letter
- A-Z: denotes any upper case letter
- 0-9: denotes any number between 0-9
- .,_,-: denotes a period, underscore, and dash

-----------

### Part 3: Connectors

Regarding 4. from the list within the process contains a special character '.' (it is special because it serves a purpose in regex), we remove its effect by using '\.' to eliminate its particular purpose ('\' is called an escape key). On the other hand, come to find out '@' is not  special character we do not have to use the escape key.

-----------

### Part 4: Putting everything together

We add all pieces information of 1. - 5. to be following code. The '+' symbol is used to concatenate the searches.

Lastly, the forward slash '/' is used to indicate the start of a regular expression. The parentheses '(' indicate that the expression that follows should be captured as a group. ')' denotes the end of the group.

The 'gi' at the end of the regular expression indicates that it should be used in a global and case-insensitive manner. This means that the expression will match all occurrences of the pattern, regardless of case.


```
/([a-zA-Z0-9._-]+@[a-zA-Z0-9._-]+\.[a-zA-Z0-9_-]+)/gi)
```

Imagine you have the url of a website and you want to extract all the emails from that website. The following is an example of a string that contains emails:


```python
str = """Name: John Doe
Email: john.doe@example.com 
Address: 123 Main Street, Anytown, USA

Name: Jane Smith
Email: jane.smith@example.com 
Address: 456 2nd Avenue, Anytown, USA

Name: Jim Johnson
Email: jim.johnson@example.com 
Address: 789 3rd Road, Anytown, USA """

```

You can use regex to extract all the emails from the string. 

## Regex

You may say what is regex? Regex is a sequence of characters that define a search pattern. Regular expressions can be used to check if a string contains the specified search pattern. It is also used to manipulate strings and extract information from them. Regular expressions are widely used in UNIX world.

The following will be used to extract emails from a string:

```python
emails = re.findall(r'^([a-zA-Z0-9._-]+@[a-zA-Z0-9._-]+\.[a-zA-Z0-9_-]+)$', str)
```

where the r in front of the string is used to denote a raw string. It is used to ignore all the escape characters present in a string. The ^ and $ are used to match the beginning and end of a string. 

## Anchors

Anchors means the beginning and end of a string using anchor characters, ^ and $ respectively. It is used to match a pattern only at the beginning or end of a string. It is also used to match a pattern only at the beginning or end of a word.

### Example 1

 For example, the following regex would match a string of exactly 4 characters: 
 
 
```python
fours = re.findall(r'^.{4}$', str)
```
 where the dot (.) is a wildcard character that matches any character and curly braces ({}) in the regex are used to specify the number of characters that should be matched. 





## Quantifiers

Quantifiers means the number of occurrences of a character that must be present in the input string for a match to be found. It is used to match a pattern between a minimum and maximum number of times. It is also used to match a pattern between a minimum number of times. It is also used to match a pattern between a maximum number of times. It is also used to match a pattern exactly n number of times. It is also used to match a pattern zero or more times. It is also used to match a pattern one or more times. It is also used to match a pattern zero or one time.

Though we do not use quantifiers in the example above, it is important to know that quantifiers are used to match a pattern between a minimum and maximum number of times. Below is a list of quantifiers:
 
The following is a list of Quantifiers in regex:

•	? (match 0 or 1 occurrence)
•	* (match 0 or more occurrences)
•	+ (match 1 or more occurrences)
•	{n} (match n occurrences)
•	{n,} (match n or more occurrences)
•	{n,m} (match between n and m occurrences)


### Example 2

For example, regex that will get all the '@' symbols from the string. The following is the output:
```python
ats = re.findall(r'/@+/g', str)
```

where  forward slash (/) in regex is used to indicate the start and end of a regular expression. The g flag in regex is used to perform a global match (find all matches rather than stopping after the first match).

*Please note:* The difference between ^ and $ and / / is that ^ and $ are anchor characters that are used to match the start and end of a string respectively, while / / is used to indicate the start and end of a regular expression.

## OR Operator

OR Operator means the logical OR operator. It is used to match a pattern with any of the alternatives specified. It is also used to match a pattern with any of the alternatives specified.

The OR Operator (|) in regex is used to match one of the specified patterns. 

### Example 3
For example, we want to match a string that contains Road or Avenue. The following is the output:

```python
road_or_avenue = re.findall(r'Road|Avenue', str)
```


## Flags
Flags are used to modify the search behavior. It is used to perform a case-insensitive match. It is also used to perform a global match (find all matches rather than stopping after the first match). It is also used to perform a multiline match. It is also used to perform a sticky match. It is also used to perform a Unicode match.

### Example 4
For example, we 

## Grouping and Capturing
Grouping and Capturing are used to match a pattern and remember the match. 



## Bracket Expressions
Bracket Expressions are used to match a single character out of several possible characters. It is also used to match a single character not present in the list of characters. It is also used to match a single character in a range. It is also used to match a single character not in a range. It is also used to match a single character of a certain type. It is also used to match a single character not of a certain type. It is also used to match any single character. It is also


## Greedy and Lazy Match
Greedy and Lazy Match are used to match as many characters as possible. It is also used to match as few characters as possible.


-----------

## Conclusion
This post provides a solution to creating a regular expression to match emails. It explains the use of letters, numbers, periods, underscores, and dashes in the username, '@' symbol, company name, '.' symbol, and uniform resource locator. It also explains the use of the escape key for the period and the '@' symbol not needing it. The final code includes the use of the forward slash, parentheses, plus sign, and "gi" at the end of the expression.

-----------

## About Author
Immanuel Williams is a data scientist, developer, and educator who has dedicated his career to helping others learn and grow in the world of technology. He is currently an adjunct professor at Cal Poly, teaching various programming and data science courses. He is also the founder of GATO365 Learning Center, an organization committed to disseminating education, knowledge, and resources related to data science and development. Immanuel has a passion for teaching, and he seeks to make data science and software development accessible to everyone. He is a strong advocate for diversity and inclusion in the technology industry, and he consistently works to ensure everyone has the opportunity to succeed. Immanuel believes that everyone should have the opportunity to learn, grow, and achieve success in the tech industry. He is committed to providing the best education and resources to help his students reach their goals.

## Contact Information:

- [Immanuel Williams's GitHub](https://github.com/gato365)
- [Immanuel Williams's LinkedIn](https://www.linkedin.com/in/immanuelwilliams/)

## [GitHub Gist Version](https://gist.github.com/gato365/5dd0f0241676b06b6f27f2ba52db7a4c)