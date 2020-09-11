# Linux Command 정리

man으로 정리 되지 않는, 혼동되거나 잊기 쉬운 옵션 혹은 예제들

## Globbing and Regex

| | Glob | Regex |
|--- | :---: | :---: |
| * | zero or more characters | zero or more of the character it follows |
| ? |	single occurrence of any character | zero or one of the character it follows but not more than 1 |
| . |	literal "." character | any single character |
| [...] | any one of the enclosed characters | any one of the enclosed characters |
| [^...] | any character not enclosed | any character not enclosed |
| [!...] | any character not enclosed | [...] |

## Bash
### Bash Shell Features
* Brace Expansion
* Tilde Expansion
* Shell Parameter Expansion
* Command Substitution
* Arithmetic Expansion
* Process Substitution
* Word Splitting
* Filename Expansion
* Quote Removal

```
echo a{d,c,b}e
ls lib/{ex?.?*, edit}
echo {1..10}
echo {1..10..2}
echo {01..10..2}

cd ~ # $HOME
cd ~-/foo # ${OLDPWD}/foo
cd ~N # dirs +N
cd ~-N # dirs -N

$(command)
`command`
$(( expression ))

# If the extglob shell option is enabled using the shopt builtin
?(pattern-list) # Matches zero or one occurrence of the given patterns.
*(pattern-list) # Matches zero or more occurrences of the given patterns.
+(pattern-list) # Matches one or more occurrences of the given patterns.
@(pattern-list) # Matches one of the given patterns.
!(pattern-list) # Matches anything except one of the given patterns.
```

### Job Control

|jobspec||
|---|---|
| % | current job |
| %n | job number n |
| %- | previous job |
| %ce | ce job |
| %?ce | job containing the string ce |

```
%1 # synonym for fg %1
%1 & # synonym for bg %1
jobs
jobs -l
kill %1
wait %1
```


### Command Line Editing
|Command||
|---|---|
| C-arrow | move forward/backword a word |
| C-a | Move to the start of the line.|
| C-e | Move to the end of the line. |
| C-w | Kill from the cursor to the previous whitespace. |
| C-u | Kill backward from the cursor to the beginning of the current line. |
| C-k | Kill the text from point to the end of the line. |
| C-y | Yank the most recently killed text back into the buffer at the cursor. |
| C-r | search backword in the history |
| C-s | search forward in the history |
| C-g | abort an incremental search and restore the original line. |

### Using History Interactively

|Command||
|---|---|
| !! | !-1 |
| !string | most recent command starting with string |
| !?string | most recent command containing string |
| ^string1^string2^ | !!:s/string1/string2/ |
| !!:$ | last argument of the preceding command. |
| !$ | !!:$ |
| !fi:2 | second argument of the most recent command starting with the letters fi. |

## Pattern Matching

| Symbol | ed | ex | vi | sed | gawk | grep | egrep | Action |
|---|---|---|---|---|---|---|---|---|
| . | • | • | • | • | • | • | • | Match any character. |
| * | • | • | • | • | • | • | • | Match zero or more precedingcharacters. |
| ^ | • | • | • | • | • | • | • | Match beginning of line/string. |
| $ | • | • | • | • | • | • | • | Match end of line/string. |
| \ | • | • | • | • | • | • | • | Escape following character. |
| [ ] | • | • | • | • | • | • | • | Match one from a set. |
| \\( \\) | • | • | • | • | | • | | Store pattern for later replay. |
| \n | • | • | • | • | | • | | Replay subpattern in match. |
| { } | | | | | •P | | •P | Match a range of instances. |
| \\{ \\} | • | | | • | | • | | Match a range of instances. |
| \< \> | • | • | •| | | | | Match word’s beginning or end. |
| + | | | | | • | | • | Match one or more precedingcharacters. |
| ? | | | | | • | | • | Match zero or one precedingcharacters. |
| \| | | | | | • | | • | Separate choices to match. |
| () | | | | | • | | • | Group expressions to match. |                                                

**Basic vs Extended Regular Expressions**

| grep | egrep |
|---|---|
| \\? | ? |
| \\+ | + |
| \\{ | { |
| \\| | \| |
| \\( | ( |
| \\) | ) |

## sed

addressing
| Command | Action performed |
| --- | --- |
| s/xx/yy/g | Substitute on all lines (all occurrences). |
| /BSD/d | Delete lines containing BSD. |
| /^BEGIN/,/^END/p | Print betweenBEGIN andEND, inclusive.
| /SAVE/!d | Delete any line that doesn’t containSAVE.
| /BEGIN/,/END/!s/xx/yy/g | Substitute on all lines, except betweenBEGIN andEND.|

```
sed 's/unix/linux/' geekfile.txt
sed 's/unix/linux/g' geekfile.txt
sed '3 s/unix/linux/' geekfile.txt
sed 's/unix/linux/p' geekfile.txt
sed '/pattern/d' filename.txt
```

## awk

* $0 (entire input record)
* $n (nth field
* NF (number of fields)
* NR (number of the current record)

```
awk '/abc/ {print $1}' myfil
awk -F: '{print $1}' /etc/passwd
echo "Hello Tom" | awk '{$2="Adam"; print $0}'
```
## find

* find는 linux pattern을 사용
* find의 옵션은 99% single dash (-)
* -name에서 regex 쓰고 싶다면, -regex
* grep은 line에서 pattern을 찾아내지만, find는 각 아이템이 pattern에 정확히 일치해야 한다.
  * file의 중간 부분에서 시작하는 패턴으로 매칭 불가.
* -path
* -maxdepth

```
find . -name 'fi*'
# find . -name 'fi.*'
# find . --nam 'fi*'
find . -regex 'fi.*'
find . -path './subdirectory/fi*'
```

## 필수 명령어
* ls
* file
* less
* mkdir
* cp
* mv
* rm
* ln
* type
* which
* man
* info
* whatis
* alias
* cat
* sort
* uniq
* wc
* grep
* head
* tail
* tee
* echo
* history
* id
* chmod
* umask
* su
* sudo
* chown
* chgrp
* passwd
* ps
* top
* jobs
* bg
* fg
* kill
* vmstat
* printenv(env)
* set
* export
* apt, yum
* ping
* netstat
* curl, wget
* ssh
* scp
* sftp
* locate
* find
* xargs
* touch
* stat
* gzip
* tar
* zip
* paste
* join
* diff
* patch
* sed
* awk
* tree
* mkfifo
* trap
* wait
