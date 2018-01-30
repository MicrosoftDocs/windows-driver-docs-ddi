---
UID: NF:ntifs.PsUpdateDiskCounters
title: PsUpdateDiskCounters function
author: windows-driver-content
description: The PsUpdateDiskCounters routine updates the disk I/O counters of a given process.
old-location: ifsk\psupdatediskcounters.htm
old-project: ifsk
ms.assetid: 0BDC6629-9C0E-4437-888D-1EF730714CA4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/PsUpdateDiskCounters, ifsk.psupdatediskcounters, PsUpdateDiskCounters routine [Installable File System Drivers], PsUpdateDiskCounters
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsUpdateDiskCounters
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsUpdateDiskCounters function


## -description


The <b>PsUpdateDiskCounters</b> routine updates the disk I/O counters of a given process.


## -syntax


````
VOID PsUpdateDiskCounters(
   PEPROCESS Process,
   ULONG64   BytesRead,
   ULONG64   BytesWritten,
   ULONG     ReadOperationCount,
   ULONG     WriteOperationCount,
   ULONG     FlushOperationCount
);
````


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

<a href="..\ntifs\nf-ntifs-psisdiskcountersenabled.md">PsIsDiskCountersEnabled</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsUpdateDiskCounters routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

