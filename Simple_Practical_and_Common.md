# Simple, Practical, and Common

[`vimgolf put 55b18bbea9c2c30d04000001`](http://vimgolf.com/challenges/55b18bbea9c2c30d04000001)

## Start file

```
*temp var1 0
*temp var2 "hi"
*temp var3 -1
*temp var4 42
*temp var5 "asdf"
*temp var6 0

Simple things we do all the time should be able to be done with very few keystrokes, but sometimes I find something I need to do makes me go, "There MUST be a better way."

This challenge is just a simple movement and entering text at a certain place.
```


## End file

```
*temp var1 0
*temp var2 "hi"
*temp var3 -1
*temp var4 42
*temp var5 "asdf"
*temp var6 0
*temp var7 11

Simple things we do all the time should be able to be done with very few keystrokes, but sometimes I find something I need to do makes me go, "There MUST be a better way."

New text.

This challenge is just a simple movement and entering text at a certain place.
```

## Solution

`6GYp<C-A>w11<C-A>GONew text.<CR><Esc>ZZ`     Score:24

`6GYp<C-A>w11<C-A>GONew te<C-N>.<CR><Esc>ZZ`  Score:23

`#Yp<C-A>w11.GONew t<C-N><C-N>.<CR><Esc>ZZ`  Score:22


### Move down

`5j` Move down to line var6

`6G` Go to line 6

`#` Here # equivalent to 6G, search backward, start from bottom and find line 6


### Copy and paste

`Yp` yank line and put


### Increase count

`<C-a>` increase 6 to 7

`w` move to next word

`[count]CTRL-A` increase by count [count], in this case count = 11


### Move

`GO` Go to end and Open a line above

`}}` Goto next paragraph twice


### Start typing

`New te<C-N>.<CR>` Use completion(C-N)