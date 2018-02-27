---
UID: NF:ntifs.CcPinRead
title: CcPinRead function
author: windows-driver-content
description: The CcPinRead routine pins the specified byte range of a cached file and reads the pinned data into a buffer in memory.
old-location: ifsk\ccpinread.htm
old-project: ifsk
ms.assetid: 46b0e05e-f7e2-4a9b-bec0-26bcaf31b013
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CcPinRead, CcPinRead routine [Installable File System Drivers], ccref_f6bbe780-631d-48f8-979f-6ed4260cbe5d.xml, ifsk.ccpinread, ntifs/CcPinRead
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcPinRead
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcPinRead function


## -description


The <b>CcPinRead</b> routine pins the specified byte range of a cached file and reads the pinned data into a buffer in memory.


## -syntax


````
BOOLEAN CcPinRead(
  _In_  PFILE_OBJECT   FileObject,
  _In_  PLARGE_INTEGER FileOffset,
  _In_  ULONG          Length,
  _In_  ULONG          Flags,
  _Out_ PVOID          *Bcb,
  _Out_ PVOID          *Buffer
);
````


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file in which a range of data is to be pinned.


### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file where the desired data resides.


### -param Length [in]

Length of desired data in bytes.


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
The buffer control block (BCB) is to be acquired exclusively. If this flag is set, PIN_WAIT must also be set.

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
The data is to be pinned only if a BCB already exists. Otherwise, the pin fails and <i>Bcb</i> is set to <b>NULL</b>.

</td>
</tr>
</table>
 


### -param Bcb [out]

On the first call this returns a pointer to a buffer control block (BCB). This pointer must be supplied as input on all subsequent calls for this buffer.


### -param Buffer [out]

Pointer to a buffer containing the pinned data.


## -returns



<b>CcPinRead</b> returns <b>TRUE</b> if the data for the cached file was pinned and read successfully, <b>FALSE</b> otherwise.




## -remarks



If the PIN_WAIT flag is set, <b>CcPinRead</b> is guaranteed to complete the pinning request and return <b>TRUE</b>. If the required pages of the cached file are already resident in memory, the data is pinned immediately and no blocking occurs. If any needed pages are not resident, the caller is put in a wait state until all required pages have been made resident and the data can be pinned. If the PIN_WAIT flag is not set, but the data cannot be pinned immediately, <b>CcPinRead</b> returns <b>FALSE</b>, and its output parameter values are meaningless.

If the caller subsequently modifies the data read by <b>CcPinRead</b>, it must also call <a href="..\ntifs\nf-ntifs-ccsetdirtypinneddata.md">CcSetDirtyPinnedData</a> so that the modified data will eventually be written to disk.

Every successful call to <b>CcPinRead</b> must be matched by a subsequent call to <a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>.

The pointer returned in <i>Buffer</i> is valid until <a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a> is called. If <a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a> is called while this pointer is still valid, the pointer remains valid after the call to <b>CcPinMappedData</b> (but only until <b>CcUnpinData</b> is called).

<b>CcPinRead</b> cannot pin data across view boundaries in the cache manager. The cache manager manages files in the system in 256 KB-aligned views. (The cache manager's view size is specified by the system-defined constant VACB_MAPPING_GRANULARITY, which is set to 256 KB in ntifs.h.) Pinned regions cannot span more than one 256 KB view. Therefore, the largest region that can be pinned is 256 KB, beginning at a 256 KB-aligned offset in the file. 

Pinning a byte range in a cached file does not ensure that the pages remain resident in memory. As long as the pages are pinned, the byte range is guaranteed to stay mapped into the system cache virtual address space, but the memory manager can page out the physical pages as the system's memory demand requires. 

If any failure occurs, <b>CcPinRead</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcPinRead</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcPinRead</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcPinRead</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To map data for a cached file, use the <a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a> routine. To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>



<a href="..\ntifs\nf-ntifs-ccsetdirtypinneddata.md">CcSetDirtyPinnedData</a>



<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>



<a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>



<a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>



<a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcPinRead routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

