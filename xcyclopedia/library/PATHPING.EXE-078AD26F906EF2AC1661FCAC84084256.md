﻿---
title: PATHPING.EXE | TCP/IP PathPing Command
---

# PATHPING.EXE 

* File Path: `C:\Windows\SysWOW64\PATHPING.EXE`
* Description: TCP/IP PathPing Command
* Comments: 

## Hashes

Type | Hash
-- | --
MD5 | `078AD26F906EF2AC1661FCAC84084256`
SHA1 | `6C43FC753A74290889C62D432035465D54D6A58E`
SHA256 | `BB6753327AECDCC1E9C44E75BE44AE94FEDDDABEF038411D510D861A1527E79E`
SHA384 | `145857C46DBFFD53BEB7D568FBF474CC643281A8B49D4FF85CE2A706017EE9302C16237BFEF4F5246482FBF17C7E9BE1`
SHA512 | `790522172D90821529D0BDF2ACB5D2C5DE3F39A5299D8469C923709DBAF9A5056186919555C9B208BA5147E46B8E5CEA8B378146BBA803C46B116F442383B849`
SSDEEP | `384:P564Qut7wFP4RXWKZCraV/mlL8fzKWVAW:Pk/P4RvV+lL8V`

## Runtime Data

### Usage (stdout):
```Batchfile

Usage: pathping [-g host-list] [-h maximum_hops] [-i address] [-n] 
                [-p period] [-q num_queries] [-w timeout] 
                [-4] [-6] target_name

Options:
    -g host-list     Loose source route along host-list.
    -h maximum_hops  Maximum number of hops to search for target.
    -i address       Use the specified source address. 
    -n               Do not resolve addresses to hostnames.
    -p period        Wait period milliseconds between pings.
    -q num_queries   Number of queries per hop.
    -w timeout       Wait timeout milliseconds for each reply.
    -4               Force using IPv4.
    -6               Force using IPv6.

```

### Usage (stderr):
```Batchfile

```

### Child Processes:
conhost.exe

## Signature

* Status: Signature verified.
* Serial: `330000023241FB59996DCC4DFF000000000232`
* Thumbprint: `FF82BC38E1DA5E596DF374C53E3617F7EDA36B06`
* Issuer: CN=Microsoft Windows Production PCA 2011, O=Microsoft Corporation, L=Redmond, S=Washington, C=US
* Subject: CN=Microsoft Windows, O=Microsoft Corporation, L=Redmond, S=Washington, C=US

## File Metadata

* Original Filename: pathping.exe
* Product Name: Microsoft Windows Operating System
* Company Name: Microsoft Corporation
* File Version: 10.0.19041.1 (WinBuild.160101.0800)
* Product Version: 10.0.19041.1
* Language: English (United States)
* Legal Copyright:  Microsoft Corporation. All rights reserved.



## Additional Info*

