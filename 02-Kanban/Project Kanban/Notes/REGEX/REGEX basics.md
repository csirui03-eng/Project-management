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
	- `^` = the start of string
	- `$` = the end of string
	- `.` = any single character
	- `\d` = any digit (0-9)
	- `\w` = any "word characters" (this strictly included: letters, digits and underscores)
	- `+` = one or more of the previous thing
	- `*` = zero or more of the previous thing
	- `?` = zero or one (optional)
	- `[]` = character set (any one of these)
