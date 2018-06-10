# I forgot quotes

[`vimgolf put 5462e3f41198b80002512673`](http://vimgolf.com/challenges/5462e3f41198b80002512673)

## Start file

```
foo = a
      ab
      abc
```


## End file

```
foo = "a"
      "ab"
      "abc"
```

## Solution #1

`:%s/a.*/“&”/<CR>ZZ` Score:15

One time subsitution, `&` equivalent to `\0`, no need `/g`


## Solution #2

`A"<Esc>j.j.b<C-V>kkI”<Esc>ZZ` Score:16

Append quotes, repeat down. Visual insert(Capital I) and repeat back up

PS: Capital `I`, Visual insert, apply to all lines after `<Esc>`


## Solution #3

`$<C-V>GI"<Esc>gv$A"<Esc>ZZ` Score:14

Select end of line, insert before words. Reselect to EOL, append quotes.

PS: `gv` reselect previous area


## Solution #4

`ta<C-V>jjA"<Esc>$.ZZ` Score:12

Append just after visual select, then repeat at EOL. Have to use `jj` goto bottom, `G` doesn’t work


## Solution #5

`<C-V>GhA"<Esc>$.ZZ` Score:10

Block select, back one char(`h`), append, then repeat at EOL.