# grep: finding the lines you need

### outline
1. demo
2. exercises

### cheatsheet

```
(navigation) pwd, ls, cd, mkdir
(useful) grep
(tricks) head, tail, wc -l
(further reading) less -S, sort, uniq, cat

tldr: https://tldr.ostera.io/
man: `man grep` or man.he.net
```

### demo
```
(grep)

grep keyword
grep "two words"
grep --inverse
grep --count

grep --context
```

```
(pipes)
grep xy example-file | head -n4
grep xy example-file | wc -l
```

```
(redirection)
```

### docs
### grep


### exercises (finally)
- prerequisites:
  - repl.it online environment with `onefile.csv`
  - copy of [Puzzle](https://docs.google.com/spreadsheets/d/11DTy6yZE3u2LqXdtTCnPEkvXgRDH9cpUZMbSH4w8hcQ/edit?usp=sharing)


- remarks:
  - header row: `grep header onefile.csv`
  - use head to preview: `head -n4 < onefile.csv` or `grep Olympics onefile.csv | head -n4`
  - careful with cASe
  - shortlists are reasonable

- more remarks
  - tab-completion
  - Ask for Help button in break-out rooms


```
(datafiles)

[literature]
[companies]
[countries]
[NYC-galleries]
[nobel-prizes]
[Olympics]
[colleges]
[us-presidents]
```

__disclaimer__: the information in the datafiles may be incomplete and/or incorrect -- they are merely meant to provide exercises for this workshop, NOT to serve as a truthful/reliable source of information


### exercises-setup
- [repl.it](https://repl.it/languages/bash)

```
> pwd
> ls
> wget https://raw.githubusercontent.com/stanl3y/teaching/sm-workshop-grep/workshop-grep/onefile.csv
> ls
```

```
> pwd
/home/runner/SiennaQuintessentialFunction
> ls
main.sh
> wget https://raw.githubusercontent.com/stanl3y/teaching/sm-workshop-grep/workshop-grep/onefile.csv
--2020-08-18 12:29:25--  https://raw.githubusercontent.com/stanl3y/teaching/sm-workshop-grep/workshop-grep/onefile.csv
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.0.133, 151.101.64.133, 151.101.128.133, ...
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|151.101.0.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2526724 (2.4M) [text/plain]
Saving to: ‘onefile.csv’

onefile.csv                               100%[=====================================================================================>]   2.41M  14.9MB/s    in 0.2s    

2020-08-18 12:29:26 (14.9 MB/s) - ‘onefile.csv’ saved [2526724/2526724]

> ls
main.sh  onefile.csv
```


- Puzzle template [link](https://docs.google.com/spreadsheets/d/11DTy6yZE3u2LqXdtTCnPEkvXgRDH9cpUZMbSH4w8hcQ/edit?usp=sharing)
