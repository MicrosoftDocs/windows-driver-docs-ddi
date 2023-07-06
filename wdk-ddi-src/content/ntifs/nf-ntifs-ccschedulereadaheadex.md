---
UID: NF:ntifs.CcScheduleReadAheadEx
title: CcScheduleReadAheadEx function (ntifs.h)
description: Learn more about the CcScheduleReadAheadEx routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["CcScheduleReadAheadEx function"]
ms.keywords: CcScheduleReadAheadEx, ifsk.ccschedulereadaheadex, ntifs/CcScheduleReadAheadEx
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcScheduleReadAheadEx
 - ntifs/CcScheduleReadAheadEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcScheduleReadAheadEx
---

# CcScheduleReadAheadEx function

## -description

The **CcScheduleReadAheadEx** routine performs read-ahead (also called "lazy read") on a cached file. The I/O byte count for the operation is charged to the issuing thread.

## -parameters

### -param FileObject [in]

Pointer to a file object for the file on which read-ahead is to be performed.

### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file where the last read occurred.

### -param Length [in]

Length in bytes of the range that was last read.

### -param IoIssuerThread [in]

The thread issuing the read ahead request. For a file system with disk I/O accounting enabled, this is the thread the I/O is charged to. If **IoIssuerThread** is NULL, the I/O is charged to the current thread.

## -remarks

**CcScheduleReadAheadEx** should be called only when **Length** >= 256. Measurements have shown that calling **CcScheduleReadAheadEx** for smaller reads actually decreases performance.

**CcScheduleReadAheadEx** can only be called after a successful call to [**CcCopyRead**](nf-ntifs-cccopyread.md), [**CcCopyReadEx**](nf-ntifs-cccopyreadex.md), [**CcFastCopyRead**](nf-ntifs-ccfastcopyread.md), or [**CcMdlRead**](/previous-versions/ff539159(v=vs.85)).

## -see-also

[**CcCopyRead**](nf-ntifs-cccopyread.md)

[**CcCopyReadEx**](nf-ntifs-cccopyreadex.md)

[**CcFastCopyRead**](nf-ntifs-ccfastcopyread.md)

[**CcMdlRead**](/previous-versions/ff539159(v=vs.85)).

[**CcReadAhead**](/previous-versions/ff539191(v=vs.85))

[**CcSetAdditionalCacheAttributes**](nf-ntifs-ccsetadditionalcacheattributes.md)

[**CcSetReadAheadGranularity**](nf-ntifs-ccsetreadaheadgranularity.md)
