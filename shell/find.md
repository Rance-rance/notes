## find command
[Link Address](https://help.ubuntu.com/community/find)

The GNU find commands is part of the GNU findutils and is installed on every Ubuntu system. findutils is actually made up of 4 utilities.
  * find
  * locate
  * updatedb
  * xargs

### locating files by name
```shell
find $HOME -name 'readme.txt'

find $HOME -iname '*.txt'

sudo find / -iname '*.txt'
```

### locating files by size

```shell
find $HOME -iname '*.txt' -size +100M

find $HOME -iname '*.txt' -type f -size -100M
```

### locating files by access time

```shell
# show all files that have not been accessed in the $Home directory for 30 days or more
find $HOME -atime +30

find $HOME -iname '*.txt' -atime +30
```