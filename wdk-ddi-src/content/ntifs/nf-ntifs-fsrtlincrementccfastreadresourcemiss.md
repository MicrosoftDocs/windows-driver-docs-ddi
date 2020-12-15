---
UID: NF:ntifs.FsRtlIncrementCcFastReadResourceMiss
title: FsRtlIncrementCcFastReadResourceMiss function (ntifs.h)
description: The FsRtlIncrementCcFastReadResourceMiss routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters.
old-location: ifsk\fsrtlincrementccfastreadresourcemiss.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlIncrementCcFastReadResourceMiss function"]
ms.keywords: FsRtlIncrementCcFastReadResourceMiss, FsRtlIncrementCcFastReadResourceMiss routine [Installable File System Drivers], fsrtlref_4eb3905b-e599-451e-ba6c-29b800b277a5.xml, ifsk.fsrtlincrementccfastreadresourcemiss, ntifs/FsRtlIncrementCcFastReadResourceMiss
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
 - FsRtlIncrementCcFastReadResourceMiss
 - ntifs/FsRtlIncrementCcFastReadResourceMiss
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIncrementCcFastReadResourceMiss
---

# FsRtlIncrementCcFastReadResourceMiss function


## -description

The <b>FsRtlIncrementCcFastReadResourceMiss</b> routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters.

## -remarks

<b>FsRtlIncrementCcFastReadResourceMiss </b>increments the CcFastReadReadResourceMiss performance counter in the per processor control block of cache manager system counters. This counter indicates that a fast I/O read operation (<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>) was called, but fast I/O was not possible because the file resource could not be acquired for shared access. 

File system drivers should call this function to update the performance counter if the driver chooses to override the default fast I/O read handler.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlincrementccfastreadnowait">FsRtlIncrementCcFastReadNoWait</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlincrementccfastreadnotpossible">FsRtlIncrementCcFastReadNotPossible</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlincrementccfastreadwait">FsRtlIncrementCcFastReadWait</a>
