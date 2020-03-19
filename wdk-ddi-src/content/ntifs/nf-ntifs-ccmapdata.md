---
UID: NF:ntifs.CcMapData
title: CcMapData function (ntifs.h)
description: The CcMapData routine maps a specified byte range of a cached file to a buffer in memory.
old-location: ifsk\ccmapdata.htm
tech.root: ifsk
ms.assetid: dccc79ba-68d9-41cf-b86d-37adb83558a0
ms.date: 04/16/2018
keywords: ["CcMapData function"]
ms.keywords: CcMapData, CcMapData routine [Installable File System Drivers], ccref_1eb788ce-2fb2-40b4-b696-14609a0c8556.xml, ifsk.ccmapdata, ntifs/CcMapData
f1_keywords:
 - "ntifs/CcMapData"
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CcMapData
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcMapData function


## -description


The <b>CcMapData</b> routine maps a specified byte range of a cached file to a buffer in memory.


## -parameters




### -param FileObject [in]

Pointer to a file object for the file whose data is to be mapped for read access.


### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file where the desired data resides.


### -param Length [in]

Length of desired data in bytes.


### -param Flags [in]

Bitmask of flags specifying how the mapping operation is to be performed. This is a bitwise OR combination of one or more of the following values: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
MAP_WAIT

</td>
<td>
The caller can be put into a wait state until the data has been mapped. 

</td>
</tr>
<tr>
<td>
MAP_NO_READ

</td>
<td>
Only pages that are already resident in memory are to be mapped. 

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>    In Windows 2000and earlier, this parameter was a BOOLEAN value named <i>Wait</i>: </div>
<div> </div>




#### Wait

Set to <b>TRUE</b> if the caller can be put into a wait state until the data has been mapped, <b>FALSE</b> otherwise.


### -param Bcb [out]

On the first call this returns a pointer to a buffer control block (BCB) structure. This pointer must be supplied as input on all subsequent calls, for this buffer.


### -param Buffer [out]

Pointer to a buffer containing the mapped data.


## -returns



<b>CcMapData</b> returns <b>TRUE</b> if the data for the cached file was mapped successfully, <b>FALSE</b> otherwise.




## -remarks



<b>CcMapData</b> maps data in a cached file for read access. Note that after <b>CcMapData</b> is called, the data is mapped; but it is not pinned. This distinction is important. Data that is mapped but not pinned cannot safely be modified. To pin the data, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539176">CcPinMappedData</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff539180">CcPinRead</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff539183">CcPreparePinWrite</a>.

Every successful call to <b>CcMapData</b> must be matched by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a>. 

<b>CcMapData</b> cannot map data across view boundaries in the cache manager. The cache manager manages files in the system in 256 KB-aligned views. (The cache manager's view size is specified by the system-defined constant <b>VACB_MAPPING_GRANULARITY</b>, which is set to 256 KB in <i>ntifs.h</i>.) Mapped regions cannot span more than one 256 KB view. Therefore, the largest region that can be mapped is 256 KB, beginning at a 256 KB-aligned offset in the file. 

Mapping a byte range in a cached file does not ensure that the pages remain resident in memory. As long as the pages are mapped, the byte range is guaranteed to stay mapped into the system cache virtual address space, but the memory manager can page out the physical pages as the system's memory demand requires. 

If the <b>MAP_WAIT</b> flag is set (or <i>Wait</i> is <b>TRUE</b>), <b>CcMapData</b> is guaranteed to complete the mapping request and return <b>TRUE</b>. If the required pages of the cached file are already resident in memory, the data is mapped immediately and no blocking will occur. If any needed pages are not resident, the caller is put in a wait state until all required pages have been made resident and the data can be mapped. If the <b>MAP_WAIT</b> flag is not set (or <i>Wait</i> is <b>FALSE</b>) and the data cannot be mapped immediately, <b>CcMapData</b> returns <b>FALSE</b>.

The pointer returned in <i>Buffer</i> is valid until <a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a> is called. If <a href="https://msdn.microsoft.com/library/windows/hardware/ff539176">CcPinMappedData</a> is called while this pointer is still valid, the pointer remains valid after the call to <b>CcPinMappedData</b> (but only until <b>CcUnpinData</b> is called).

If any failure occurs, <b>CcMapData</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcMapData</b> raises a <b>STATUS_INSUFFICIENT_RESOURCES</b> exception; if an I/O error occurs, <b>CcMapData</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcMapData</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539176">CcPinMappedData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539180">CcPinRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539183">CcPreparePinWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a>
 

 

