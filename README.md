# Linux REGEX

Regex == Regular Expression

Regular expressions are all about text! Regular expressions is a tool to help working with text eaiser by describing text pattern.

## Advantages

**Regular Expression**
- Symbols representing a text pattern

**Regular Expressions**
- Formal language interpreted by a regular expression processor

**Used for matching, searching and replacing text**

## What are Regular Expression use for?

- Test if a phone number has the correct number of digits
- Test if an email address is in a valid format
- Search a document for either "color" of "colour"
- Replace all occurrences of "Bob", "Bobby", or "B." with "Robert"
- Count the number of times "training" is immediately preceded by "computer", "video", or "online"
- Convert a tab-delimited file into a comma-delimited file
- Find duplicate words in a text

matches  
- A regular expression matches text if it correctly describes the text
- Text matches a regular expression if it is correctly described by the expression

## History of Regular Expressions

- 1943: Warren McCulloch and Walter Pitts develop models of how the nervous systems works (i.e., how a machine could be built like a brain)
- 1956: Stephen Kleene describes these models with an algebra called "regular sets" and creates a notation to express them called "regular expressions"
- 1968: Ken Thompson implements regular expressions in ed, an early Unix text editor
- g/Regular Expression/p = Global Regular Expression Print: "grep"
- Then we have egrep - extended grep
- 1986: POSIX (Portable Operating System Interface), is a standard to ensure compatibility. Then we have **Basic Regular Expressions (BREs)** and **Extended Regular Expressions (RREs)**
- 1986: Henry Spencer releases a regex library written in C, which could be incorporated into other programs and provides consistency
- 1987: Larry Wall releases Perl, which used Spencer's regex library and over time, added many powerful features
- Perl-compatible languages and programs (PCRE library)

It is the rise of the web that encourages more use of regex in many other pragramming languages.

## Regular Expression Engines

- C/C++
- Java
- JavaScripts/ActionScript (ECMAScript)
- .NET
- Perl
- PHP (PCRE)
- Python
- Ruby
- Unix (POSIX BRE, POSIX ERE)
- Apache (v1:POSIX ERE, v2:PCRE)
- MySQL (POSIX ERE)

## Regular Expression Modes

- Standard: /re/
- Global: /re/g
- Case-insensitive: /re/i
- Multiline: /re/m
- Dot-matches-all: /re/s

## Use regexpal.com

## Metacharacters

**Characters with special meaning**
- Like mathematical operators
- Transform literal characters into powerful expressions

**Only a few metacharacters to learn**
```regex
\ . * + - {} [] ^ $ | ? () : ! =
```
