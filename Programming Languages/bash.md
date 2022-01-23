# BASH

## FAQ

**What's the difference between [ and [[** 

1. It is a syntactical feature of the shell, so it has some special behavior that [ doesn't have. 
You no longer have to quote variables like mad because [[ handles empty strings and strings with whitespace more intuitively. 
For example, with [ you have to write `if [ -f "$file" ]` to correctly handle empty strings or file names with spaces in them. 
With [[ the quotes are unnecessary `if [[ -f $file ]]`

2. Because it is a syntactical feature, it lets you use && and || operators for boolean tests and < and > for string comparisons. 
[ cannot do this because it is a regular command and  &&, ||, <, and > are not passed to regular commands as command-line arguments.

[link](http://mywiki.wooledge.org/BashFAQ/031)