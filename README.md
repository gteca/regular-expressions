# regular-expressions

Build, test and debug regex [regex101](https://regex101.com/)

## Character Set

The set of characters that we want to match is placed in brackets ```[]```.
- Example: ```[bcf]at``` Matches any character (just one) that starts with ```b```, or ```c```, or ```f``` and followed by ```at```.

![image](https://user-images.githubusercontent.com/26907925/211916186-1ca1d3c2-624a-477a-bc36-c29155d82c48.png)

## Ranges
The range of characters that we want to match is placed in brackets separated by dash ```[]```.
- Example: ```[a-z]at``` Matches any character from ```a``` to ```z``` followed by ```at```.

![image](https://user-images.githubusercontent.com/26907925/211917697-8592a720-1d70-4839-8949-a0dd9c025aff.png)

- Example: ```[0-9]th``` Matches anything from ```0``` to ```9``` followed by ```th```.

![image](https://user-images.githubusercontent.com/26907925/211917169-f9cd07b9-0bfa-4a6d-86b6-9ecaa125abb1.png)

- Example: ```[a-zA-Z0-9]``` Matches anything from ```a``` to ```z``` or ```A``` to ```Z``` or ```0``` to ```9```. All the alfanumeric characters.

![image](https://user-images.githubusercontent.com/26907925/211932128-daa60c9e-e0e6-4a5d-9243-1cc5b39e0648.png)

## Repeating Characters

To specify the number of repeating characters, we place the number inside ```{}```.
- Example: ```[a]{3}``` Matches any string with ```aaa```.

- Example: ```[a-z]{6,}``` Matches any sentence with six or more characters.

- Example: ```[a-z]{6,8}``` Matches any sentence with length between 8 and 11.
- 
![image](https://user-images.githubusercontent.com/26907925/211934851-5598569e-60fa-41ce-a731-9a8bf222b2bd.png)

- Example: ```[0-9]{15}``` Matches a number with exact 15 digits (IMSI number for example)
- 
- ![image](https://user-images.githubusercontent.com/26907925/211935124-0b2481d0-4e83-42f8-a5a6-fbd0984e3e77.png)

## Metacharacters

- ```\d``` matches any digit that is the same as ```[0-9]```
- ```\w``` matches any letter, digit and underscore character is the same as ```[a-zA-Z0-9_]```
- ```\s``` matches a whitespace character — that is, a space or tab
- ```\t``` matches a tab character only

Combining with repeating characters:

- ```\w{5}``` matches any five-letter word or a five-digit number
- ```\d{11}``` matches an 11-digit number such as a phone number

## Special Characters

- ```.``` Matches any digit, letter or symbol except newline
     - Example: ```.{8}``` Matches anything with 8 characters.
     - 
![image](https://user-images.githubusercontent.com/26907925/211936657-107880f0-b509-4d26-a757-36cb7e92c046.png)

- ```\``` "Escape character", used when we want to use a special character literally
     - Example: ```c\*``` Matches ```c*``` and not "ccccccc".

- ```^```  This "negate" notation is used to indicate a character that should not be matched within a range.
     - Example: ```b[^ae]d``` Avoid a match with a sentence starting with ```b``` having ```a``` or ```e``` and ending with ```d```
     - 
![image](https://user-images.githubusercontent.com/26907925/211937692-53c3b5a1-129f-47a3-8aa0-cd137d0616cb.png)


## Quantifiers:

- ```+``` Matches 1 or more of the preceding characters (Match at least one of the preceding character). The preceding character must exist and can be optionally duplicated.
      - Example: ```c+at``` Matches anything that starts with at least **1** or **more** ```c``` characters and ends with ```at```
      - 
![image](https://user-images.githubusercontent.com/26907925/211938212-47935378-0e60-4d36-80e8-2e0a8ff18bab.png)

     - Example: ```abc+at``` Matches anything starting with ```ab``` follows by at least **1** or **more** ```c``` characters and ends with ```at```
     
![image](https://user-images.githubusercontent.com/26907925/211938945-f4276cae-c56e-41bb-807c-7db53babbeec.png)


- ```?``` Zero or one quantifier (preceding character is optional)
     - Example: ```c?at``` Matches anything that **optionally** starts ```c``` and ends with ```at```
    
![image](https://user-images.githubusercontent.com/26907925/211939549-a2130367-1f81-4223-af20-1f8bed950f3d.png)

     - Example: ```https?``` Matches a string starting with ```http``` **optionally** ends with ```end```
     
![image](https://user-images.githubusercontent.com/26907925/211944084-411a97e6-f881-4ec4-8376-29f32bc77255.png)

- ```*``` Match 0 or more of the preceding character. The preceding character is optional and can be optionally duplicated. That is a combination of ```+``` and ```?``` because provides optional preecing character and duplication
     - Example: ```c?at``` Matches anything that **optionally** starts with one ```c``` or repeated characters and ends with ```at```
     - 
![image](https://user-images.githubusercontent.com/26907925/211939836-51d1c3af-2017-4e31-a4ac-505b33d2ce9f.png)

![image](https://user-images.githubusercontent.com/26907925/211942850-0e35ba12-231d-4e9b-86c6-4bebf0889132.png)

Combining with repeating characters:

- ```.+``` Matches one or an unlimited number of characters. 
     - Example, ```c``` , ```cc``` and ```bcd#.670``` will all match

```[a-z]+``` Matches all lowercase letter words irrespective of length, as long as they contain at least one letter. 
     - Example, ```book``` and ```boardroom``` both match.
  
## Groups

All the special characters mentioned only affect a single character or a range set. To apply the regex in expression (sentences) we group using ```()```.
- Example: ```book(.com)?``` Matches both ```book``` and ```book.com```, since the ```.com``` part is optional.

Here's a more complex example that would be used in a realistic scenario such as email validation:

pattern: ```@\w+\.\w{2,3}(\.\w{2,3})?```

![image](https://user-images.githubusercontent.com/26907925/211940666-3f454f1f-9197-433e-ab49-4fb8b15230a6.png)

## Alternate Characters
In regex, we can specify alternate characters using the "pipe" symbol ```|```. This is different from the special characters we showed earlier as it affects all the characters on each side of the pipe symbol. For example, the pattern ```sat|sit``` will match both ```sat``` and ```sit``` strings. We can rewrite the pattern as ```s(a|i)t``` to match the same strings.

![image](https://user-images.githubusercontent.com/26907925/211943998-3dd4c7ab-f041-4732-a9bf-de822541792a.png)


## Starting and Ending Patterns
You may have noticed that some positive matches are a result of partial matching. For example, if I wrote a pattern to match the string “boo”, the string “book” will get a positive match as well, despite not being an exact match. To remedy this, we’ll use the following notations:

- ```^``` Placed at the start, this character matches a pattern at the start of a string.

     - Example: ```^a\w*``` Matches both any sentence that **starts** with ```a``` and follow by **0** or **1** alfanumeric characters (allows repeation if any alfanumeric charcter after a exits)
![image](https://user-images.githubusercontent.com/26907925/211944685-dd636c20-c0f5-4e28-8fab-12b98f7a7a52.png)

- ```$``` Placed at the end, this character matches a pattern at the end of the string.

     - Example: ```[ltb]ook$``` Matches both any sentence that starts with ```l```, ```b``` or ```b``` followed by ```ook``` and **ending** with a new line.
     
![image](https://user-images.githubusercontent.com/26907925/211945134-d955f3ce-357e-4672-a9a1-850dfbbb49ab.png)


## Aditional Resources
[RegexOne](https://www.sitepoint.com/learn-regex/)
