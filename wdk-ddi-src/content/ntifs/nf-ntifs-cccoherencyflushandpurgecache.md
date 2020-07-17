---
UID: NF:ntifs.CcCoherencyFlushAndPurgeCache
title: CcCoherencyFlushAndPurgeCache function (ntifs.h)
description: The CcCoherencyFlushAndPurgeCache routine flushes and/or purges the cache to ensure cache coherency.
old-location: ifsk\cccoherencyflushandpurgecache.htm
tech.root: ifsk
ms.assetid: 61dfdd09-1e2b-4771-a2c2-62454adc7832
ms.date: 04/16/2018
keywords: ["CcCoherencyFlushAndPurgeCache function"]
ms.keywords: CcCoherencyFlushAndPurgeCache, CcCoherencyFlushAndPurgeCache routine [Installable File System Drivers], ccref_79641311-568b-472c-9950-2e46472affcf.xml, ifsk.cccoherencyflushandpurgecache, ntifs/CcCoherencyFlushAndPurgeCache
f1_keywords:
 - "ntifs/CcCoherencyFlushAndPurgeCache"
 - "CcCoherencyFlushAndPurgeCache"
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CcCoherencyFlushAndPurgeCache
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcCoherencyFlushAndPurgeCache function


## -description


The <b>CcCoherencyFlushAndPurgeCache</b> routine flushes and/or purges the cache to ensure cache coherency. Use <b>CcCoherencyFlushAndPurgeCache</b> when possible instead of an explicit flush and purge call sequence as it will invalidate user mapped views to prevent data corruption.


## -parameters




### -param SectionObjectPointer [in]

A pointer to a structure that contains the section object pointers of the file object.


### -param FileOffset [in, optional]

A pointer to a variable that specifies the starting byte offset to flush, purge, or both.


### -param Length [in]

The length, in bytes of the data to flush and/or purge starting at <i>FileOffset</i>. This parameter is ignored if a <b>NULL</b> pointer is passed to <i>FileOffset</i>.


### -param IoStatus [out]

A pointer to a caller-allocated structure that receives the final completion status and information about the operation.


### -param Flags [in, optional]

A bitmask of flags that specify how the operation is to be performed. The one flag is defined in the following table. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CC_FLUSH_AND_PURGE_NO_PURGE

</td>
<td>
Flush, but do not purge the cache. This is useful for read coherency flushes.

</td>
</tr>
</table>
 


## -remarks



The file must be acquired exclusively before you call <b>CcCoherencyFlushAndPurgeCache</b>.

You can flush and/or purge any byte range within a file by using the <i>FileOffset</i> and <i>Length</i> parameters. Or you can flush, purge, or both an entire file if you pass a <b>NULL</b> pointer to the <i>FileOffset</i> parameter.

A call to <b>CcCoherencyFlushAndPurgeCache</b> is a synchronous (blocking) operation, not an asynchronous (non-blocking) operation.

An <i>IoStatus</i>-><i>Status </i>value of STATUS_CACHE_PAGE_LOCKED indicates that page invalidation failed. Be aware that page invalidation can fail even if you pass CC_FLUSH_AND_PURGE_NO_PURGE in the <i>Flags</i> parameter.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539082">CcFlushCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>
 

 

