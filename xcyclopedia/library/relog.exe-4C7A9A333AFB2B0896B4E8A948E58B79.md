﻿---
title: relog.exe | Performance Relogging Utility
---

# relog.exe 

* File Path: `C:\windows\system32\relog.exe`
* Description: Performance Relogging Utility
* Comments: 

## Hashes

Type | Hash
-- | --
MD5 | `4C7A9A333AFB2B0896B4E8A948E58B79`
SHA1 | `948FEBD5456420916256FCC94E3ED19AAFE5390B`
SHA256 | `100AF46C952E58105DBC51EB92510F6990377A3FFC57E82074A8BFB64C56C529`
SHA384 | `01D078341EF753B90A6737429F665524C16F1CED299F33048EB7B285BFEB66E3F2384B307218DF78BA0FEF3CC7B6B6CC`
SHA512 | `2FBB960AAA2322F0BD5BC14096F9640F0AEAD480BEAB9DF687837516B7EE898E1A2B3C14FFD34BA663B0F11AC1B4B0EA81850AC92176903F324D38D1BADD872D`
SSDEEP | `768:mC+N6nlPSz0JPC/3c6f7Jl1/zdBNZj99mNUkiyDvkejoLWoe3F22Ms/qc/:7+HMUl5zbNB99mNUkiy4KWWTF2U/qc/`

## Runtime Data

### Usage (stdout):
```Batchfile

Microsoft r Relog.exe (10.0.17763.1)

Relog creates new performance logs from data in existing performance logs by
changing the sampling rate and/or converting the file format. Supports all
performance log formats, including Windows NT 4.0 compressed logs.

Usage:
C:\windows\system32\relog.exe <filename [filename ...]> 
                                [options]

Parameters:
  <filename [filename ...]>     Performance file to relog.

Options:
  -?                            Displays context sensitive help.
  -a                            Append output to the existing binary file.
  -c <path [path ...]>          Counters to filter from the input log.
  -cf <filename>                File listing performance counters to filter
                                from the input log. Default is all counters
                                in the original log file.
  -f <CSV|TSV|BIN|SQL>          Output file format.
  -t <value>                    Only write every nth record into the output
                                file. Default is to write every record.
  -o                            Output file path or SQL database.
  -b <M/d/yyyy h:mm:ss[AM|PM]>  Begin time for the first record to write into
                                the output file.
  -e <M/d/yyyy h:mm:ss[AM|PM]>  End time for the last record to write into
                                the output file.
  -config <filename>            Settings file containing command options.
  -q                            List performance counters in the input file.
  -y                            Answer yes to all questions without prompting.

Examples:
  relog logfile.csv -c "\Processor(_Total)\% Processor Time" -o logfile.blg
  relog logfile.blg -cf counters.txt -f bin
  relog logfile.blg -f csv -o logfile.csv -t 2
  relog logfile.blg -q -o counters.txt

```

### Usage (stderr):
```Batchfile

```

### Child Processes:
mmc.exe

## Signature

* Status: Signature verified.
* Serial: `33000001C422B2F79B793DACB20000000001C4`
* Thumbprint: `AE9C1AE54763822EEC42474983D8B635116C8452`
* Issuer: CN=Microsoft Windows Production PCA 2011, O=Microsoft Corporation, L=Redmond, S=Washington, C=US
* Subject: CN=Microsoft Windows, O=Microsoft Corporation, L=Redmond, S=Washington, C=US

## File Metadata

* Original Filename: Relog.exe.mui
* Product Name: Microsoft Windows Operating System
* Company Name: Microsoft Corporation
* File Version: 10.0.17763.1 (WinBuild.160101.0800)
* Product Version: 10.0.17763.1
* Language: English (United States)
* Legal Copyright:  Microsoft Corporation. All rights reserved.



## Additional Info*

