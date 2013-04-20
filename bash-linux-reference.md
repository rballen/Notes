
bash-linux reference
====================================
`#!/bin/bash`

#### Resources

* http://www.commandlinefu.com/commands/browse


#### command vs expression

!space is important! 
```bash
grep -q "$text" is a command

filelist=`ls | grep -i '.jpg'`  is a command

filelist = `ls | grep -i '.jpg'` is an error - bash will execute filelist as a command 
```

#### for loop 
```sh
for f in $(ls); do
     echo "$f"
done
```
or 

```sh
for OUTPUT in $(Unix-Command)
do
  command1 on $OUTPUT
done
```

**examples**

```bash
for i in {1..5}
for (( c=1; c<=5; c++ ))
for (( ; ; ))     # infinite loop  use break  to exit   
for f in /path/to/dir/*.txt
for file in /etc/*
```

#### if

`test` and `[` are equivelent builtins commands i.e.

`if [ "$name" = 'Bob' ]; then ...`

**same as**

`if test "$name" = 'Bob'; then ...`


**examples**

```bash
if [ "${file}" == "/etc/resolv.conf" ]
if [ -f ${f}.bak ]     # file exists
[ -f "$f" ] && rm "$f"  # if file exits, delete it - can be written as ... if test 
```
