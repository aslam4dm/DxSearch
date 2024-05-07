# DxSearch
This is designed to help make grepping easier for useful information, in a CTF or Pentest context, where you can easily specify what the path should contain or what the filename should contain. 
Currently not compatible with Windows 

Note: 
--file_contains (-fc) and --path_contains (-pc) default to ignoring the letter casing
--search (-s) is in the code to as input for the `grep` command, therefore you can supply grepable input. Additionally, within the code, by default grep is performed with the ignore-case (-i) flag
--path (-p) defaults to the current working directory '.'

Usage:
### file contains single // searches all files that contain 'user' for 'ctfuser1'
```
python dxsearch.py -fc user -s ctfuser1 -p /
```
### file contains multi input // searches all files that contain 'config, user or key' for 'password, pwd, username, uname or key'
```
python dxsearch.py -fc config,user,key -s "password\|pwd\|username\|uname\|key" -p "/home/user/Documnents"
```
### path contains single // searchers all files in paths that contain 'user' for 'ctfuser1' 
```
python dxsearch.py -pc user -s ctfuser1 -p /
```
### path contains multi input // searchers all files in paths that contain 'log, backup or storage' for 'password, pwd, username, uname or key'
```
python dxsearch.py -pc log,backup,storage -s "password\|pwd\|username\|uname" -p "/home/user/Documnents"
```
### file contains and path contains // searches file that contain filename 'fb' within paths that contain 'socm' 
```
python dxsearch.py -pc socm -fc fb -s "username" -p /
```
