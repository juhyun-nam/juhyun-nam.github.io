# Symbol

| Symbol | Action |
|---|---|
| . | Match any character. |
| * | Match zero or more precedingcharacters. |
| ^ | Match beginning of line/string. |
| $ | Match end of line/string. |
| \ | Escape following character. |
| [ ] | Match one from a set. |
| \\( \\) | Store pattern for later replay. |
| \n | Replay subpattern in match. |
| { } | Match a range of instances. |
| \\{ \\} | Match a range of instances. |
| \< \> | Match word’s beginning or end. |
| + | Match one or more precedingcharacters. |
| ? | Match zero or one precedingcharacters. |
| \| | Separate choices to match. |
| () | Group expressions to match. |

# Globbing and Regex

| | Glob | Regex |
|--- | :---: | :---: |
| * | zero or more characters | zero or more of the character it follows |
| ? |	single occurrence of any character | zero or one of the character it follows but not more than 1 |
| . |	literal "." character | any single character |
| [...] | any one of the enclosed characters | any one of the enclosed characters |
| [^...] | any character not enclosed | any character not enclosed |
| [!...] | any character not enclosed | [...] |

# Basic vs Extended Regular Expressions

| BRE | ERE |
|---|---|
| \\? | ? |
| \\+ | + |
| \\{ | { |
| \\\| | \| |
| \\( | ( |
| \\) | ) |

| command | |
|---|---|
| ed | BRE |
| grep | BRE |
| sed | BRE |
| awk | ERE |
| egrep | ERE |

# sed

```
```

# awk

* $0 (entire input record)
* $n (nth field
* NF (number of fields)
* NR (number of the current record)

```
awk '/abc/ {print $1}' myfil
awk -F: '{print $1}' /etc/passwd
echo "Hello Tom" | awk '{$2="Adam"; print $0}'
```


# find

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
