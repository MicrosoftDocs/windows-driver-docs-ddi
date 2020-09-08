---
UID: NF:ntifs.CcFlushCache
title: CcFlushCache function (ntifs.h)
description: The CcFlushCache routine flushes all or a portion of a cached file to disk.
old-location: ifsk\ccflushcache.htm
tech.root: ifsk
ms.assetid: 06bb49bc-56e6-42fc-ae52-c954507d2a3f
ms.date: 04/16/2018
keywords: ["CcFlushCache function"]
ms.keywords: CcFlushCache, CcFlushCache routine [Installable File System Drivers], ccref_089656c6-a12e-4e74-a72d-7f0182f3c3dd.xml, ifsk.ccflushcache, ntifs/CcFlushCache
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - CcFlushCache
 - ntifs/CcFlushCache
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcFlushCache
---

# CcFlushCache function


## -description

The <b>CcFlushCache</b> routine flushes all or a portion of a cached file to disk.

## -parameters

### -param SectionObjectPointer 

[in]
Pointer to a <b>SECTION_OBJECT_POINTERS</b> structure containing the file object's section object pointers.

### -param FileOffset 

[in, optional]
Pointer to a variable that specifies the starting byte offset within the cached file where the data is to be flushed. 

If <i>FileOffset</i> is <b>NULL</b>, the entire file is flushed from the cache.

If <i>FileOffset</i> is not <b>NULL</b>, only the byte range specified by <i>FileOffset</i> and <i>Length</i> is flushed.

### -param Length 

[in]
Length of the byte range to flush, starting at <i>FileOffset</i>. If <i>FileOffset</i> is <b>NULL</b>, <i>Length</i> is ignored.

### -param IoStatus 

[out, optional]
Pointer to a structure that receives the final completion status and information about the flush operation. If the data is flushed successfully, <i>IoStatus.Status</i> contains STATUS_SUCCESS. If not all of the data is flushed successfully, <i>IoStatus.Information</i> contains the actual number of bytes that were flushed. Otherwise, <i>IoStatus.Information</i> contains the value  given in <i>Length</i>.

## -remarks

<b>CcFlushCache</b> has no <i>Wait</i> parameter. Thus the caller must be able to enter a wait state until all the data has been flushed.

To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539045">CcCopyWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://docs.microsoft.com/previous-versions/ff539143(v=vs.85)">CcIsFileCached</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>

