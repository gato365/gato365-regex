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

Are you interested getting your hands dirty with regular expressions? Do you want to learn how to match emails? If so, this post is for you. This post provides a solution to creating a regular expression to match emails, which consists of three parts. The first part explains that the user name, the '@' symbol, the company name, the '.' symbol, and a uniform resource locator can all contain letters, numbers, periods, underscores, and dashes. The second part explains the use of escape key for the period, and that the '@' symbol does not need it. The third part provides the final code, which includes the use of the forward slash, parentheses, plus sign, and "gi" at the end of the expression.

## Summary
This post provides a solution to creating a regular expression to match emails, which consists of three parts. The first part explains that the user name, the '@' symbol, the company name, the '.' symbol, and a uniform resource locator can all contain letters, numbers, periods, underscores, and dashes. The second part explains the use of escape key for the period, and that the '@' symbol does not need it. The third part provides the final code, which includes the use of the forward slash, parentheses, plus sign, and "gi" at the end of the expression.



-----------

## You say you want emails huh
You want get emails from a potential clients website. You need to address of the following questions:

1. What is the format of website?
2. What is general format of a email?
3. How many peoples' email are you trying to extract?
4. What other types of information are you looking for? (i.e. name, position, phone number)

This post will primarily for focus on question 2., however, when using regex (regular expression) you might as well know these other parameters so that you are not redoing work.



-----------

### Part 1: The Breakdown of Process

We know that emails are strings that have 3 pieces of information in the following order

1. username  **then**
2. the '@' symbol **then**
3. name of the company **then**
4. the '.' symbol **then**
5. a uniform resource locator (i.e. com, edu, or org)


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

-----------

## Conclusion
This post provides a solution to creating a regular expression to match emails. It explains the use of letters, numbers, periods, underscores, and dashes in the username, '@' symbol, company name, '.' symbol, and uniform resource locator. It also explains the use of the escape key for the period, and the '@' symbol not needing it. The final code includes the use of the forward slash, parentheses, plus sign, and "gi" at the end of the expression.

-----------

## About Author
Immanuel Williams is a data scientist, developer, and educator who has dedicated his career to helping others learn and grow in the world of technology. He is currently an adjunct professor at Cal Poly, where he teaches a variety of programming and data science courses. He is also the founder of GATO365 Learning Center, an organization committed to the dissemination of education, knowledge, and resources related to data science and development. Immanuel has a passion for teaching, and he seeks to make data science and software development accessible to everyone. He is a strong advocate for diversity and inclusion in the technology industry, and he consistently works to ensure that everyone has the opportunity to succeed. Immanuel believes that everyone should have the opportunity to learn, grow, and achieve success in the tech industry. He is committed to providing the best education and resources to help his students reach their goals.

## Contact Information:

- [Immanuel Williams's GitHub](https://github.com/gato365)
- [Immanuel Williams's LinkedIn](https://www.linkedin.com/in/immanuelwilliams/)