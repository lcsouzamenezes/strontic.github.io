﻿---
title: OpenWith.exe | Pick an app
---

# OpenWith.exe 

* File Path: `C:\Windows\system32\OpenWith.exe`
* Description: Pick an app
* Comments: 

## Hashes

Type | Hash
-- | --
MD5 | `49371805F24C419A1362A6672F0A8A76`
SHA1 | `4B1EF77551590D53BADBE757687C44588474559E`
SHA256 | `9CF635BE9BE023F6A24E885B369F7906EFF772AC9E6D8C496D5D9786D4018745`
SHA384 | `61C77B9897AA73648BAFE8410A8870D6D681628D7E78A31261FBBEFDFB77D532E99FDC575356001CBCF85D31396292E3`
SHA512 | `E065CC6292BAE0B2F0F58513594D35A182B2B61CDB5D215EFE784E3689A273777307AD3A572BF43B3BEB588804CDF9973E92339C0758D1B5629541B3714059E0`
SSDEEP | `1536:B6YmJompoZOQ76froDbm4w63ijMYoOeAjEyPzI0fKQTzBNer+CE+Ge+cPZ:h96MDbu1oOeAhcorer+CE+GOh`

## Runtime Data

### Usage (stdout):
```Batchfile

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

* Original Filename: OpenWith.exe.mui
* Product Name: Microsoft Windows Operating System
* Company Name: Microsoft Corporation
* File Version: 10.0.19041.1 (WinBuild.160101.0800)
* Product Version: 10.0.19041.1
* Language: English (United States)
* Legal Copyright:  Microsoft Corporation. All rights reserved.

## File Similarity (ssdeep match)

File | Score
-- | --
[C:\WINDOWS\system32\OpenWith.exe](OpenWith.exe-C9B3F7E1EB1970A715FA56AB076A260B.md) | 50
[C:\Windows\system32\OpenWith.exe](OpenWith.exe-FEAEEC585FEA59A316DDDD6C8505DA8D.md) | 46
[C:\Windows\SysWOW64\OpenWith.exe](OpenWith.exe-64148E3F7B8519DCB04FE5E96D5F1184.md) | 41
[C:\Windows\SysWOW64\OpenWith.exe](OpenWith.exe-A633739DA182E75C0D6741119A902A0B.md) | 43
[C:\WINDOWS\SysWOW64\OpenWith.exe](OpenWith.exe-FADC6187E347B4820DA5B907B45F6024.md) | 43

## Possible Misuse

*The following table contains possible examples of `OpenWith.exe` being misused. While `OpenWith.exe` is **not** inherently malicious, its legitimate functionality can by abused for malicious purposes.*

Source | Source File | Example | License
-- | -- | -- | --
[sigma](https://github.com/Neo23x0/sigma) | [win_susp_openwith.yml](https://github.com/Neo23x0/sigma/blob/master/rules/windows/process_creation/win_susp_openwith.yml) | `title: OpenWith.exe Executes Specified Binary` | [DRL 1.0](https://github.com/Neo23x0/sigma/blob/master/LICENSE.Detection.Rules.md)
[sigma](https://github.com/Neo23x0/sigma) | [win_susp_openwith.yml](https://github.com/Neo23x0/sigma/blob/master/rules/windows/process_creation/win_susp_openwith.yml) | `description: The OpenWith.exe executes other binary` | [DRL 1.0](https://github.com/Neo23x0/sigma/blob/master/LICENSE.Detection.Rules.md)
[sigma](https://github.com/Neo23x0/sigma) | [win_susp_openwith.yml](https://github.com/Neo23x0/sigma/blob/master/rules/windows/process_creation/win_susp_openwith.yml) | `    - https://github.com/LOLBAS-Project/LOLBAS/blob/master/yml/LOLUtilz/OSBinaries/Openwith.yml` | [DRL 1.0](https://github.com/Neo23x0/sigma/blob/master/LICENSE.Detection.Rules.md)
[sigma](https://github.com/Neo23x0/sigma) | [win_susp_openwith.yml](https://github.com/Neo23x0/sigma/blob/master/rules/windows/process_creation/win_susp_openwith.yml) | `        Image\|endswith: '\OpenWith.exe'` | [DRL 1.0](https://github.com/Neo23x0/sigma/blob/master/LICENSE.Detection.Rules.md)
[sigma](https://github.com/Neo23x0/sigma) | [win_susp_openwith.yml](https://github.com/Neo23x0/sigma/blob/master/rules/windows/process_creation/win_susp_openwith.yml) | `    - Legitimate use of OpenWith.exe by legitimate user` | [DRL 1.0](https://github.com/Neo23x0/sigma/blob/master/LICENSE.Detection.Rules.md)
[LOLBAS](https://github.com/LOLBAS-Project/LOLBAS) | [Openwith.yml](https://github.com/LOLBAS-Project/LOLBAS/blob/master/yml/LOLUtilz/OSBinaries/Openwith.yml) | `Name: Openwith.exe` | 
[LOLBAS](https://github.com/LOLBAS-Project/LOLBAS) | [Openwith.yml](https://github.com/LOLBAS-Project/LOLBAS/blob/master/yml/LOLUtilz/OSBinaries/Openwith.yml) | `  - Command: OpenWith.exe /c C:\test.hta` | 
[LOLBAS](https://github.com/LOLBAS-Project/LOLBAS) | [Openwith.yml](https://github.com/LOLBAS-Project/LOLBAS/blob/master/yml/LOLUtilz/OSBinaries/Openwith.yml) | `  - Command: OpenWith.exe /c C:\testing.msi` | 
[LOLBAS](https://github.com/LOLBAS-Project/LOLBAS) | [Openwith.yml](https://github.com/LOLBAS-Project/LOLBAS/blob/master/yml/LOLUtilz/OSBinaries/Openwith.yml) | `  - c:\windows\system32\Openwith.exe` | 
[LOLBAS](https://github.com/LOLBAS-Project/LOLBAS) | [Openwith.yml](https://github.com/LOLBAS-Project/LOLBAS/blob/master/yml/LOLUtilz/OSBinaries/Openwith.yml) | `  - c:\windows\sysWOW64\Openwith.exe` | 



MIT License. Copyright (c) 2020 Strontic.

