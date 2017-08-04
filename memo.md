### Sha-Bang(#!) + pathName
The program saved in the path  will interpret the commands in the script
```bash
#!/bin/sh
#!/bin/bash
#!/usr/bin/perl
#!/usr/bin/tcl
#!/bin/sed -f
#!/bin/awk -f
```


### to make a script executable by itself
```bash
chmod 555 scriptname
chmod +rx scriptname
chmod u+rx scriptname
```


### semicolon (;)
Permits putting two or more commands on the same line.
But a space is needed between the semicolon and the other command
`echo hello; echo there`

### double quote and single quote
"STRING" preserves (from interpretation) most of the special characters within STRING.
'STRING' preserves all special characters within STRING. This is a stronger form of quoting than "STRING"


### test
Arithmetic evaluation of octal / hexadecimal constants takes place automatically within a [[ ... ]] construct.


### String

String length
```bash
${#varString}
`expr length $varString`
`expr "$varString":'.*'`
```

Length of matching substring at beginning of string
```bash
`expr match "$varString" 'regExpr'`
`expr "$varString":'regExpr'`
```

the postion at which the substring first appears in String(the index of string is from 1 not 0)
```bash
`expr index "$varString" "$subString"`
```

subString extraction
```bash
${varString:position} #extract subString from $varString at position
${varString:position:length} #extract subString from $varString at position with a certain length
`expr substr $varString $position $length` #the same as above
`expr match "$string" '\($regExpr\)'` #Extracts $substring at beginning of $string
`expr "$string" : '\($substring\)'` #the same as above
```

subString Removal (substring is a regExpr)
```bash
${string#substring}
#Deletes shortest match of $substring from front of $string.

${string##substring}
#Deletes longest match of $substring from front of $string.

${string%substring}
#Deletes shortest match of $substring from back of $string.

${string%%substring}
#Deletes longest match of $substring from back of $string.
```

subString Replacement
```bash
${string/substring/replacement}
#Replace first match of $substring with $replacement.The string itself is not changed

${string//substring/replacement}
#Replace all matches of $substring with $replacement.The string itself is not changed

${string/#substring/replacement}
#If $substring matches front end of $string, substitute $replacement for $substring.

${string/%substring/replacement}
#If $substring matches back end of $string, substitute $replacement for $substring.
```


### paramater substitution
```bash
${parameter} #get the value of variable parameter
$parameter #get the value of variable parameter, sometimes dose not work.So it is better to use the way above.

${parameter-default}
${parameter:-default} #if parameter is not set, use default(not set default)
#the two above are always the same.The extra : makes a difference only when parameter has been declared, but is null.

${parameter=default}
${parameter:=default}
#If parameter not set, set it to default.

${parameter+alt_value}, ${parameter:+alt_value}
#If parameter set, use alt_value, else use null string.

${parameter?err_msg}, ${parameter:?err_msg}
#If parameter set, use it, else print err_msg and abort the script with an exit status of 1.

${!varprefix*}
${!varprefix@}
#Matches names of all previously declared variables beginning with varprefix.
```

