## Regular expressions (REGEX) 
A mini-language first implemented by Ken Thomspon in the Unix text editor with the ed standalone program, then implemented into the grep standalone program("Global regular expression print") which is still used today in mac and linux systems.

### Brief history: 
- Basic REGEX - The original ed/grep versions. Minimal (68)
- Extended REGEX - adding + , ? , | (or) and grouping function using (79)
- Perl Compatible (PCRE) - Perl compatible regex, massively expanded (97)


For my purpose in python it is a mini-language for explaining text patterns. 

```python
import re #Library that reads REGEX for python
```

### Application: 
**REGEX has 2 parts:**
- Literal characters which means well.... itself haha
	- `a` matches a
	- `cat` matches cat
	- etc
- Special characters which have a function
	- `^` = the start of string (optional)
	- `$` = the end of string (optional)
	- `.` = any single character
	- `\d` = any digit (0-9)
	- `\w` = any "word characters" (this strictly included: letters, digits and underscores)
	- `+` = matches the preceding element one or more times
	- `*` = matches the preceding element zero or more times
	- `?` = matches the preceding element zero or one time
	- `[]` = character set (any one of these)
	- `{n}` = matches the preceding element exactly n times
	- `{n.m}` = matches the preceding element between n and m times

### Exercises:
**Level 1: Reading patterns (what does this match?)**
1. `^\d+$`
2. `^[A-Z]\d$`
3. `^\w+@\w+$`
4. `^[aeiou]+$`

**Level 2: Writing patterns (write a regex for...)**
5. A string that is exactly 3 uppercase letters (like "ABC")
6. A number between 1 and 4 digits (like "7" or "1234")
7. A string starting with "NZ" followed by any digits (like "NZ12345")
8. A word containing only lowercase letters and underscores (like "folder_name")

**Level 3: Your actual use case**
9. Your simple folder pattern: `A-1-folder_name` (category letter, dash, number, dash, name)
10. Your priority folder pattern: `[R]-A-1-folder_name` (bracket letter bracket, dash, category, dash, number, dash, name)

[Regex Checker](https://regex101.com) 

**Level 1 answers:**
1. The string contains only one or more digits
2. The string is only a combination of a single capitalized letter and a digit
3. The string contains only one or more wrd charactersord characters followed by the literal character @ before another set of one or more wo
4. The string contains only one or more vowels

**Level 2 answers:**
1. `^[A-Z]{3}$`
2. `^\d{1,4}$`
3. `^NZ\d+$`
4. `^[a-z_]+$`

**Level 3 answers:**
1.  
