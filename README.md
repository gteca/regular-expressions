# regular-expressions

Build, test and debug regex [regex101](https://regex101.com/)

## Character Set

The set of character that we want to match is placed in brackets ```[]```.
- Example: ```[bcf]at```.
Matches anything that starts with ```b```, ```c```, ```f``` and followed by ```at```.

![image](https://user-images.githubusercontent.com/26907925/211916186-1ca1d3c2-624a-477a-bc36-c29155d82c48.png)

## Ranges
The range of character that we want to match is placed in brackets separated by dash ```[]```.
- Example: ```[a-z]at```.
Matches anything from ```a``` to ```z``` followed by ```at```.

![image](https://user-images.githubusercontent.com/26907925/211917697-8592a720-1d70-4839-8949-a0dd9c025aff.png)

- Example: ```[0-9]th```.
Matches anything from ```0``` to ```9``` followed by ```th```.

![image|100x100](https://user-images.githubusercontent.com/26907925/211917169-f9cd07b9-0bfa-4a6d-86b6-9ecaa125abb1.png)


Specify the range of character or digits to match.


.       - Any Character Except New Line

/.at/

The **fat** **cat** runs down the street.
     It was searching for a mouse to **eat**


\d      - Digit (0-9)

\D      - Not a Digit (0-9)

\w      - Word Character (a-z, A-Z, 0-9, _)

The **fat** **cat** runs down the street.
     It was searching for a mouse to **eat**
     
\W      - Not a Word Character

\s      - Whitespace (space, tab, newline)

\S      - Not Whitespace (space, tab, newline)

\b      - Word Boundary

\B      - Not a Word Boundary

^       - Beginning of a String

$       - End of a String

[]      - Matches Characters in brackets

[^ ]    - Matches Characters NOT in brackets

|       - Either Or

( )     - Group

Quantifiers:
*       - Match 0 or more pf the preceding token

/re*/
Ex: The fat cat **r**uns down th**e** st**ree**t.
     It was sea**r**ching fo**r** a mouse to eat
  
+       - Matches 1 or more of the preceding token (Match at least one of the preceding character)

/e+/

Ex: Th**e** fat cat runs down th**e** str**ee**t.
   
?       - Matches 0 or 1 of the preceding character (optional) 

Match all occurences of character **e** and optionally **ea**
/ea?/

Ex: Th**e** fat cat runs down th**e** str**ee**t.
     It was s**ea**rching for a mous**e** to **ea**t
{3}     - Exact Number

{3,4}   - Range of Numbers (Minimum, Maximum)

## Aditional Resources
[RegexOne](https://regexone.com/lesson/introduction_abcs)
