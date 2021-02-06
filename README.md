# Find-Memento

A memento about the find command, a very useful research tool

Find is a program taht lets us search files in a folder tree. It is installed normally in every Linux distros.
It has lots of options, basically you can find every file your want with the find command.

## Basic use cases

The command find is generally used with this scheme :  
'find /folder -options ...'

### Simple search

Simple one :  
`find /home`

>List all the files in the directory /home
>We can't see files that we don't have access
>It lists even the files in the subdirectory

Search in our actual path :
`find .`

Search by name :  
`find / -name "test.txt"`
> It is case sensitive

Search by extension :
`find / -name "*.txt"`

>It can be mixed with special characters :
> tes?.txt

Search all files which contain the name :  
`find / -name "*test*"`

Search isensitive case :
`find / -iname "test.txt"`

Search only files :  
`find / -type f -iname "test.txt"`

Search only directories :  
`find / -type d -iname "test.txt"`

Search by size :  
`find /boot -size +10M`  
`find /boot -size -10M`  
> All the options can be mixed  
`find /boot -size +10M -size -20M`

### Advanced search

#### Time

Search by access date :
`find / -atime -1`
> Files accessed less than a day  
Exact date :  
`find / -atime 1`

More than a day :  
`find / -atime +1`

Created time :
`find / -ctime -1`

Modified time :
`find / -mtime +1`

Time in minute :  
`find / -amin -1`

#### Users

Search all files created by a user :  
`find / -user userName`

With uid :
`find / -uid userId`

Search with group :  
`find / -group groupName`

With gid :
`find / -gid groupId`

### Search with execution

`find / -exec command {} \;`
`find / -exec command {} +`

## Remove permissions errors

`find / 2>/dev/null`

## Find empty files

`find / -empty`

## Permissions search

`find / -type f -perm 777`

List file with suid (extended permissions) :  
`find / -perm /u=s -exec ls -la {} \;`

___
Updated : 18/01/2021
Author : AnthonyF
