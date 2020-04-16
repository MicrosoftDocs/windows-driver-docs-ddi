---
UID: NF:fltkernel.FltEnumerateFilters
title: FltEnumerateFilters function (fltkernel.h)
description: The FltEnumerateFilters routine enumerates all registered minifilter drivers in the system.
old-location: ifsk\fltenumeratefilters.htm
tech.root: ifsk
ms.assetid: f39ff534-7b51-49b5-bb1f-7cb0e18b3cfc
ms.date: 04/16/2018
keywords: ["FltEnumerateFilters function"]
ms.keywords: FltApiRef_e_to_o_04dcdecd-0910-42be-ae92-93bce56216d7.xml, FltEnumerateFilters, FltEnumerateFilters routine [Installable File System Drivers], fltkernel/FltEnumerateFilters, ifsk.fltenumeratefilters
f1_keywords:
 - "fltkernel/FltEnumerateFilters"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltEnumerateFilters
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltEnumerateFilters function


## -description


The <b>FltEnumerateFilters</b> routine enumerates all registered minifilter drivers in the system. 


## -parameters




### -param FilterList [out]

Pointer to a caller-allocated buffer that receives an array of opaque filter pointers. This parameter is optional and can be <b>NULL</b> if the value of <i>FilterListSize</i> parameter is zero. If <i>FilterListSize</i> is zero on input and <i>FilterList</i> is <b>NULL</b>, the <i>NumberFiltersReturned</i> parameter receives the number of minifilter drivers found. 


### -param FilterListSize [in]

Number of opaque filter pointers that the buffer that the <i>FilterList</i> parameter points to can hold. This parameter is optional and can be zero. If <i>FilterListSize</i> is zero on input and <i>FilterList</i> is <b>NULL</b>, the <i>NumberFiltersReturned</i> parameter receives the number of minifilter drivers found. 


### -param NumberFiltersReturned [out]

Pointer to a caller-allocated variable that receives the number of opaque filter pointers returned in the array that the <i>FilterList </i>parameter points to. If the <i>FilterListSize</i> parameter value is too small and <i>FilterList</i> is non-<b>NULL</b> on input, <b>FltEnumerateFilters</b> returns STATUS_BUFFER_TOO_SMALL and sets <i>NumberFiltersReturned</i> to point to the number of minifilter drivers found. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltEnumerateFilters</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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
The buffer that the <i>FilterList</i> parameter points to is not large enough to store the requested information. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Because filters can register at any time, two calls to <b>FltEnumerateFilters</b> are not guaranteed to return the same result. 

<b>FltEnumerateFilters</b> adds a rundown reference to each of the opaque filter pointers returned in the array that the <i>FilterList </i>parameter points to. When these pointers are no longer needed, the caller must release them by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a> on each one. Thus every successful call to <b>FltEnumerateFilters</b> must be matched by a subsequent call to <b>FltObjectDereference</b> for each returned filter pointer. 

To list filter information for all registered minifilter drivers, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratefilterinformation">FltEnumerateFilterInformation</a>. 

To enumerate instances of all minifilter drivers on all volumes, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstances">FltEnumerateInstances</a>. 

To enumerate all volumes that are known to the Filter Manager, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratevolumes">FltEnumerateVolumes</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratefilterinformation">FltEnumerateFilterInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstances">FltEnumerateInstances</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratevolumes">FltEnumerateVolumes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilterinformation">FltGetFilterInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a>
 

 

