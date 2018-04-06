---
UID: NF:ntifs.FsRtlIncrementCcFastReadResourceMiss
title: FsRtlIncrementCcFastReadResourceMiss function
author: windows-driver-content
description: The FsRtlIncrementCcFastReadResourceMiss routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters.
old-location: ifsk\fsrtlincrementccfastreadresourcemiss.htm
old-project: ifsk
ms.assetid: 38264afe-e324-455d-b81a-7dafae8abc1c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlIncrementCcFastReadResourceMiss, FsRtlIncrementCcFastReadResourceMiss routine [Installable File System Drivers], fsrtlref_4eb3905b-e599-451e-ba6c-29b800b277a5.xml, ifsk.fsrtlincrementccfastreadresourcemiss, ntifs/FsRtlIncrementCcFastReadResourceMiss
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlIncrementCcFastReadResourceMiss
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIncrementCcFastReadResourceMiss function


## -description


The <b>FsRtlIncrementCcFastReadResourceMiss</b> routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters.


## -parameters








## -returns



This routine does not return a value.




## -remarks



<b>FsRtlIncrementCcFastReadResourceMiss </b>increments the CcFastReadReadResourceMiss performance counter in the per processor control block of cache manager system counters. This counter indicates that a fast I/O read operation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff545791">FsRtlCopyRead</a>) was called, but fast I/O was not possible because the file resource could not be acquired for shared access. 

File system drivers should call this function to update the performance counter if the driver chooses to override the default fast I/O read handler.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545791">FsRtlCopyRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546085">FsRtlIncrementCcFastReadNoWait</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546078">FsRtlIncrementCcFastReadNotPossible</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546096">FsRtlIncrementCcFastReadWait</a>
 

 

