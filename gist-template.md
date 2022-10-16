# Regex Code Breakdown: Matching an Email

## Summary
Regex (short for regular expressions) is a sequence of characters used to check for patterns in a string. This tutorial will explain a sample line of Regex code to breakdown Regex syntax in a practical situation. The sample line or Regex is used to validate an email.

Here is the code regular expression that will be analyzed:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

## Table of Contents
- [Regex Compentents](#regex-components)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Author](#author)


## Regex Components <a id=regex-components></a>
Regex syntax is structured with the following components:

Every expression is wrapped in a opening anchor (`/^`) and a closing anchor (`$/`).

Within the opening and closing anchor is where the pattern checkers are established in 'grouping constructs'. Grouping constructs are wrapped in brackets like this
```
// match any sequence of ...
/^([a-z])$/         // lowercase letters
/^([a-z0-9])$/      // lowercase letters + numbers
/^([a-z0-9_\.-])$/  // lowercase letters + numbers + specified characters
```

## Anchors <a id=anchors></a>
Unlike other Regex grouping constructs, anchors don't match with characters. Instead, the job of an anchor is to match the position before, after or between characters.
```
// specified characters are followed by...
/^([a-z0-9_\.-]+)@([\da-z\.-]+)$/   // a '@' + '.' or '-' + 
                                    // lowercase letters
```


## Quantifiers <a id=quantifiers></a>
Quantifiers help a Regex quantify how many times a character or group of characters is represented. With a specified limit or range of character or character groups, a quantifier can determine whether or not the expression matches.

Quantifiers range in terms of specificity. You can match a certain amount of characters (`{x}`), match a minimum amount of times (`{x,}`) or match between a certain range of times (`{x, y}`). There are other quantifiers such as `*` that are less picky, matching any amount of characters except for 0.

## OR Operator <a id=or-operator></a>
An or operator in a Regex represented a match in different cases. For example, `(lions|tigers)` will match in either the case of the word `lions` or in the case of the word `tiger` being applied.

## Character Classes <a id=character-classes></a>
Instead of matching characters by a manually prescribed character or character group, we can use character classes to match expressions by a class of characters.

Here are a few character classes and what they match:
```
.     // any class: matches any character (except new lines)
\d    // digit class: matches with numbers
\s    // white space class: matches with spaces, new lines and tabs
```

## Flags <a id=flags></a>
While there are no flags in this email address, they are a useful Regex tool worth noting. Flags are Regex syntax that change the way Regex matches with text. Here are a few examples:
```
i   // ignore case-sensitivity
g   // search for all instances of a match
s   // match content even if it's on new line
```

## Grouping and Capturing <a id=grouping-and-capturing></a>
Grouping and capturing refers to the group constructors that serve different purposes for the text. As mentioned, `[a-z0-9_\.-]` serves as a set of rules for matching the unique part of a user's email. The `[\da-z\.-]` matches the email provider's domain (ex. gmail). The final group, `[a-z\.]` matches the ending of the emal address, including the dot (ex. .com, .ca)

## Bracket Expressions <a id=bracket-expressions></a>
Bracket expressions refer to each group in a bracket. As mentioned in the previous section, there are 3 bracket expressions in the email Regex example.

## Greedy and Lazy Match <a id=greedy-and-lazy-match></a>
Greedy matches are Regex matches that look for not only one instance of a match, but every potential instance in the given string up (until a line break). Lazy matches, the default for Regex, look for the first match only. There are only lazy matches in the example email expression as there is nothing checking for a repeat of matches.

## Boundaries <a id=boundaries></a>
Boundaries are the extent of characters to which a group constructor reaches to find a match. In our case, there are three boundaries divided by the @ and . in the email.

## Back-references <a id=back-references></a>
Say you want to match text that will have the same beginning and end. You would need a Regex that will match with 2 different group constructors. Back-references prevent you from the repeated syntax of rewriting the same condition in a different place. You can simply write your group constructor as usual. Then add a backslash at the end of you Regex followed by the sequential number of the group constructor you're looking to match wherever you're looking to match it. For example, if you want to repeat the 

## Look-ahead and Look-behind <a id=look-ahead-and-look-behind></a>
Look-aheads and look-behinds (together, called look-arounds) are are a method that regex uses to find a specified match and then locate another specified match ahead or behind the first match. Here are some examples, given the phrase `meowbarkbarkmeow`:

```
meow(?=bark)           // match the 1st "meow" followed by a "bark" (1st "meow")
bark(?!bark)           // match the 1st "bark" NOT followed by "bark" (2nd "bark")
(?<=meow)bark          // match the 1st "bark" with "meow" before it (1st "bark")
(?<=bark)meow(?=bar)   // match the 1st "meow" with "bark" before it & "meow" after it (no match) 
```

Note that there are also positive and negative look-ahead, -behinds and -arounds. The first line is an example of a positive look ahead. The second is a negative look ahead. The last is a positive look around.

## Author <a id=author></a>
Janae Welsh is a full-stack web developer, learning React at the time of this gist's creation.

Contact me via:
- Email: janae.wel@gmail.com
- GitHub: https://github.com/gitJanaeW/
- LinkedIn: https://www.linkedin.com/in/janae-welsh-01a52a23a/
