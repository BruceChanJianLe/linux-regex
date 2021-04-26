# Linux REGEX

Regex == Regular Expression

Regular expressions are all about text! Regular expressions is a tool to help working with text eaiser by describing text pattern.

- Regular expression engines are eager.
- Regular expression engines are greedy.

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
- Dot-matches-all: /re/s (matches also return line)

## Use regexpal.com

## Metacharacters

**Characters with special meaning**
- Like mathematical operators
- Transform literal characters into powerful expressions

**Only a few metacharacters to learn**
```regex
\ . * + - {} [] ^ $ | ? () : ! =
```

**Can have more than more than one meaning**

**Variation between regex engines**

Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Wildcard | . | Any character except newline | /h.t/ matches "hat", "hot", "hit", but not "heat"
Escaping | \ | Allow use of metacharacters as literal characters | /9\.00/ matches "9.00" but not "9500" or "9-00"
Begin set | [ | Begin a character set | - 
End set | ] | End a character set | - 
Set | [] | Use to define a character set | /gr[ea]y/ matches "grey" and "gray"
Ranges | - | Use to define a range of character | /[A-Z]ello/ matches "Hello"; [0-9], [A-Za-z], [a-ek-ou-y]
Caret | ^ | Negate a character | /see[^mn]/ matches "seek", "see " and "sees" but not "seem" or "seen"

Name | Special Character | Meaning
--- | --- | ---
Space | ` ` | Spaces
Tab | `\t` | Tabs
Line return | `\r, \n, \r\n` | Line returns
Non-printable character | bell `\a`, escape `\e`,  form feed `\f`, vertical tab `\v` | bell, escape, form feed, vertical tab
ASCII or ANSI code |  `0xA9 = \xA9` | codes that control appearance of a text terminal

Shorthand | Meaning | Equivalen
--- | --- | ---
\d | Digit | [0-9]
\w | Word character | [a-zA-Z0-9]
\s | Whitespaces | [ \t\r\n]
\D | Not digit | [^0-9]
\W | Not word charater | [^a-zA-Z0-9_]
\S | Not whitespace | [^ \t\r\n]

**Examples**  
/\d\d\d\d/ matches "1984" but not "text"  
/\w\w\w/ matches "ABC", "123", and "1_A"  
/\w\s\w\w/ matches "I am" but not "Am I"  
/[\w\-]/ matches as word character or hyphen (useful)  
/[\d\s]/ matches any digit or whitespace character  
/[^\d]/ is the same as /\D\ and /[^0-9]/  

**POSIX BRACKET EXPRESSIONS**
Class | Meaning | Equivalent
--- | --- | ---
[:alpha:] | Alphabetic characters | A-za-z
[:digit:] | Numeric characters | 0-9
[:alnum:] | Alphanumeric characters | A-Za-z0-9
[:lower:] | Lowercase alphabetic characters | a-z
[:upper:] | Uppercase alphabetic characters | A-Z
[:punct:] | Punctuation characters | -
[:space:] | Space characters | \s
[:blank:] | Blank characters (space, tab) | -
[:print:] | Printable characters, space | -
[:graph:] | Printable characters, no space | -
[:cntrl:] | Control characters (non-printable) | -
[:xdigit:] | Hexadecimal characters | A-Fa-f0-9

**Examples**
```bash
ps aux | grep --regexp="s[[:digit:]]"
```

## Repetition Metacharacters

**Unlimited Repetition**
Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Asterisk | * | Preceding item zero more times | /apples*/ matches "apple", "apples", and "applessssss'
Plus | + | Preceding item one or more times | /apples+/ matches "apples" and "applessssss" but not "apple"
Question mark | ? | Preceding item zero or one time | /apples?/ matches "apple" and "apples" but not "applessssss"

**Examples**  
/colou?r/ matches "color" and "colour"  
/\d\d\d\d*/ is the same as /\d\d\d+/ which matches "123456789" "1234" "123" but not "12"  
/\w+s/ matches any word that ends with 's'  

