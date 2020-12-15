---
UID: NF:ntifs.CcInitializeCacheMap
title: CcInitializeCacheMap function (ntifs.h)
description: File systems call the CcInitializeCacheMap routine to cache a file.
old-location: ifsk\ccinitializecachemap.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcInitializeCacheMap function"]
ms.keywords: CcInitializeCacheMap, CcInitializeCacheMap routine [Installable File System Drivers], ccref_8a69cf72-ebb8-499d-8b15-8b0e0b912c95.xml, ifsk.ccinitializecachemap, ntifs/CcInitializeCacheMap
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
 - CcInitializeCacheMap
 - ntifs/CcInitializeCacheMap
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcInitializeCacheMap
---

# CcInitializeCacheMap function


## -description

File systems call the <b>CcInitializeCacheMap</b> routine to cache a file.

## -parameters

### -param FileObject 

[in]
Pointer to a file object for the file.

### -param FileSizes 

[in]
Pointer to a CC_FILE_SIZES structure containing <b>AllocationSize</b>, <b>FileSize</b>, and <b>ValidDataLength</b> for the file. This structure is defined as follows:


```
typedef struct _CC_FILE_SIZES {
    LARGE_INTEGER AllocationSize;
    LARGE_INTEGER FileSize;
    LARGE_INTEGER ValidDataLength;
} CC_FILE_SIZES, *PCC_FILE_SIZES;
```

<table>
<tr>
<th>Member</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>AllocationSize</b>

</td>
<td>
New section object size for the file. Ignored if less than or equal to the current section size.

</td>
</tr>
<tr>
<td>
<b>FileSize</b>

</td>
<td>
New file size for the file.

</td>
</tr>
<tr>
<td>
<b>ValidDataLength</b>

</td>
<td>
New valid data length for the file.

</td>
</tr>
</table>

### -param PinAccess 

[in]
Set to <b>TRUE</b> if <b>CcPin</b><i>Xxx</i> routines will be used on the file.

### -param Callbacks 

[in]
Pointer to a structure allocated from nonpaged pool, containing entry points of caller-supplied read-ahead and write-behind callback routines.This structure and its members are defined as follows:


```
typedef struct _CACHE_MANAGER_CALLBACKS {
    PACQUIRE_FOR_LAZY_WRITE AcquireForLazyWrite;
    PRELEASE_FROM_LAZY_WRITE ReleaseFromLazyWrite;
    PACQUIRE_FOR_READ_AHEAD AcquireForReadAhead;
    PRELEASE_FROM_READ_AHEAD ReleaseFromReadAhead;
} CACHE_MANAGER_CALLBACKS, *PCACHE_MANAGER_CALLBACKS;
typedef
BOOLEAN (*PACQUIRE_FOR_LAZY_WRITE) (
             IN PVOID Context,
             IN BOOLEAN Wait
             );
typedef
VOID (*PRELEASE_FROM_LAZY_WRITE) (
             IN PVOID Context
             );
typedef
BOOLEAN (*PACQUIRE_FOR_READ_AHEAD) (
             IN PVOID Context,
             IN BOOLEAN Wait
             );
typedef
VOID (*PRELEASE_FROM_READ_AHEAD) (
             IN PVOID Context
             );
```


### -param LazyWriteContext 

[in]
Pointer to context information to be passed to the callback routines specified in <i>Callbacks</i>.

## -remarks

<b>CcInitializeCacheMap</b> creates the data structures required for file data caching.

If any failure occurs, <b>CcInitializeCacheMap</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcInitializeCacheMap</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcInitializeCacheMap</b> in a <b>try-except</b> or <b>try-finally</b> statement.

File systems must call <b>CcInitializeCacheMap</b> to cache a file before using any other cache manager routines on the file, unless the file was created with data caching disabled. In most file systems, file caching is enabled by default, but can be disabled by setting the FILE_NO_INTERMEDIATE_BUFFERING flag to <b>TRUE</b> in the file create options.

After calling <b>CcInitializeCacheMap</b>, the file system can call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetadditionalcacheattributes">CcSetAdditionalCacheAttributes</a> to disable read-ahead or write-behind, if desired.

When closing a file, every file system that supports file caching must call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccuninitializecachemap">CcUninitializeCacheMap</a> on that file, whether the file is cached or not. Even if the file was created with caching disabled, the file system still must call <b>CcUninitializeCacheMap</b>.

The <b>CcIsFileCached</b> macro determines whether a file is cached or not.


```cpp
BOOLEAN CcIsFileCached(
  [in] PFILE_OBJECT FileObject
);

```

Parameters

<i>FileObject[in]</i> [in]

Pointer to a file object for the file.

Return value

Returns <b>TRUE</b> if the file is cached, <b>FALSE</b> otherwise.

<div class="alert"><b>Note</b>  Because multiple file objects can refer to the same file (that is, data stream), it is possible for the <b>CcIsFileCached</b> macro to return <b>TRUE</b> given a non-cached file object if another cached file object refers to the same data stream.  In other words, if there is a set of file objects that refer to the same data stream and if at least one of the file objects in the set is cached, <b>CcIsFileCached</b> will return <b>TRUE</b> for all file objects in the set.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetadditionalcacheattributes">CcSetAdditionalCacheAttributes</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccuninitializecachemap">CcUninitializeCacheMap</a>
