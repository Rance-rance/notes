# socat 
[Link Address](https://www.redhat.com/sysadmin/getting-started-socat)

```shell
socat TCP4-LISTEN:<PORT>,fork TCP4:<IP>:<PORT>
```

# ss(Socket Statistics)

```shell
sudo ss -tulpn
```

# find
[Link Address](https://help.ubuntu.com/community/find)

The GNU find commands is part of the GNU findutils and is installed on every Ubuntu system. findutils is actually made up of 4 utilities.
  * find
  * locate
  * updatedb
  * xargs

## locating files by name
```shell
find $HOME -name 'readme.txt'

find $HOME -iname '*.txt'

sudo find / -iname '*.txt'
```

## locating files by size

```shell
find $HOME -iname '*.txt' -size +100M

find $HOME -iname '*.txt' -type f -size -100M
```

## locating files by access time

```shell
# show all files that have not been accessed in the $Home directory for 30 days or more
find $HOME -atime +30

find $HOME -iname '*.txt' -atime +30
```

# grep
[Link Address](https://help.ubuntu.com/community/grep)

Grep is a command-line tool that allows you to find a string in a file or stram. It can be used with a regular expression to be more flexible ai finding strings.

## how to use

```shell
grep 'abc' filename

# this command searches all files in the current directory for the name and lists all lines that contain a match
grep 'abc' *
```
# tar
command|description
-|-
C|compress
x|decompress
v|show progress
f|filename
t|view compressed file content
j|compress to bzip2
z|compress to gzip
r|append dir or file to compressed file
W|verify compressed file

```shell
# compress /xxx/ to xxx.tar
tar -cvf xxx.tar /dir/

# compress /xxx/ to xxx.tar.gz
tar -czvf xxx.tar.gz /xxx/
```

```shell
# extract from xxx.tar
tar -xvf xxx.tar.gz

# extract from xxx.tar.gz
tar -zxvf xxx.tar.gz

#extract from xxx.tar.gz to /xxx/
tar -zxvf xxx.tar.gz -C /xxx/
```
