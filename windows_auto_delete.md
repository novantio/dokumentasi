# definition 
for automated deleted files after serveral days

# command
save in .bat
```
forfiles -p "C:\tmpdata" -s -m *.* /D -1 /C "cmd /c del @path"
```
