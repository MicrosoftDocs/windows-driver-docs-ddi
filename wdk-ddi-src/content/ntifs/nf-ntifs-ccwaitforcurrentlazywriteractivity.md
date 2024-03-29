---
UID: NF:ntifs.CcWaitForCurrentLazyWriterActivity
title: CcWaitForCurrentLazyWriterActivity function (ntifs.h)
description: The CcWaitForCurrentLazyWriterActivity routine puts the caller into a wait state until the current batch of lazy writer activity is completed.
old-location: ifsk\ccwaitforcurrentlazywriteractivity.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcWaitForCurrentLazyWriterActivity function"]
ms.keywords: CcWaitForCurrentLazyWriterActivity, CcWaitForCurrentLazyWriterActivity routine [Installable File System Drivers], ccref_a216c467-24be-4ea5-9c53-71cf1fe1c47d.xml, ifsk.ccwaitforcurrentlazywriteractivity, ntifs/CcWaitForCurrentLazyWriterActivity
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - CcWaitForCurrentLazyWriterActivity
 - ntifs/CcWaitForCurrentLazyWriterActivity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcWaitForCurrentLazyWriterActivity
---

# CcWaitForCurrentLazyWriterActivity function


## -description

The <b>CcWaitForCurrentLazyWriterActivity</b> routine puts the caller into a wait state until the current batch of lazy writer activity is completed.

## -returns

<b>CcWaitForCurrentLazyWriterActivity</b> can return one of the following NTSTATUS values:

## -remarks

<b>CcWaitForCurrentLazyWriterActivity</b> puts the calling thread into a wait state until all work items currently in the lazy writer (read ahead or write behind) work queue have completed.

To prevent deadlock, the caller should release any currently held synchronization objects before calling <b>CcWaitForCurrentLazyWriterActivity</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a>



<a href="/previous-versions/ff539191(v=vs.85)">CcReadAhead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetadditionalcacheattributes">CcSetAdditionalCacheAttributes</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetreadaheadgranularity">CcSetReadAheadGranularity</a>
