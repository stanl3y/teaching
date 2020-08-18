# grep: finding the lines you need

### outline
1. demo [link](https://repl.it/languages/bash)
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
> pwd
/home/runner/SiennaQuintessentialFunction
> ls .
main.sh  onefile.csv
> cat main.sh
echo Hello World
> mkdir workshop
> ls .
main.sh  onefile.csv  workshop
> cd workshop/
> pwd
/home/runner/SiennaQuintessentialFunction/workshop
> ls .
> cd ..
> pwd
/home/runner/SiennaQuintessentialFunction
```

- [tldr pages](https://tldr.ostera.io/)

```
> wget https://raw.githubusercontent.com/stanl3y/teaching/sm-workshop-grep/workshop-grep/sigma.txt
[...]

> echo "grep {{search_pattern}} {{path/to/file}}"
grep {{search_pattern}} {{path/to/file}}

> grep science sigma.txt 
SigmaCamp is a week-long math and science sleepaway camp
unique opportunity to learn math and science from
science research is like. We want to show them the 
interdependence of the sciences: Physics, Mathematics, 

> grep "math and science" sigma.txt 
SigmaCamp is a week-long math and science sleepaway camp
unique opportunity to learn math and science from

> grep -v a sigma.txt 
following in the footsteps of scientists from the time of 

> grep -c SigmaCamp sigma.txt 
4
> grep SigmaCamp sigma.txt
SigmaCamp is a week-long math and science sleepaway camp
for students 12-16 years old. SigmaCamp gives campers a
The goal of SigmaCamp is to ignite a spark of interest and
the SigmaCampers themselves.


> grep research sigma.txt 
science research is like. We want to show them the 

> grep -C1 research sigma.txt 
scientists who can give a first-hand account of what real 
science research is like. We want to show them the 
interdependence of the sciences: Physics, Mathematics, 
```

- [man pages](http://man.he.net/)

```
(pipes)  # composition

> grep science sigma.txt
SigmaCamp is a week-long math and science sleepaway camp
unique opportunity to learn math and science from
science research is like. We want to show them the 
interdependence of the sciences: Physics, Mathematics, 

> grep science sigma.txt | grep unique
unique opportunity to learn math and science from

> grep science sigma.txt | head -n2
SigmaCamp is a week-long math and science sleepaway camp
unique opportunity to learn math and science from

> grep science sigma.txt | head -n2 | wc -l
2
```

```
(redirection)

> head -n2 <sigma.txt
SigmaCamp is a week-long math and science sleepaway camp
for students 12-16 years old. SigmaCamp gives campers a

> head -n2 <sigma.txt >sigma_two_lines.txt
main.sh  sigma_two_lines.txt  sigma.txt
> cat sigma_two_lines.txt
SigmaCamp is a week-long math and science sleepaway camp
for students 12-16 years old. SigmaCamp gives campers a
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
