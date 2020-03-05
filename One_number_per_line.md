# Simple, Practical, and Common

[`vimgolf put 56fb2e75ccffcc0009026473`](http://vimgolf.com/challenges/56fb2e75ccffcc0009026473)

## Start file

```
- One number per line -
-----------------------
2,3,5,7,
11,13,17,
19,23,29,
```


## End file

```
2
3
5
7
11
13
17
19
23
29
```

## Solution #1

`2D:%s/,/\r/g<CR>:g/^$/d<CR>ZZ`  Score:23

`2DgJ.:s/,/\r/g<CR>ddZZ`  Score:22

`2D3gJ:s/,/\r/g|d<CR>ZZ`    Score:22

`dj3gJ:s/,/\r/g|d|x<CR>`    Score:22


### Delete first two lines

`dj`  d{motion} delete, j moves down one line

`2D`  D delete the character under the cursor until the end of line and [count]-1 more lines

### Join all lines together without space

`JxJx` : Join and delete the extra character twice

`gJ.` Joins three lines together without space

`3gJ` Same as above


### Replace , with new line

`:s/,/\r/g` sed like replacement

`:s/,/<C-V><CR>/g` same as above but inserts a control character

### delete last line

`dd`,but `D` doesn't work here

pipe `|d` will delete the last line

pipe `|x` will quit, don't need `ZZ`


## Solution #2

`djgJ.$x:s/,/\r/g|x<CR>`    Score:22

could delete before substitution, but same score


## Solution #3

2D3gJIwr<CR><Esc>u9@.$xZZ 18
dj3JIwr<CR><Esc>u9@.$xZZ  17


## Solution #4

dj3gJV"=[<C-R><C-A>]<CR>pZZ 16
dj3JV"=[<C-R><C-L>]<CR>pZZ 15
5gJV"=[<C-R><C-A>]<CR>pZZ 14

[explain](http://vi.stackexchange.com/questions/13602/the-meaning-of-in-vim)
