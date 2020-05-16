# Unix

### Grep
Grep is an acronym that stands for Global Regular Expression Print.
The grep command consists of three parts in its most basic form. The first part starts with grep, followed by the pattern that you are searching for. After the string comes the file name that the grep searches through.

#### To Search a File
```bash
 grep access file.txt
 ```
 Result:
 ```
 u (user)	  + (add access)	     r (read)
 g (group)	  - (remove access)	     w (write)
 o (other)	  = (set exact access)	     x (execute)
 ```
#### Search All Files in Directory
 ```bash
 grep access *
 ```
 Result
 ```
 file.txt: u (user)	  + (add access)	     r (read)
file.txt: g (group)	  - (remove access)	     w (write)
file.txt: o (other)	  = (set exact access)	     x (execute)
file2.txt:access is there in file2.txt
grep: folder: Is a directory
grep: new_folder: Is a directory
grep: p12: Is a directory
grep: permission: Is a directory
 ```
#### To Find Whole Words
 ```bash
 grep -w access *
 ```
#### To Ignore Case in Grep Searches
 ```bash
 grep  -i Access *
 ```
#### To Search Subdirectories
 ```
 grep -r access *
 ```
#### To show Exactly Match
 ```bash
 grep  -x "access is there in file2.txt" *
```
#### To List Names of Matching Files
```bash
grep -l access *
```
#### To Count number of matched
```bash
grep -c access *
```
#### To Limit grep Output
```bash
grep -m1  access *
```
[Back to Index](README.md)