**Quantified Repetition**
Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Opening curly braces | { | Start quantified repetition of preceding item | -
Closing curly braces | } | End quantified repetition of preceding item | -
Curly braces | {min,max} | min and max are positive numbers; min must always be included; can be zero; max is optional

**Examples**  
\d{4,8} matches numbers with four to eight digits  
\d{4} matches numbers with exactly four digits (min is max)  
\d{4,} matches numbers with four or more digits (max is infinite)  
\d{3}-\d{3}-\d{4} matches use number line 555-867-5309  

**Greedy Expression**

**Lazy Expression**
Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Lazy | ? | Make preceding quantifier lazy | -

Usage: *?, +? <metacharacter>?
This uses the lazy method to search instead of the default greedy method.  

## Grouping and Alternating Metacharacters

**Grouping Character**  
Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Left Parentheses | ( | Start grouped expression | /(abc)+/ matches "abc" and "abcabcabc"
Right Parentheses | ) | End grouped expression | /(in)?dependent/ matches "independent" and "dependent"

- Group portions of the expression
    - Apply repetition operators to a group
    - Makes expressions easier to read
    - Captures group for use in matching and replacing
    - Cannot be used inside of character set

**Alternation Character**  
Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Pipe / Or | \| | Match previous or next expression | /apple|orange/ matches "apple" and "orange"

- It is an OR operator
    - Either match expression on the left or match expression on the right
    - Ordered, leftmost expression gets precedence
    - Multiple choices can be daisy-chained
    - Group alternation expressions to keep them distinct

**Writing Logical and Efficient Alternations**  

Regex are eager and greedy!  

**Repeating and Nesting Alternations**  

- Repeating
    - First matched alternation does not effect the next matches
    - /(AA|BB|CC){6}/ matches "AABBAACCAABB"

- Nesting
    - Check nesting carefully
    - /(\d{2}([A-Z]{2}|-\d\w\d\w)|\d{4}(-\d{2}-[A-Z]{2,8}|_x[A-F]))/
    - Trade-off between precision, readability and efficiency

## Anchored Metacharacters

**Start and End Metacharacter**  
Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Caret | ^ | Start of string/line | /^apple/ 
Dollar Sign | $ | End of string/line | /apple$/
Backslash A | \A | Start of string, never end of line | /\Aapple/
Backslash Z | \Z | End of string, never end of line | /apple\Z/

Note that caret can also meas negate but here it has a different meaning.

- Reference a position, not an actual character
    - Zero-width

Note that \A and \Z may not be supported on some platform.  
Do keep in mind of line breaks and multi-line mode.

**Word Boundaries**  
Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Backslash lower-case b | \b | Word boundary (start/end of word) | \b\w+\b\ finds four matches in "This is a test."
Backslash Upper-case b | \B | Not a word boundary | /\Bw+\B/ finds two matches in "This is a test." ("hi" and "es")

- Reference a position, not an actual character
- Conditions for matching
    - Before the first word character in the string
    - After the last word character in the string
    - Between a word character and a non-word character
- Word characters: [A-Za-z0-9_]
- Support
    - Most regex engines, not in early Unix tools (BREs)
- Caution
    - A space is not a word boundary
    - Word boundaries reference a position
        - Not an actual character
        - Zero-length
- Examples
    - String: "apples and oranges"
    - No match: /apples\band\boranges/
    - Match: /apples\b \band\b \boranges/

## Backreferences

- Grouped expressions are captured
    - Stores the matched portion in parentheses
        - /a(p{2}l)e/ matches "apple" and stores "ppl"
        - Stores the data matched, not the expression
    - Automatically, by default save the data
- Backreferences allow access to captured data
    - Refer to first backreference with \1

Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Backslash 1 to 9 | \1 through \9 | Backreference for positions 1 to 9 | /(apples) to \1/ matches "apples to apples"

