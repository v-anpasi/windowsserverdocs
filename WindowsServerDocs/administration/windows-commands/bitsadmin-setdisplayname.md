---
title: bitsadmin setdisplayname
description: "Windows Commands topic for **bitsadmin setdisplayname** - Sets the display name of the specified job."
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 13706c53-fb5f-4879-b5ca-82531361d6e1
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/12/2016
---
# bitsadmin setdisplayname

>Applies To: Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Sets the display name of the specified job.
## Syntax
```
bitsadmin /SetDisplayName <Job> <DisplayName>
```
## Parameters
|Parameter|Description|
|-------|--------|
|Job|The job's display name or GUID|
|DisplayName|Text used for the display name of the specified job.|
## <a name="BKMK_examples"></a>Examples
The following example sets the display name for the job named *myDownloadJob* to *myDownloadJob2*.
```
C:\>bitsadmin /SetDisplayName myDownloadJob "Download Music Job"
```
## additional references
[Command-Line Syntax Key](command-line-syntax-key.md)
