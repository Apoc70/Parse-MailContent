# Parse-MailContent.ps1

Fetch email content from monitoring emails generated by ENow Management Suite for further processing

## Description

This script fetches emails from a given monitoring mailbox by searching messages for a given subject string.
In this case email messages sent by the ENow Manage Suite (http://enowsoftware.com/)
The mailbox is queried using Exchange Web Services (EWS). The EWS endpoint is identified by AutoDiscover.

The is a good example for parsing emails using EWS.

The script exports the following columns for further processing:

SERVER = Name of Exchange server reporting issue
DATE = Date of issue occurance (Short Date)
TIME = Time of issue occurance (Long Time)
IO = READ or WRITE
THRESHOLD = WARNING or CRITICAL
VALUE = reported value 

## Requirements

* Windows Server 2012 R2+
* Exchange Server 2013+
* Exchange Web Services Library

Do not forget to adjust the EWS library path

## Parameters

### TargetMailbox

Email address of the monitoring mailbox, Example: monitoring@mcscmemail.de

### MailboxFolderPath

Mailbox folder path to search. The string is language specific (EN starts with '\Inbox', DE starts with '\Posteingang'), Example '\Inbox\My Monitoring'

### SubjectSearchString

Message subject of monitoring messages to find. Query uses LIKE.

### CsvFilename

File name of exported CSV

## Examples

``` PowerShell
.\Get-EmailContent.ps1
```

Run script using default parameters

## Note

THIS CODE IS MADE AVAILABLE AS IS, WITHOUT WARRANTY OF ANY KIND. THE ENTIRE  
RISK OF THE USE OR THE RESULTS FROM THE USE OF THIS CODE REMAINS WITH THE USER.

## Credits

Written by: Thomas Stensitzki

## Stay connected

- My Blog: [http://justcantgetenough.granikos.eu](http://justcantgetenough.granikos.eu)
- Twitter: [https://twitter.com/stensitzki](https://twitter.com/stensitzki)
- LinkedIn: [http://de.linkedin.com/in/thomasstensitzki](http://de.linkedin.com/in/thomasstensitzki)
- Github: [https://github.com/Apoc70](https://github.com/Apoc70)
- MVP Blog: [https://blogs.msmvps.com/thomastechtalk/](https://blogs.msmvps.com/thomastechtalk/)
- Tech Talk YouTube Channel (DE): [http://techtalk.granikos.eu](http://techtalk.granikos.eu)

For more Office 365, Cloud Security, and Exchange Server stuff checkout services provided by Granikos

- Blog: [http://blog.granikos.eu](http://blog.granikos.eu)
- Website: [https://www.granikos.eu/en/](https://www.granikos.eu/en/)
- Twitter: [https://twitter.com/granikos_de](https://twitter.com/granikos_de)