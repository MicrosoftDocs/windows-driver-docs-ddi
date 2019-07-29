---
UID: NF:ntifs.FsRtlAreThereWaitingFileLocks
title: FsRtlAreThereWaitingFileLocks function (ntifs.h)
description: The FsRtlAreThereWaitingFileLocks routine checks a file lock queue for any waiting file locks.
old-location: ifsk\fsrtlaretherewaitingfilelocks.htm
tech.root: ifsk
ms.assetid: 92093588-DD44-4503-8803-7E47F178A728
ms.date: 04/16/2018
ms.keywords: FsRtlAreThereWaitingFileLocks, FsRtlAreThereWaitingFileLocks routine [Installable File System Drivers], ifsk.fsrtlaretherewaitingfilelocks, ntifs/FsRtlAreThereWaitingFileLocks
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlAreThereWaitingFileLocks"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlAreThereWaitingFileLocks
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlAreThereWaitingFileLocks function


## -description


The <b>FsRtlAreThereWaitingFileLocks</b> routine checks a file lock queue for any waiting file locks.


## -parameters




### -param FileLock [in]

The file lock that specifies locked ranges.


## -returns




      Returns <b>TRUE</b> if waiting file  locks are present;  <b>FALSE</b> otherwise.