**The information below is copied from [MicrosoftDocs](https://github.com/MicrosoftDocs/windowsserverdocs), which is maintained by [Microsoft](https://opensource.microsoft.com/codeofconduct/). Available under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.*

---
## relog

> Applies to: Windows Server (Semi-Annual Channel), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Extracts performance counters from performance counter logs into other formats, such as text-TSV (for tab-delimited text), text-CSV (for comma-delimited text), binary-BIN, or SQL.

### Syntax
```
relog [<FileName> [<FileName> ...]] [/a] [/c <path> [<path> ...]] [/cf <FileName>] [/f  {bin|csv|tsv|SQL}] [/t <Value>] [/o {OutputFile|DSN!CounterLog}] [/b <M/D/YYYY> [[<HH>:] <MM>:] <SS>] [/e <M/D/YYYY> [[<HH>:] <MM>:] <SS>] [/config {<FileName>|i}] [/q]
```

##### Parameters

|                                         Parameter                                          |                                                                                                                                                                  Description                                                                                                                                                                   |
|--------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                *FileName* [*FileName ...*]                                 |                                                                                                                      Specifies the pathname of an existing performance counter log. You can specify multiple input files.                                                                                                                      |
|                                             -a                                             |                                                                                                          Appends output file instead of overwriting. This option does not apply to SQL format where the default is always to append.                                                                                                           |
|                                   -c *path* [*path ...*]                                   |                                                       Specifies the performance counter path to log. To specify multiple counter paths, separate them with a space and enclose the counter paths in quotation marks (for example, **"**<em>Counterpath1</em> <em>Counterpath2</em>**"**)                                                       |
|                                       -cf *FileName*                                       |                                            Specifies the pathname of the text file that lists the performance counters to be included in a relog file. Use this option to list counter paths in an input file, one per line. Default setting is all counters in the original log file are relogged.                                            |
|                                  -f {bin\| csv\|tsv\|SQL}                                  |                                       Specifies the pathname of the output file format. The default format is **bin**. For a SQL database, the output file specifies the *DSN!CounterLog*. You can specify the database location by using the ODBC manager to configure the DSN (Database System Name).                                        |
|                                         -t *Value*                                         |                                                                                                           Specifies sample intervals in "*N*" records. Includes every nth data point in the relog file. Default is every data point.                                                                                                           |
| -o {*OutputFile* \| *"SQL:DSN!Counter_Log*} where DSN is a ODBC DSN defined on the system. |                                                   Specifies the pathname of the output file or SQL database where the counters will be written. <br>Note: For the 64-bit and 32-bit versions of Relog.exe, you need to define a DSN in the ODBC Data Source (64-bit and 32-bit respectively). Use the "SQL Server" ODBC driver to define a DSN                                                   |
|                          -b \<*M*/*D*/*YYYY*> [[*HH*:]*MM*:]*SS*                           |                                                                          Specifies begin time for copying first record from the input file. date and time must be in this exact format <em>M</em>**/**<em>D</em>**/**<em>YYYYHH</em>**:**<em>MM</em>**:**<em>SS</em>.                                                                          |
|                          -e \<*M*/*D*/*YYYY*> [[*HH*:]*MM*:]*SS*                           |                                                                           Specifies end time for copying last record from the input file. date and time must be in this exact format <em>M</em>**/**<em>D</em>**/**<em>YYYYHH</em>**:**<em>MM</em>**:**<em>SS</em>.                                                                            |
|                                -config {*FileName* \| *i*}                                 | Specifies the pathname of the settings file that contains command-line parameters. Use *-i* in the configuration file as a placeholder for a list of input files that can be placed on the command line. On the command line, however, you do not need to use *i*. You can also use wildcards such as \*.blg to specify many input file names. |
|                                             -q                                             |                                                                                                                          Displays the performance counters and time ranges of log files specified in the input file.                                                                                                                           |
|                                             -y                                             |                                                                                                                                            Bypasses prompting by answering "yes" to all questions.                                                                                                                                             |
|                                             /?                                             |                                                                                                                                                      Displays help at the command prompt.                                                                                                                                                      |

### Remarks
Counter path format:
- The general format for counter paths is as follows: [\\\<computer>] \\\<Object>[\<Parent>\\<Instance#Index>] \\\<Counter>] where the parent, instance, index, and counter components of the format may contain either a valid name or a wildcard character. The computer, parent, instance, and index components are not necessary for all counters.
- You determine the counter paths to use based on the counter itself. For example, the LogicalDisk object has an instance <Index>, so you must provide the <#index> or a wildcard. Therefore, you could use the following format: **\LogicalDisk(\*/\*#\*)\\\\***
- In comparison, the Process object does not require an instance \<Index>. Therefore, you could use the following format: **\Process(\*)\ID Process**
- If a wildcard character is specified in the parent name, all instances of the specified object that match the specified instance and counter fields will be returned.
- If a wildcard character is specified in the instance name, all instances of the specified object and parent object will be returned if all instance names corresponding to the specified index match the wildcard character.
- If a wildcard character is specified in the counter name, all counters of the specified object are returned.
- Partial counter path string matches (for example, pro*) are not supported.

Counter files:
-   Counter files are text files that list one or more of the performance counters in the existing log. Copy the full counter name from the log or the **/q** output in \<computer>\\\<Object>\\\<Instance>\\\<Counter> format. list one counter path on each line.

Copying counters:
-   When executed, **relog** copies specified counters from every record in the input file, converting the format if necessary. Wildcard paths are allowed in the counter file.
Saving input file subsets:
-   Use the **/t** parameter to specify that input files are inserted into output files at intervals of every <n>th record. By default, data is relogged from every record.
Using **/b** and **/e** parameters with log files
-   You can specify that your output logs include records from before begin-time (that is, **/b**) to provide data for counters that require computation values of the formatted value. The output file will have the last records from input files with timestamps less than the **/e** (that is, end time) parameter.
Using the **/config** option:
-   The contents of the setting file used with the **/config** option should have the following format:
    -   \<CommandOption>\\\<Value>, where \<CommandOption> is a command line option and \<Value> specifies its value.

For more information about incorporating **relog** into your Windows Management Instrumentation (WMI) scripts, see "Scripting WMI" at the [Microsoft Windows Resource Kits Web site](https://go.microsoft.com/fwlink/?LinkId=4665).

### Examples
To resample existing trace logs at fixed intervals of 30, list counter paths, output files and formats:
```
relog c:\perflogs\daily_trace_log.blg /cf counter_file.txt /o c:\perflogs\reduced_log.csv /t 30 /f csv
```
To resample existing trace logs at fixed intervals of 30, list counter paths and output file:
```
relog c:\perflogs\daily_trace_log.blg /cf counter_file.txt /o c:\perflogs\reduced_log.blg /t 30
```
To resample existing trace logs into a database use:
```
relog "c:\perflogs\daily_trace_log.blg" -f sql -o "SQL:sql2016x64odbc!counter_log"
```

### Additional References
- [Command-Line Syntax Key](https://github.com/MicrosoftDocs/windowsserverdocs/tree/master/WindowsServerDocs/administration/windows-commands/command-line-syntax-key.md)

---



MIT License. Copyright (c) 2020 Strontic.