**The information below is copied from [MicrosoftDocs](https://github.com/MicrosoftDocs/windowsserverdocs), which is maintained by [Microsoft](https://opensource.microsoft.com/codeofconduct/). Available under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.*

---

## pathping

> Applies to: Windows Server (Semi-Annual Channel), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Provides information about network latency and network loss at intermediate hops between a source and destination. **pathping** sends multiple echo Request messages to each router between a source and destination over a period of time and then computes results based on the packets returned from each router. Because **pathping** displays the degree of packet loss at any given router or link, you can determine which routers or subnets might be having network problems.

**pathping** performs the equivalent of the **tracert** command by identifying which routers are on the path. It then sends pings periodically to all of the routers over a specified time period and computes statistics based on the number returned from each. Used without parameters, **pathping** displays help.

### Syntax
```
pathping [/n] [/h] [/g <Hostlist>] [/p <Period>] [/q <NumQueries> [/w <timeout>] [/i <IPaddress>] [/4 <IPv4>] [/6 <IPv6>][<TargetName>]
```
##### Parameters
|Parameter|Description|
|-------|--------|
|/n|Prevents **pathping** from attempting to resolve the IP addresses of intermediate routers to their names. This might expedite the display of **pathping** results.|
|/h \<MaximumHops>|Specifies the maximum number of hops in the path to search for the target (destination). The default is 30 hops.|
|/g \<Hostlist>|Specifies that the echo Request messages use the Loose Source Route option in the IP header with the set of intermediate destinations specified in *Hostlist*. With loose source routing, successive intermediate destinations can be separated by one or multiple routers. The maximum number of addresses or names in the host list is 9. The *Hostlist* is a series of IP addresses (in dotted decimal notation) separated by spaces.|
|/p \<Period>|Specifies the number of milliseconds to wait between consecutive pings. The default is 250 milliseconds (1/4 second).|
|/q \<NumQueries>|Specifies the number of echo Request messages sent to each router in the path. The default is 100 queries.|
|/w \<timeout>|Specifies the number of milliseconds to wait for each reply. The default is 3000 milliseconds (3 seconds).|
|/i \<IPaddress>|Specifies the source address.|
|/4 \<IPv4>|Specifies that pathping uses IPv4 only.|
|/6 \<IPv6>|Specifies that pathping uses IPv6 only.|
|\<TargetName>|Specifies the destination, which is identified either by IP address or host name.|
|/?|Displays help at the command prompt.|

### Remarks
-   **pathping** parameters are case-sensitive.
-   To avoid network congestion, pings should be sent at a sufficiently slow pace.
-   To minimize the effects of burst losses, do not send pings too frequently.
-   When using the **/p** parameter, pings are sent individually to each intermediate hop. Because of this, the interval between two pings sent to the same hop is *period* multiplied by the number of hops.
-   When using the **/w** parameter, multiple pings can be sent in parallel. Because of this, the amount of time specified in the *timeout* parameter is not bounded by the amount of time specified in the *Period* parameter for waiting between pings.
-   This command is available only if the Internet Protocol (TCP/IP) protocol is installed as a component in the properties of a network adapter in Network Connections.

### Examples

To shows **pathping** command output:

```
D:\>pathping /n corp1
Tracing route to corp1 [10.54.1.196]
over a maximum of 30 hops:
  0  172.16.87.35
  1  172.16.87.218
  2  192.168.52.1
  3  192.168.80.1
  4  10.54.247.14
  5  10.54.1.196
computing statistics for 125 seconds...
            Source to Here   This Node/Link
Hop  RTT    Lost/Sent = Pct  Lost/Sent = Pct  address
  0                                           172.16.87.35
                                0/ 100 =  0%   |
  1   41ms     0/ 100 =  0%     0/ 100 =  0%  172.16.87.218
                               13/ 100 = 13%   |
  2   22ms    16/ 100 = 16%     3/ 100 =  3%  192.168.52.1
                                0/ 100 =  0%   |
  3   24ms    13/ 100 = 13%     0/ 100 =  0%  192.168.80.1
                                0/ 100 =  0%   |
  4   21ms    14/ 100 = 14%     1/ 100 =  1%  10.54.247.14
                                0/ 100 =  0%   |
  5   24ms    13/ 100 = 13%     0/ 100 =  0%  10.54.1.196
Trace complete.
```
When **pathping** is run, the first results list the path. This is the same path that is shown using the **tracert** command. Next, a busy message is displayed for approximately 90 seconds (the time varies by hop count). During this time, information is gathered from all routers previously listed and from the links between them. at the end of this period, the test results are displayed.

In the sample report above, the **This Node/Link**, **Lost/Sent = Pct** and **address** columns show that the link between 172.16.87.218 and 192.168.52.1 is dropping 13 percent of the packets. The routers at hops 2 and 4 also are dropping packets addressed to them, but this loss does not affect their ability to forward traffic that is not addressed to them.

The loss rates displayed for the links, identified as a vertical bar (**|**) in the **address** column, indicate link congestion that is causing the loss of packets that are being forwarded on the path. The loss rates displayed for routers (identified by their IP addresses) indicate that these routers might be overloaded.

### Additional References
- [Command-Line Syntax Key](https://github.com/MicrosoftDocs/windowsserverdocs/tree/master/WindowsServerDocs/administration/windows-commands/command-line-syntax-key.md)

---



MIT License. Copyright (c) 2020 Strontic.

