---
title: manage-bde changekey
description: "Windows Commands topic for **** - "
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 69463db9-7e03-47ff-b233-a95d5055725f
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/12/2016
---
# manage-bde: changekey

>Applies To: Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Modifies the startup key for an operating system drive. For examples of how this command can be used, see [Examples](#BKMK_Examples).
## Syntax
```
manage-bde -changekey [<Drive>] [<pathToExternalKeydirectory>] [-computername <Name>] [{-?|/?}] [{-help|-h}]
```
### Parameters
|Parameter|Description|
|-------|--------|
|<Drive>|Represents a drive letter followed by a colon.|
|<pathToExternalKeydirectory>|Represents the directory location to save the external startup key file that can be used to unlock the drive.|
|-computername|Specifies that manage-bde.exe will be used to modify BitLocker protection on a different computer. You can also use **-cn** as an abbreviated version of this command.|
|<Name>|Represents the name of the computer on which to modify BitLocker protection. Accepted values include the computer's NetBIOS name and the computer's IP address.|
|-? or /?|Displays brief help at the command prompt.|
|-help or -h|Displays complete help at the command prompt.|
## <a name="BKMK_Examples"></a>Examples
The following example illustrates using the **-changekey** command to create a new startup key on drive E to use with BitLocker encryption on drive C.
```
manage-bde  changekey C: E:\
```
## additional references
-   [Command-Line Syntax Key](command-line-syntax-key.md)
-   [manage-bde](manage-bde.md)
