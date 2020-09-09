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

## Redirection

```
ls -l /bin/usr 2> ls-error.txt
ls -l /bin/usr &> ls-output.txt
ls -l /bin/usr 2> /dev/null

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
