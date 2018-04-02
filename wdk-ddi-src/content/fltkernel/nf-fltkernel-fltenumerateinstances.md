---
UID: NF:fltkernel.FltEnumerateInstances
title: FltEnumerateInstances function
author: windows-driver-content
description: The FltEnumerateInstances routine enumerates minifilter driver instances for a given minifilter driver or volume.
old-location: ifsk\fltenumerateinstances.htm
old-project: ifsk
ms.assetid: d09b95d9-4b45-4da5-9c61-8e30ed4fa1d5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_3875fd52-c8b1-4d79-9f90-83297dbbb44c.xml, FltEnumerateInstances, FltEnumerateInstances routine [Installable File System Drivers], fltkernel/FltEnumerateInstances, ifsk.fltenumerateinstances
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
-	FltEnumerateInstances
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltEnumerateInstances function


## -description


The <b>FltEnumerateInstances</b> routine enumerates minifilter driver instances for a given minifilter driver or volume. 


## -parameters




### -param Volume [in, optional]

Opaque pointer for the volume for which the caller wants to enumerate minifilter driver instances. If <b>NULL</b>, instances for all volumes are enumerated. Must be non-<b>NULL</b> if <i>Filter</i> is <b>NULL</b>. 


### -param Filter [in, optional]

Opaque filter pointer for the minifilter driver whose instances are to be enumerated. If <b>NULL</b>, instances for all minifilter drivers are enumerated. Must be non-<b>NULL</b> if <i>Volume</i> is <b>NULL</b>. 


### -param InstanceList [out]

Pointer to a caller-allocated buffer that receives an array of opaque instance pointers. 


### -param InstanceListSize [in]

Number of opaque instance pointers that the buffer that <i>InstanceList</i> points to can hold. 


### -param NumberInstancesReturned [out]

Pointer to a caller-allocated variable that receives the number of opaque instance pointers returned in the array that <i>InstanceList </i>points to. If <i>InstanceListSize</i> is too small, <b>FltEnumerateInstances</b> returns STATUS_BUFFER_TOO_SMALL and sets <i>NumberInstancesReturned</i> to point to the number of matching instances found. 


## -returns



<b>FltEnumerateInstances</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
The buffer that the <i>InstanceList</i> parameter points to is not large enough to store the requested information. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>Volume</i> and <i>Filter</i> cannot both be <b>NULL</b>. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Because the minifilter driver instances in the instance list can change at any time, two calls to <b>FltEnumerateInstances</b> with the same <i>Volume</i> and <i>Filter</i> values are not guaranteed to return the same result. 

<b>FltEnumerateInstances</b> adds a rundown reference to each of the opaque instance pointers returned in the array that the <i>InstanceList </i>parameter points to. When these pointers are no longer needed, the caller must release them by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a> on each one. Thus every successful call to <b>FltEnumerateInstances</b> must be matched by a subsequent call to <b>FltObjectDereference</b> for each returned instance pointer. 

To enumerate all registered minifilter drivers, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a>. 

To enumerate all volumes that are known to the Filter Manager, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542092">FltEnumerateVolumes</a>. 

To list filter information for all registered minifilter drivers, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a>. 

To get filter information for a given minifilter driver, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543053">FltGetFilterInformation</a>. 

To enumerate all instances of a given minifilter driver, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542071">FltEnumerateInstanceInformationByFilter</a>. 

To enumerate all minifilter driver instances on a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542071">FltEnumerateInstanceInformationByFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542092">FltEnumerateVolumes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543053">FltGetFilterInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>
 

 

