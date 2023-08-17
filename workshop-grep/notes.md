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

tldr: https://tldr.sh/
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

- [tldr pages](https://tldr.sh/)

```
> curl -O https://raw.githubusercontent.com/stanl3y/teaching/sm-workshop-grep/workshop-grep/sigma.txt
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

### exercises (finally)
- prerequisites:
  - repl.it online environment with `onefile.csv`
  - copy of [Puzzle](https://docs.google.com/spreadsheets/d/11DTy6yZE3u2LqXdtTCnPEkvXgRDH9cpUZMbSH4w8hcQ/edit?usp=sharing)


- remarks:
  - about datafiles
  - header row: `grep header onefile.csv`
  - use head to preview: `head -n4 < onefile.csv` or `grep Olympics onefile.csv | head -n4`
  - careful with cASe
  - shortlists are reasonable

- more remarks
  - tab-completion
  - Ask for Help button in break-out rooms


```
(datafiles)

[literature] a random selection of ~2000 books
[companies] Forbes Global 2000 (from 2018)
[countries] countries of the world
[NYC-galleries] a list of galleries in NYC
[nobel-prizes]
[Olympics] medalists by sport (abridged)
[colleges] a non-definitive list of US colleges
[us-presidents]
```

__disclaimer__: the information in the datafiles may be incomplete and/or incorrect -- they are merely meant to provide exercises for this workshop, NOT to serve as a truthful/reliable source of information


### exercises-setup
- [repl.it](https://repl.it/languages/bash)

```
> pwd
> ls
> curl -O https://raw.githubusercontent.com/stanl3y/teaching/sm-workshop-grep/workshop-grep/onefile.csv
> ls
```

```
> pwd
/home/runner/SiennaQuintessentialFunction
> ls
main.sh
> curl -O https://raw.githubusercontent.com/stanl3y/teaching/sm-workshop-grep/workshop-grep/onefile.csv
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--100 2467k  100 2467k    0     0  22.1M      0 --:--:-- --:--:-- --:--:-- 22.3M

> ls
main.sh  onefile.csv
```


- Puzzle template [link](https://docs.google.com/spreadsheets/d/11DTy6yZE3u2LqXdtTCnPEkvXgRDH9cpUZMbSH4w8hcQ/edit?usp=sharing)
