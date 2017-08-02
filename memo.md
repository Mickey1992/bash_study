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