- Usage
    - Can be used in the same expression as the group
    - Can be accessed after the match is complete
    - Cannot be used inside character classes
- Support
    - Most regex engines support only \1 to \9
    - Some regex engines support \10 to \99
    - Some regex engines use $1 to $9 instead

- Examples
    - /(apples) to \1/ matches "apples to apples"
    - /(ab)(cd)(ef)\3\2\1/ matches "abcdefefcdab"
    - /<(i|em)>.+?</\1> matches "<i>Hello</i>" and "<em>Hello</em>"; it does not match "<i>Hello</em>

**Optional Expressions**

- Optional elementss
    - /A?B/ matches "AB" or "B"

- Captures occur on zero-width matches
    - /(A?)B/ matches "AB" and captures "A"
    - /(A?)B/ matches "B" and captures ""

- Backreference become zero-width too
    - /(A?)B\1/ matches "ABA" and "B"
    - /(A?)B\1C/ matches "ABAC" and "BC"

**The Right way to do!!!**

- Captures do not always occur on optional groups
    - /(A)?B/ matches "AB" and captures "A"
    - /(A)?B/ matches "B" and does not captures anything

- Backreference is to a group that failed to match
    - /(A)?B\1/ matches "ABA" but not "B"
    - Except in JavaScript

**The differences**

- Element is optional, group/capture is not optional
    - /(A?)B/ matches "B" and captures ""

- Element is not optional, but group/capture is optional
    - /(A)?B/ matches "B" and does not captures anything


**Non-Capturing Group Expression**

Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Question mark colon | ?: | Specify a non-capturing group | /(\w+)/becomes/(?:\w+)/

- Syntax 
    - /(\w+)/becomes/(?:\w+)/
    - ? = "Give this group a different meaning"
    - : = "The meaning is non-capturing"

- Turns off capture and backreferences
    - Optimize for speed
    - Preserve space for more captures

- Support
    - Most regex engines except Unix tools

## Lookahead Assertions

- Positive lookahead assertions

Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Question mark equal sign | ?= | Positive lookahead assertion | /(?=seashore)sea/ matches "sea" in "seashore" but not "seaside"

- Assertion of what ought to be ahead
    - If lookahead expression fails, the match fails
    - Any valid regular expression can be used
    - Zero-width, does not include group in the match

- Support
    - Most regex engines except Unix

- Syntax
    - /(?=regex)/

- Example
    - /(?=seashore)sea/ matches "sea" in "seashore" but not "seaside"
    - Same as /sea(?=shore)/

Explanation: (?=seashore)sea matches only the sea in seashore  
Usage: \b[A-Za-z']\b(?=,) this will match `Emerson,` but only the `Emerson` is match but it need the comma there.  

**Double-testing with Lookahead Assertions**  

Difference between /(?=seashore)sea/ and /sea(?=shore)/  
- It matches seashore first before attempting for sea
- It matches sea first then look for shore

- Match a pattern that also matches another pattern
    - /\d{3}-\d{3}-\d{4}/ matches "555-302-4321" and "555-781-6978"
    - /^[0-5\-]+$/ mathces "555-302-4321" and "23410-5"
    - /(?=^[0-5\-]+$)\d{3}-\d{3}-\d{4}/ matches "555-302-3421"
    - /(?=^[0-5\-]+$)(?=.*4321)\d{3}-\d{3}-\d{4}/ matches "555-302-4321"


- Negative lookahead assertions

Name | Metacharacter | Meaning | Example
--- | --- |--- | ---
Question mark exclamation mark | ?! | Negative lookahead assertion | /(?!seashore)sea/ matches "sea" in "seaside" but not in "seashore"/

- Syntax
    - /(?!regex)/

- Example
    - /(?!seashore)sea/ matches "sea" in "seaside" but not in "seashore"
    - Same as /sea(?!shore)/
    - /online(?! training)/ does not match "online training"
    -  /online(?!.*training)/ does not match "online video traning"

## Lookbehind Assertions

