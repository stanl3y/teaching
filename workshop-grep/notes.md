# grep: finding the lines you need

### outline
- docs
- explain grep (with examples)
- explain redirection & pipes
- exercises

### cheatsheet

```
(navigation) pwd, ls, cd, mkdir
(useful) grep, less
(sort-me) which, head, tail, 

tldr: https://tldr.ostera.io/
man: `man grep` or man.he.net
```
```
grep
grep --inverse
grep --count

grep --context
```

### docs
### grep
### exercises
- [repl.it](https://repl.it/languages/bash)

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

```
wget [...]
```


