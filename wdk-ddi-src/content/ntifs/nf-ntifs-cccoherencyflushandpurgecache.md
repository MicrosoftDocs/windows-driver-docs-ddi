---
UID: NF:ntifs.CcCoherencyFlushAndPurgeCache
title: CcCoherencyFlushAndPurgeCache function (ntifs.h)
description: The CcCoherencyFlushAndPurgeCache routine flushes and/or purges the cache to ensure cache coherency.
old-location: ifsk\cccoherencyflushandpurgecache.htm
tech.root: ifsk
ms.date: 08/30/2021
keywords: ["CcCoherencyFlushAndPurgeCache function"]
ms.keywords: CcCoherencyFlushAndPurgeCache, CcCoherencyFlushAndPurgeCache routine [Installable File System Drivers], ccref_79641311-568b-472c-9950-2e46472affcf.xml, ifsk.cccoherencyflushandpurgecache, ntifs/CcCoherencyFlushAndPurgeCache
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
targetos: Windows
req.typenames: 
f1_keywords:
 - CcCoherencyFlushAndPurgeCache
 - ntifs/CcCoherencyFlushAndPurgeCache
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcCoherencyFlushAndPurgeCache
---

# CcCoherencyFlushAndPurgeCache function

## -description

The **CcCoherencyFlushAndPurgeCache** routine flushes, or flushes and purges, the cache to ensure cache coherency.

## -parameters

### -param SectionObjectPointer [in]

A pointer to a [**SECTION_OBJECT_POINTERS**](../wdm/ns-wdm-_section_object_pointers.md) structure that contains the section object pointers of the file object.

### -param FileOffset [in, optional]

A pointer to a variable that specifies the starting byte offset to flush, or to flush and purge.

### -param Length [in]

The length in bytes of the data to flush, or to flush and purge, starting at **FileOffset**. This parameter is ignored if a **NULL** pointer is passed to **FileOffset**.

### -param IoStatus [out]

A pointer to a caller-allocated [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that receives the final completion status and information about the operation.

### -param Flags [in, optional]

A bitmask of the following flags that specify how the operation is to be performed:

| Value | Meaning |
| ----- | ------- |
| CC_FLUSH_AND_PURGE_NO_PURGE                | Flush, but do not purge the cache. This is useful for read coherency flushes. |
| CC_FLUSH_AND_PURGE_GATHER_DIRTY_BITS       | Reserved for system use; do not use. |
| CC_FLUSH_AND_PURGE_WRITEABLE_VIEWS_NOTSEEN | The caller can set this flag when there are no mappings to the file outside of the cache manager, in order to skip the expensive operation of trimming [process working sets](/windows/win32/memory/working-set). |

## -remarks

 Use **CcCoherencyFlushAndPurgeCache** when possible instead of an explicit flush and purge call sequence as it will invalidate user mapped views to prevent data corruption. **CcCoherencyFlushAndPurgeCache** ensures cache coherency; as such, there is no option to do a purge only via this function.

The file must be acquired exclusively before you call **CcCoherencyFlushAndPurgeCache**.

You can flush, or flush and purge, any byte range within a file by using the **FileOffset** and **Length** parameters. Or you can flush, or flush and purge, an entire file if you pass a **NULL** pointer to the **FileOffset** parameter.

A call to **CcCoherencyFlushAndPurgeCache** is a synchronous (blocking) operation, not an asynchronous (non-blocking) operation.

An **IoStatus->Status** value of STATUS_CACHE_PAGE_LOCKED indicates that page invalidation failed. Be aware that page invalidation can fail even if you pass CC_FLUSH_AND_PURGE_NO_PURGE in the **Flags** parameter.

## -see-also

[**CcFlushCache**](nf-ntifs-ccflushcache.md)

[**CcPurgeCacheSection**](nf-ntifs-ccpurgecachesection.md)
