### R4DS
#### Chapter 14 (Strings)
This chapter shows regular expressions, or regexps for short. Regexps are a concise language for describing patterns in strings. Package prerequisites are tidyverse and stringr.

- A basic string is created with
```
string <- 'Write something that is a string'
```
- After, we can show the string by tiping in the variable or just the content of the string with 
```
writelines(string)
```
This is helpful for testing a whether a special character (mostly a ' or ") is correctly set in the string. Escapes can be inserted as backslashs `\'`.

**Use of stringr basics**
By typing str_ a bunch of possible commands are presented, e.g.:
- Get length of a string (here, it's 32):
```
stringr::str_length(string)
```
- Combine two+ exisisting strings:
```
string1 <- 'Test'
stringr::str_c(string,string1)
[1] "Write something that is a stringTest"
```
- Subsetting strings (meaning that we only take parts of a string depending on the position related to the start or the end of the string:
```
stringr::str_sub(x, <start_of_subset>, <endofsubset>)
```
   - It is also possible to put a minus sign before `<start_of_subset>` or `<endofsubset>`. Like this, the count is 'mirrored'             from the latter to the previous part of the string.

- Matching patterns with regexps
  We’ll use str_view() and str_view_all(). These functions take a character vector and a regular expression, and show you how     they match.
```
stringr::str_view(x, "<searched_string")
```
   - Anchor are possible to look for a certain string pattern at the beginning or the end of a string with:
   ```
   str_view(<variable_name_of_string>, "^a$")
   ```
   If the `^`is set 'a' in the beginning of a string is searched, and if `$` is set, a 'a' at the end of a string is searched.
   
   - Repetition (how many matches does `str_view`find in one string?): This can be controlled by adding a `?`, `+`, or `*`.
   
### INTS
#### Chapter 10 (second part: Open Science and Planning Research)
The chapter is concerned about the replicability crisis and how researches should react to that. It reports that most published research findings are false because in many research fields exist the following problems: selective publication, the .05 imperative, and lack of replication. 

As all of them seem to be important, the latter above the others seems to me one of the biggest problems in bevahioral economics research (or all economics). Many researches think that positive results that were achieved (with a p-value < 0.05) are taken for true and established. This leads to the problem, that these experiments are not interesting to re-work on (as the prior positive results are taken for true). Like this, reproduction of experimental research is uninteresting and don't check possible false statement of the prior research.

The essence of the chapter is to postulate open science activities that "foster the openness, integrity, and reproducibility of scientific research" according to the Center of Open Science (COS.io). To achieve this, we will pre-register our study on the platform in order to focus on a proper study design beforehand.
   
   



