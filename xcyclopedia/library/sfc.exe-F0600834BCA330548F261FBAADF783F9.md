﻿---
title: sfc.exe | System Integrity Check and Repair
---

# sfc.exe 

* File Path: `C:\Windows\system32\sfc.exe`
* Description: System Integrity Check and Repair
* Comments: 

## Hashes

Type | Hash
-- | --
MD5 | `F0600834BCA330548F261FBAADF783F9`
SHA1 | `8D76F73ECBD6837424C1845FF3E3BFA09B16F79D`
SHA256 | `E7A57BE660B32AEBEC5C59786D9F56DE1DFB9E4BCE2B1AAEFEA94CAAC5C63E42`
SHA384 | `F0972D3556DC3B1B630799073C796EC76C6332458E757323E598ABAA908EC68FFBF055A48F9BF8D665ECA9B1288A6368`
SHA512 | `6F701FA28AF5D235A72337120510FC42CCAEE7DF654AC0D4E9DC14AC63DB6322C49A4D6CD2E63D74CE53FA34FDF735A08D15A0EBEE56DC4F9A9766493DA040E1`
SSDEEP | `1536:hO1eY5wNp9njw3I8QQ/Q/CZ2ujdQsGyhP:m35J/0j+GsP`

## Runtime Data

### Usage (stdout):
```Batchfile

Microsoft (R) Windows (R) Resource Checker Version 6.0
Copyright (C) Microsoft Corporation. All rights reserved.

Scans the integrity of all protected system files and replaces incorrect versions with 
correct Microsoft versions.

SFC [/SCANNOW] [/VERIFYONLY] [/SCANFILE=<file>] [/VERIFYFILE=<file>]
    [/OFFWINDIR=<offline windows directory> /OFFBOOTDIR=<offline boot directory> [/OFFLOGFILE=<log file path>]]

/SCANNOW        Scans integrity of all protected system files and repairs files with
                problems when possible.
/VERIFYONLY     Scans integrity of all protected system files. No repair operation is
                performed.
/SCANFILE       Scans integrity of the referenced file, repairs file if problems are
                identified. Specify full path <file>
/VERIFYFILE     Verifies the integrity of the file with full path <file>.  No repair
                operation is performed.
/OFFBOOTDIR     For offline repair, specify the location of the offline boot directory
/OFFWINDIR      For offline repair, specify the location of the offline windows directory
/OFFLOGFILE     For offline repair, optionally enable logging by specifying a log file path

e.g.

        sfc /SCANNOW
        sfc /VERIFYFILE=c:\windows\system32\kernel32.dll
        sfc /SCANFILE=d:\windows\system32\kernel32.dll /OFFBOOTDIR=d:\ /OFFWINDIR=d:\windows
        sfc /SCANFILE=d:\windows\system32\kernel32.dll /OFFBOOTDIR=d:\ /OFFWINDIR=d:\windows /OFFLOGFILE=c:\log.txt
        sfc /VERIFYONLY

```

### Usage (stderr):
```Batchfile

```

### Child Processes:


## Signature

* Status: Signature verified.
* Serial: `330000023241FB59996DCC4DFF000000000232`
* Thumbprint: `FF82BC38E1DA5E596DF374C53E3617F7EDA36B06`
* Issuer: CN=Microsoft Windows Production PCA 2011, O=Microsoft Corporation, L=Redmond, S=Washington, C=US
* Subject: CN=Microsoft Windows, O=Microsoft Corporation, L=Redmond, S=Washington, C=US

## File Metadata

* Original Filename: sfc.exe.mui
* Product Name: Microsoft Windows Operating System
* Company Name: Microsoft Corporation
* File Version: 10.0.19041.1 (WinBuild.160101.0800)
* Product Version: 10.0.19041.1
* Language: English (United States)
* Legal Copyright:  Microsoft Corporation. All rights reserved.



## Additional Info*

**The information below is copied from [MicrosoftDocs](https://github.com/MicrosoftDocs/windowsserverdocs), which is maintained by [Microsoft](https://opensource.microsoft.com/codeofconduct/). Available under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.*

---
## sfc

> Applies to: Windows Server (Semi-Annual Channel), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Scans and verifies the integrity of all protected system files and replaces incorrect versions with correct versions.


### Syntax
```
sfc [/scannow] [/verifyonly] [/scanfile=<file>] [/verifyfile=<file>] [/offwindir=<offline windows directory> /offbootdir=<offline boot directory>]
```

##### Parameters
|Parameter|Description|
|-------|--------|
|/scannow|Scans the integrity of all protected system files and repairs files with problems when possible.|
|/verifyonly|Scans integrity of all protected system files. No repair operation is performed.|
|/scanfile|Scans integrity of the specified file and repairs the file if problems are detected, when possible.|
|\<file>|Specified full path and filename|
|/verifyfile|verifies the integrity of the specified file. No repair operation is performed.|
|/offwindir|Specifies the location of the offline windows directory, for offline repair.|
|/offbootdir|Specifies the location of the offline boot directory for offline|
|/?|Displays help at the command prompt.|

### Remarks
-   You must be logged on as a member of the Administrators group to run **sfc.exe**.
-   if **sfc** discovers that a protected file has been overwritten, it retrieves the correct version of the file from the **systemroot\system32\dllcache** folder, and then replaces the incorrect file.
-   There are functional differences between **sfc** on Windows Server  2003,  Windows Server  2008 , and  Windows Server  2008 R2 :
-   for more information about **sfc** on Windows Server 2003, see [article 310747](https://go.microsoft.com/fwlink/?LinkId=227069) in the Microsoft Knowledge Base.
-   for more information about **sfc** on  Windows Server  2008 , and  Windows Server  2008 R2 , see [System File Checker](https://go.microsoft.com/fwlink/?LinkId=227071).

### Examples
To verify the **kernel32.dll file**, type:
```
sfc /verifyfile=c:\windows\system32\kernel32.dll
```
To setup offline repair of the **kernel32.dll** file with an offline boot directory set to **d:** and offline windows directory set to **d:\windows**, type:
```
sfc /scanfile=d:\windows\system32\kernel32.dll /offbootdir=d:\ /offwindir=d:\windows
```

### Additional References
- [Command-Line Syntax Key](https://github.com/MicrosoftDocs/windowsserverdocs/tree/master/WindowsServerDocs/administration/windows-commands/command-line-syntax-key.md)


---



MIT License. Copyright (c) 2020 Strontic.

