---
UID: NF:ntifs.FsRtlIncrementCcFastReadNoWait
title: FsRtlIncrementCcFastReadNoWait function (ntifs.h)
description: The FsRtlIncrementCcFastReadNoWait routine increments the CcFastReadNoWait performance counter in a per processor control block of cache manager system counters.
old-location: ifsk\fsrtlincrementccfastreadnowait.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlIncrementCcFastReadNoWait function"]
ms.keywords: FsRtlIncrementCcFastReadNoWait, FsRtlIncrementCcFastReadNoWait routine [Installable File System Drivers], fsrtlref_f72704ce-84b6-4201-a727-b97fd70accfd.xml, ifsk.fsrtlincrementccfastreadnowait, ntifs/FsRtlIncrementCcFastReadNoWait
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
 - FsRtlIncrementCcFastReadNoWait
 - ntifs/FsRtlIncrementCcFastReadNoWait
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIncrementCcFastReadNoWait
---

# FsRtlIncrementCcFastReadNoWait function


## -description

The <b>FsRtlIncrementCcFastReadNoWait</b> routine increments the CcFastReadNoWait performance counter in a per processor control block of cache manager system counters.

## -remarks

<b>FsRtlIncrementCcFastReadNoWait</b> increments the CcFastReadNoWait performance counter in the per processor control block of cache manager system counters. This counter indicates that a fast I/O read operation, <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>, was called with the <i>Wait</i> parameter set to <b>FALSE</b> indicating that the caller cannot be put into a wait state until all the data has been copied.

File system drivers should call this function to update the performance counter if the driver chooses to override the default fast I/O read handler.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlincrementccfastreadnotpossible">FsRtlIncrementCcFastReadNotPossible</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlincrementccfastreadresourcemiss">FsRtlIncrementCcFastReadResourceMiss</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlincrementccfastreadwait">FsRtlIncrementCcFastReadWait</a>
