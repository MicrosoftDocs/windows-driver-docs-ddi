---
UID: NF:ntifs.CcInitializeCacheMap
title: CcInitializeCacheMap function
author: windows-driver-content
description: File systems call the CcInitializeCacheMap routine to cache a file.
old-location: ifsk\ccinitializecachemap.htm
old-project: ifsk
ms.assetid: a76027d9-b486-4596-bbe4-0a801ed73256
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcInitializeCacheMap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcInitializeCacheMap
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# CcInitializeCacheMap function



## -description
File systems call the <b>CcInitializeCacheMap</b> routine to cache a file.



## -syntax

````
VOID CcInitializeCacheMap(
  _In_ PFILE_OBJECT             FileObject,
  _In_ PCC_FILE_SIZES           FileSizes,
  _In_ BOOLEAN                  PinAccess,
  _In_ PCACHE_MANAGER_CALLBACKS Callbacks,
  _In_ PVOID                    LazyWriteContext
);
````


## -parameters

### -param FileObject [in]

Pointer to a file object for the file.


### -param FileSizes [in]

Pointer to a CC_FILE_SIZES structure containing <b>AllocationSize</b>, <b>FileSize</b>, and <b>ValidDataLength</b> for the file. This structure is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _CC_FILE_SIZES {
    LARGE_INTEGER AllocationSize;
    LARGE_INTEGER FileSize;
    LARGE_INTEGER ValidDataLength;
} CC_FILE_SIZES, *PCC_FILE_SIZES;</pre>
</td>
</tr>
</table></span></div>
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
 


### -param PinAccess [in]

Set to <b>TRUE</b> if <b>CcPin</b><i>Xxx</i> routines will be used on the file.


### -param Callbacks [in]

Pointer to a structure allocated from nonpaged pool, containing entry points of caller-supplied read-ahead and write-behind callback routines.This structure and its members are defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _CACHE_MANAGER_CALLBACKS {
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
             );</pre>
</td>
</tr>
</table></span></div>

### -param LazyWriteContext [in]

Pointer to context information to be passed to the callback routines specified in <i>Callbacks</i>.


## -returns
None


## -remarks
<b>CcInitializeCacheMap</b> creates the data structures required for file data caching.

If any failure occurs, <b>CcInitializeCacheMap</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcInitializeCacheMap</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcInitializeCacheMap</b> in a <b>try-except</b> or <b>try-finally</b> statement.

File systems must call <b>CcInitializeCacheMap</b> to cache a file before using any other cache manager routines on the file, unless the file was created with data caching disabled. In most file systems, file caching is enabled by default, but can be disabled by setting the FILE_NO_INTERMEDIATE_BUFFERING flag to <b>TRUE</b> in the file create options.

After calling <b>CcInitializeCacheMap</b>, the file system can call <a href="..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md">CcSetAdditionalCacheAttributes</a> to disable read-ahead or write-behind, if desired.

When closing a file, every file system that supports file caching must call <a href="..\ntifs\nf-ntifs-ccuninitializecachemap.md">CcUninitializeCacheMap</a> on that file, whether the file is cached or not. Even if the file was created with caching disabled, the file system still must call <b>CcUninitializeCacheMap</b>.

The <b>CcIsFileCached</b> macro determines whether a file is cached or not.

Parameters


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md">CcSetAdditionalCacheAttributes</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccuninitializecachemap.md">CcUninitializeCacheMap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcInitializeCacheMap routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

