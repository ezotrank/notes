
List the markdown style principles to be consistent in all documents.

[TOC]


## Headers

-   H1 header `#` uses camel case with spaces(e.g., `Markdown Style Guide`)
-   Other headers start with capital later and no full stop at the end.



## Spacings

-   One spacing between the header and content:
	
	```markdown
	## Heading 1
	
	Text after...
	```

-   Tree spacing between header 1 blocks:

	```markdown
	## Heading 1

	Text after...



	## Heading 2

	Text after...
	```

-   Two spacing between headers in all others cases:

	```markdown
	## Heading 1

	Text after...


	### Inside Heading 2

	Text after...


	### Inside Heading 2

	Text after...
	```

-   One spect between text and the code block:
	
	~~~markdown
	The simple bash loop

	```shell
	for var in one two three; 
	do
		echo "Variable is $var"
	done
	```
	~~~



## Lists

-   Use "lazy" numbering:

	```markdown
	1.  First line.
	1.  Second line.
	1.  The third line. 
	```

-   Two spaces after a number list and three after bullet:

	```markdown
	1.  Hello.
		1.  Hello two.
		2.  Hello three.

	-   Hello One.
	-   Hello two.
	```

-   Use dash `-` instead of `*` for the bullet list.
-   Each list ends with full stop.

**Example**

```markdown
1.  2 spaces after a numbered list.
	4 space indent for wrapped text.
2.  2 spaces again.

-   3 spaces after a bullet.
	4 space indent for wrapped text.
	1.  2 spaces after a numbered list.
		8-space indent for the wrapped text of a nested list.
	2.  Looks nice, don't it?
-   3 spaces after a bullet.
```



## Code blocks

*   Use the three tildes if you need to use three backticks inside the block:

	~~~markdown
	The simple shell command
	
	```shell
	for var in one two three; 
	do
		echo "Variable is $var"
	done
	```
	~~~

-   Use for space indenting for one line code block instead of three backticks:

	```markdown
	To find all directories without nested, use the find command:

		find . -maxdeph 1 -type d
	```

-   When the line before the code block provides a way to use it, finish that line with a colon:

	```markdown
	Please execute the following command:

		ls -lt|grep *.md
	```



## See also

* [Google Markdown Style Guide](https://google.github.io/styleguide/docguide/style.html)
