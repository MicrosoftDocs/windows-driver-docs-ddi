---
UID: NF:fltkernel.FltEnumerateVolumes
title: FltEnumerateVolumes function (fltkernel.h)
description: The FltEnumerateVolumes routine enumerates all volumes in the system.
old-location: ifsk\fltenumeratevolumes.htm
tech.root: ifsk
ms.assetid: 67038ff5-c450-460b-b158-f5d817fdc972
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_20e817de-0825-4c5f-a831-2815c216344e.xml, FltEnumerateVolumes, FltEnumerateVolumes routine [Installable File System Drivers], fltkernel/FltEnumerateVolumes, ifsk.fltenumeratevolumes
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltEnumerateVolumes
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltEnumerateVolumes function


## -description


The <b>FltEnumerateVolumes</b> routine enumerates all volumes in the system. 


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>.


### -param VolumeList [out]

Pointer to a caller-allocated buffer that receives an array of opaque volume pointers. This parameter is optional and can be <b>NULL</b> if <i>VolumeListSize</i> is zero. If <i>VolumeListSize</i> is zero on input and <i>VolumeList</i> is <b>NULL</b>, <i>NumberVolumesReturned</i> receives the number of volumes found.


### -param VolumeListSize [in]

Number of opaque filter pointers that the buffer that <i>VolumeList</i> points to can hold. This parameter is optional and can be zero. If <i>VolumeListSize</i> is zero on input and <i>VolumeList</i> is <b>NULL</b>, <i>NumberVolumesReturned</i> receives the number of volumes found.


### -param NumberVolumesReturned [out]

Pointer to a caller-allocated variable that receives the number of opaque volume pointers returned in the array that <i>VolumeList </i>points to. If <i>VolumeListSize</i> is too small and <i>VolumeList</i> is non-<b>NULL</b> on input, <b>FltEnumerateVolumes</b> returns STATUS_BUFFER_TOO_SMALL and sets <i>NumberVolumesReturned</i> to point to the number of volumes found. This parameter is required and cannot be <b>NULL</b>.


## -returns



<b>FltEnumerateVolumes</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>VolumeList</i> parameter points to is not large enough to store the requested information. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Because the contents of the filter manager's volume list can change at any time, two calls to <b>FltEnumerateVolumes</b> are not guaranteed to return the same result. 

<b>FltEnumerateVolumes</b> adds a rundown reference to each of the opaque volume pointers returned in the array that <i>VolumeList </i>points to. When these pointers are no longer needed, the caller must release them by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a> on each one. Thus every successful call to <b>FltEnumerateVolumes</b> must be matched by a subsequent call to <b>FltObjectDereference</b> for each returned volume pointer. 

To convert one or more opaque volume pointers returned by the <i>VolumeList</i> parameter into volume information, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543238">FltGetVolumeInformation</a>.

To list volume information for all volumes that are known to the filter manager, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542091">FltEnumerateVolumeInformation</a>. 

To enumerate all registered minifilter drivers, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a>. 

To enumerate all minifilter driver instances, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542090">FltEnumerateInstances</a>. 

To enumerate all minifilter driver instances on a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542090">FltEnumerateInstances</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542091">FltEnumerateVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543238">FltGetVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>
 

 

