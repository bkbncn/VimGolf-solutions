# prepend * to every non-blank line

[`vimgolf put 5e4dfcccaa2db400090b66c3`](http://vimgolf.com/challenges/5e4dfcccaa2db400090b66c3)

## Start file

```
This is a
very short

file, but it is
still
full

of

surpises.
```


## End file

```
*This is a
*very short

*file, but it is
*still
*full

*of

*surpises.
```

## Solution #1

`:g/./norm I*<CR>ZZ` Score:15

`:g/^\w/norm I*<CR>ZZ` Score:17

Find the line stats with any character, and inset * at the beginning.


## Solution #2

`<C-V>GI*<Esc>:%s/*$//<CR>ZZ` Score:16

Insert * at beginning of every line and remove * following with empty line.


## Solution #3

`:%s/^\ze./*<CR>ZZ` Score:14

`:%s/^\ze\w/*<CR>ZZ` Score:15

Match the beginning of a line with any character, and subsitute with *.

```
\ze	Matches at any position, and sets the end of the match there: The
	previous char is the last char of the whole match.
```

`\zs` doesn't work, which will replace the first character with *.


## Solution #4

`:%s/./*&<CR>ZZ` Score:11

`:%s/^./*&/<CR>ZZ` Score:12

 `&` means the whole matched pattern, same as `/0`


## Solution #5

`:g/./s/^/*<CR>ZZ` Score:13

Find the line stats with any character, and replace the beginning with *.


## Solution #6

`<C-V>GyPgvr*ZZ` Score:10

Copy first character of each line at the beginning, reselect them and replace with *
