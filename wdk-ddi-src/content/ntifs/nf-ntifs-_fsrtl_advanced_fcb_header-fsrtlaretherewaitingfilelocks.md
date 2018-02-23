---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAreThereWaitingFileLocks
title: FsRtlAreThereWaitingFileLocks function
author: windows-driver-content
description: The FsRtlAreThereWaitingFileLocks routine checks a file lock queue for any waiting file locks.
old-location: ifsk\fsrtlaretherewaitingfilelocks.htm
old-project: ifsk
ms.assetid: 92093588-DD44-4503-8803-7E47F178A728
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntifs/FsRtlAreThereWaitingFileLocks, FsRtlAreThereWaitingFileLocks routine [Installable File System Drivers], ifsk.fsrtlaretherewaitingfilelocks, FsRtlAreThereWaitingFileLocks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlAreThereWaitingFileLocks
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAreThereWaitingFileLocks function


## -description


The <b>FsRtlAreThereWaitingFileLocks</b> routine checks a file lock queue for any waiting file locks.


## -syntax


````
BOOLEAN FsRtlAreThereWaitingFileLocks(
  _In_ PFILE_LOCK FileLock
);
````


## -parameters




### -param FileLock [in]

The file lock that specifies locked ranges.


## -returns




      Returns <b>TRUE</b> if waiting file  locks are present;  <b>FALSE</b> otherwise.



