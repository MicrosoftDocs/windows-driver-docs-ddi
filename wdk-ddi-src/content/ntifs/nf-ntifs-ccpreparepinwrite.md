---
UID: NF:ntifs.CcPreparePinWrite
title: CcPreparePinWrite function
author: windows-driver-content
description: The CcPreparePinWrite routine pins the specified byte range of a cached file for write access.
old-location: ifsk\ccpreparepinwrite.htm
old-project: ifsk
ms.assetid: 1645c7e9-5ae7-41d1-92db-1f069f79ac81
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CcPreparePinWrite, CcPreparePinWrite routine [Installable File System Drivers], ccref_00b887b5-cd87-44be-b96e-6be96df13a2b.xml, ifsk.ccpreparepinwrite, ntifs/CcPreparePinWrite
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcPreparePinWrite
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcPreparePinWrite function


## -description


The <b>CcPreparePinWrite</b> routine pins the specified byte range of a cached file for write access.


## -syntax


````
BOOLEAN CcPreparePinWrite(
  _In_  PFILE_OBJECT   FileObject,
  _In_  PLARGE_INTEGER FileOffset,
  _In_  ULONG          Length,
  _In_  BOOLEAN        Zero,
  _In_  ULONG          Flags,
  _Out_ PVOID          *Bcb,
  _Out_ PVOID          *Buffer
);
````


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file to which the data is to be written.


### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the file where the data is to be written.


### -param Length [in]

Length of desired data in bytes.


### -param Zero [in]

Set to <b>TRUE</b> if the buffer is to be zeroed on return. This parameter is ignored if the PIN_CALLER_TRACKS_DIRTY_DATA flag is set in the <i>Flags</i> parameter.


### -param Flags [in]

Bitmask of flags specifying how the pinning operation is to be performed. ORed combination of one or more of the following values: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PIN_WAIT

</td>
<td>
The caller can be put into a wait state until the data has been pinned.

</td>
</tr>
<tr>
<td>
PIN_EXCLUSIVE

</td>
<td>
The buffer control block (BCB) is to be acquired exclusively.

</td>
</tr>
<tr>
<td>
PIN_NO_READ

</td>
<td>
Only pages that are already resident in memory are to be pinned. If this flag is set, PIN_WAIT must also be set.

</td>
</tr>
<tr>
<td>
PIN_IF_BCB

</td>
<td>
The data is to be pinned only if a BCB already exists. Otherwise, the pin fails and no BCB is returned.

</td>
</tr>
<tr>
<td>
PIN_CALLER_TRACKS_DIRTY_DATA

</td>
<td>
The caller is responsible for  keeping track of dirty pages. If this flag is set, all other flags are ignored. This flag is available on Microsoft Windows Server 2003 SP1 and later.

</td>
</tr>
</table>
 


### -param Bcb [out]

Opaque pointer to a pinned buffer control block (BCB). This pointer must be supplied as input on any subsequent calls to <b>CcPreparePinWrite</b> or <a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a> for this buffer.


### -param Buffer [out]

Returns pointer to desired data, valid until the buffer is unpinned or freed.


## -returns



<b>CcPreparePinWrite</b> returns <b>TRUE</b> if the cached file was pinned successfully, <b>FALSE</b> otherwise.




## -remarks



<b>CcPreparePinWrite</b> pins the specified file pages in the system cache. Pages to be completely overwritten may be satisfied with pages of zeros.

If the PIN_WAIT flag is set, <b>CcPreparePinWrite</b> is guaranteed to complete the preparation request and return <b>TRUE</b>. If all of the pages can be prepared immediately, no blocking occurs. If any needed pages are not resident, the caller is put in a wait state until all required pages have been made resident and the pages can be prepared. If the PIN_WAIT flag is not set, but not all of the pages can be prepared immediately, <b>CcPreparePinWrite</b> returns <b>FALSE</b>, and its output parameter values are meaningless.

<b>Microsoft Windows Server 2003 SP1 and later:</b> The PIN_CALLER_TRACKS_DIRTY_DATA flag is commonly used in cases where a file system is managing a log file that is written to but not read from. Because the existing file data will be overwritten and not read, the cache manager may return pages of zeros instead of faulting in the actual pages of file data from disk. If this flag is set, the cache manager does not keep track of dirty pages. The caller is responsible for keeping track of any dirty pages. Note that <b>CcPreparePinWrite</b> should only be used to pin data in this manner if the buffer will eventually be flushed to disk. Before calling <a href="..\ntifs\nf-ntifs-ccflushcache.md">CcFlushCache</a> to flush the buffer to disk, the caller must first call <a href="..\ntifs\nf-ntifs-mmsetaddressrangemodified.md">MmSetAddressRangeModified</a> to notify the memory manager that the specified pages in the system cache buffer are dirty and should be written. 

Every successful call to <b>CcPreparePinWrite</b> must be matched by a subsequent call to <a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>. If <b>CcPreparePinWrite</b> is called multiple times for the same data, <b>CcUnpinData</b> must be called the same number of times. 

The pointer returned in <i>Buffer</i> is valid until <a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a> is called. If <a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a> is called while this pointer is still valid, the pointer remains valid after the call to <b>CcPinMappedData</b> (but only until <b>CcUnpinData</b> is called).

<b>CcPreparePinWrite</b> cannot pin data across view boundaries in the cache manager. The cache manager manages files in the system in 256 KB-aligned views. (The cache manager's view size is specified by the system-defined constant VACB_MAPPING_GRANULARITY, which is set to 256 KB in ntifs.h.) Pinned regions cannot span more than one 256 KB view. Therefore, the largest region that can be pinned is 256 KB, beginning at a 256 KB-aligned offset in the file. 

Pinning a byte range in a cached file does not ensure that the pages remain resident in memory. As long as the pages are pinned, the byte range is guaranteed to stay mapped into the system cache virtual address space, but the memory manager can page out the physical pages as the system's memory demand requires. 

It is not necessary to call <a href="..\ntifs\nf-ntifs-ccsetdirtypinneddata.md">CcSetDirtyPinnedData</a> after calling <b>CcPreparePinWrite</b>. If <b>CcPreparePinWrite</b> returns <b>TRUE</b>, the BCB is already marked as dirty. 

If any failure occurs, <b>CcPreparePinWrite</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcPreparePinWrite</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcPreparePinWrite</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcPreparePinWrite</b> in a <b>try-except</b> or <b>try-finally</b> statement. 




## -see-also

<a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>



<a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>



<a href="..\ntifs\nf-ntifs-ccsetdirtypinneddata.md">CcSetDirtyPinnedData</a>



<a href="..\ntifs\nf-ntifs-ccflushcache.md">CcFlushCache</a>



<a href="..\ntifs\nf-ntifs-mmsetaddressrangemodified.md">MmSetAddressRangeModified</a>



<a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>



<a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcPreparePinWrite routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

