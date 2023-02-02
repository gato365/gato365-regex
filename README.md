# Regex Tutorial Starter Code

## You say you want emails, huh????

You want get emails from a potential clients website. You need to address of the following questions:

1. What is the format of website?
2. What is general format of a email?
3. How many peoples' email are you trying to extract?
4. What other types of information are you looking for? (i.e. name, position, phone number)

This post will primarily for focus on question 2., however, when using regex (regular expression) you might as well know these other parameters so that you are not redoing work.




## Process for getting emails
We know that emails are strings that have 3 pieces of information in the following order

1. username  **then**
2. the '@' symbol **then**
3. name of the company **then**
4. the '.' symbol **then**
5. a uniform resource locator (i.e. com, edu, or org)

### Part 1 of solution
1, 3, 5 have to be any letter (upper and/or lower) and/or number as well as periods '.', underscore '_' or dash '-'. Let's assume no special character can be selected (i.e., ?, /, or  \ ). This is not bad to create.

We will inclose out search to be within '[]' so that we can match other components of the email

```
/([a-zA-Z0-9._-]+@[a-zA-Z0-9._-]+\.[a-zA-Z0-9_-]+)/gi)
```
