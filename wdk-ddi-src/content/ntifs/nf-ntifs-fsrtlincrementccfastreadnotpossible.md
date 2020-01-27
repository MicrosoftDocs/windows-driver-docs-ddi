---
UID: NF:ntifs.FsRtlIncrementCcFastReadNotPossible
title: FsRtlIncrementCcFastReadNotPossible function (ntifs.h)
description: The FsRtlIncrementCcFastReadNotPossible routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters.
old-location: ifsk\fsrtlincrementccfastreadnotpossible.htm
tech.root: ifsk
ms.assetid: 2e0ae5d1-5189-4f78-9729-9c1b9bbf046d
ms.date: 04/16/2018
ms.keywords: FsRtlIncrementCcFastReadNotPossible, FsRtlIncrementCcFastReadNotPossible routine [Installable File System Drivers], fsrtlref_7789e1c4-9ac3-48c7-9191-f5eba5f4e5e0.xml, ifsk.fsrtlincrementccfastreadnotpossible, ntifs/FsRtlIncrementCcFastReadNotPossible
f1_keywords:
 - "ntifs/FsRtlIncrementCcFastReadNotPossible"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlIncrementCcFastReadNotPossible
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIncrementCcFastReadNotPossible function


## -description


The <b>FsRtlIncrementCcFastReadNotPossible</b> routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters.


## -remarks



<b>FsRtlIncrementCcFastReadNotPossible </b>increments the CcFastReadNotPossible performance counter in the per processor control block of cache manager system counters. This counter indicates that a fast I/O read operation (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>) was called, but fast I/O was not possible. This counter does not get incremented if fast I/O was not possible because the file resource could not be acquired for shared access. When the resource could not be acquired, the CcFastReadResourceMiss performance counter should be incremented. 

File system drivers should call this function to update the performance counter if the driver chooses to override the default fast I/O read handler.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546085">FsRtlIncrementCcFastReadNoWait</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546091">FsRtlIncrementCcFastReadResourceMiss</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546096">FsRtlIncrementCcFastReadWait</a>
 

 

