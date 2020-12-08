---
UID: NF:ntifs.FsRtlIncrementCcFastReadWait
title: FsRtlIncrementCcFastReadWait function (ntifs.h)
description: The FsRtlIncrementCcFastReadWait routine increments the CcFastReadWait performance counter in a per processor control block of cache manager system counters.
old-location: ifsk\fsrtlincrementccfastreadwait.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlIncrementCcFastReadWait function"]
ms.keywords: FsRtlIncrementCcFastReadWait, FsRtlIncrementCcFastReadWait routine [Installable File System Drivers], fsrtlref_487f6c6e-ec6f-4b81-a303-829e6d82d260.xml, ifsk.fsrtlincrementccfastreadwait, ntifs/FsRtlIncrementCcFastReadWait
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlIncrementCcFastReadWait
 - ntifs/FsRtlIncrementCcFastReadWait
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIncrementCcFastReadWait
---

# FsRtlIncrementCcFastReadWait function


## -description

The <b>FsRtlIncrementCcFastReadWait</b> routine increments the CcFastReadWait performance counter in a per processor control block of cache manager system counters.

## -remarks

<b>FsRtlIncrementCcFastReadWait</b> increments the CcFastReadWait performance counter in the per processor control block of cache manager system counters. This counter indicates that a fast I/O read operation, <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>, was called with the <i>Wait</i> parameter set to <b>TRUE</b> indicating that the caller can be put into a wait state until all the data has been copied.

File system drivers should call this function to update the performance counter if the driver chooses to override the default fast I/O read handler.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlincrementccfastreadnowait">FsRtlIncrementCcFastReadNoWait</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlincrementccfastreadnotpossible">FsRtlIncrementCcFastReadNotPossible</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlincrementccfastreadresourcemiss">FsRtlIncrementCcFastReadResourceMiss</a>
