# Powershell Commands
## Create a File
**Syntax:** `New-Item -Path "<filepath-and-name>" -ItemType <filetype> -Name "file"`

**Example:**
```powershell
New-Item -Path . -Name "text.txt" -ItemType file
``` 

## Create a Directory

**Syntax:** `New-Item -Path <filepath> -Name <file-name> -ItemType "directory"`

**Example:**
```powershell
New-Item -Path . -Name "test-dir" -ItemType "directory"
```


## Delete Everything in a File and the File

**Syntax:** `Remove-Item `<filepath>` -Recurse -Force`

**Example:**
```ps
Remove-Item -Path "test-dir" -Recurse -Force
```