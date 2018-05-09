---
UID: NF:ntifs.PsUpdateDiskCounters
title: PsUpdateDiskCounters function
author: windows-driver-content
description: The PsUpdateDiskCounters routine updates the disk I/O counters of a given process.
old-location: ifsk\psupdatediskcounters.htm
old-project: ifsk
ms.assetid: 0BDC6629-9C0E-4437-888D-1EF730714CA4
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PsUpdateDiskCounters, PsUpdateDiskCounters routine [Installable File System Drivers], ifsk.psupdatediskcounters, ntifs/PsUpdateDiskCounters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsUpdateDiskCounters
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsUpdateDiskCounters function


## -description


The <b>PsUpdateDiskCounters</b> routine updates the disk I/O counters of a given process.


## -parameters




### -param Process

A pointer to the process to update counters for.


### -param BytesRead

The number of bytes to update in the Read counter.


### -param BytesWritten

The number of bytes to update in the Write counter.


### -param ReadOperationCount

The number of read operations to update in the Read Operation counter.


### -param WriteOperationCount

The number of write operations to update in the Write Operation counter.


### -param FlushOperationCount

The number of flush operations to update in the Flush Operation counter.


## -returns



This routine does not return a value.




## -remarks



File system drivers use <b>PsUpdateDiskCounters</b> to update counts for disk I/O accounting. A client process can be "charged" the disk I/O counts by the file system.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh971608">PsIsDiskCountersEnabled</a>
 

 

