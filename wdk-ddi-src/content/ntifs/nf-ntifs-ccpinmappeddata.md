---
UID: NF:ntifs.CcPinMappedData
title: CcPinMappedData function (ntifs.h)
description: The CcPinMappedData routine pins the specified byte range of a cached file.
old-location: ifsk\ccpinmappeddata.htm
tech.root: ifsk
ms.assetid: aa0903db-fced-4af9-bfc9-2769ed4962a1
ms.date: 04/18/2018
ms.keywords: CcPinMappedData, CcPinMappedData routine [Installable File System Drivers], ccref_3935eee3-9906-4110-812f-ca186953cfbf.xml, ifsk.ccpinmappeddata, ntifs/CcPinMappedData
ms.topic: function
f1_keywords:
- "ntifs/CcPinMappedData"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CcPinMappedData
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcPinMappedData function


## -description


The <b>CcPinMappedData</b> routine pins the specified byte range of a cached file.


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file in which a range of data is to be pinned.


### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file where the desired data resides.


### -param Length [in]

Length in bytes of the data to be pinned.


### -param Flags [in]

Bitmask of flags specifying how the pinning operation is to be performed. ORed combination of one or more of the following values: 

<table>
<tr>
<th>Flag</th>
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
 


### -param Bcb [in, out]

On the first call this returns a pointer to a buffer control block (BCB). This pointer must be supplied as input on all subsequent calls for this buffer. 


## -returns



<b>CcPinMappedData</b> returns <b>TRUE</b> if the data for the cached file was pinned successfully, <b>FALSE</b> otherwise.




## -remarks



A successful return from <b>CcPinMappedData</b> guarantees that the data previously mapped in a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539155">CcMapData</a> is pinned in the cache and data in the specified range can be safely modified. If the caller subsequently modifies the data pinned by <b>CcPinMappedData</b>, it must also call <a href="https://msdn.microsoft.com/library/windows/hardware/ff539211">CcSetDirtyPinnedData</a> so that the modified data will eventually be written to disk.

<b>CcPinMappedData</b> cannot pin data across view boundaries in the cache manager. The cache manager manages files in the system in 256 KB-aligned views. (The cache manager's view size is specified by the system-defined constant <b>VACB_MAPPING_GRANULARITY</b>, which is set to 256 KB in <i>ntifs.h</i>.) Pinned regions cannot span more than one 256 KB view. Therefore, the largest region that can be pinned is 256 KB, beginning at a 256 KB-aligned offset in the file. 

Pinning a byte range in a cached file does not ensure that the pages remain resident in memory. As long as the pages are pinned, the byte range is guaranteed to stay mapped into the system cache virtual address space, but the memory manager can page out the physical pages as the system's memory demand requires. 

If any failure occurs, <b>CcPinMappedData</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcPinMappedData</b> raises a <b>STATUS_INSUFFICIENT_RESOURCES</b> exception; if an I/O error occurs, <b>CcPinMappedData</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcPinMappedData</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To map data for a cached file, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539155">CcMapData</a> routine. To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.

It is not necessary to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a> after calling <b>CcPinMappedData</b> since the pin reference is matched to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539155">CcMapData</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539155">CcMapData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539180">CcPinRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539183">CcPreparePinWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539211">CcSetDirtyPinnedData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a>
 

 

