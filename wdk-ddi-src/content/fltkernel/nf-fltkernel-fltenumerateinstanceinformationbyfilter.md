---
UID: NF:fltkernel.FltEnumerateInstanceInformationByFilter
title: FltEnumerateInstanceInformationByFilter function
author: windows-driver-content
description: The FltEnumerateInstanceInformationByFilter routine provides information about instances of a given minifilter driver.
old-location: ifsk\fltenumerateinstanceinformationbyfilter.htm
old-project: ifsk
ms.assetid: c5590897-45cf-4712-b980-b99aaacfba88
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_89f20331-46dd-42f8-bbf5-42650766bdc8.xml, FltEnumerateInstanceInformationByFilter, FltEnumerateInstanceInformationByFilter routine [Installable File System Drivers], fltkernel/FltEnumerateInstanceInformationByFilter, ifsk.fltenumerateinstanceinformationbyfilter
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	FltEnumerateInstanceInformationByFilter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltEnumerateInstanceInformationByFilter function


## -description


The <b>FltEnumerateInstanceInformationByFilter</b> routine provides information about instances of a given minifilter driver.


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. 


### -param Index [in]

Zero-based index of the instance for which the information is requested. 


### -param InformationClass [in]

Type of information requested. This parameter can have one of the following values. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>InstanceBasicInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548176">INSTANCE_BASIC_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstanceFullInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548185">INSTANCE_FULL_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstancePartialInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548190">INSTANCE_PARTIAL_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstanceAggregateStandardInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548172">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a> structure for the instance.  The <i>LegacyFilter</i> portion of the structure is not utilized. This structure is available starting with Windows Vista.

</td>
</tr>
</table>
 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter. 


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value. 


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer </i>points to. If the input value of <i>BufferSize</i> is too small, <b>FltEnumerateInstanceInformationByFilter</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltEnumerateInstanceInformationByFilter</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

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
The buffer that the <i>Buffer</i> parameter points to is not large enough to store the requested information. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
A matching instance was found, but it is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>InformationClass</i> parameter. For example, if <b>FilterAggregateStandardInformation</b> is specified on an operating system prior to Windows Vista, the routine will return STATUS_INVALID_PARAMETER.  This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
There are no more entries in the minifilter driver's instance list. This is a warning code. 

</td>
</tr>
</table>
 




## -remarks



The <i>Index</i> parameter is simply a way for <b>FltEnumerateInstanceInformationByFilter </b>to select among instances in the instance list for the minifilter driver specified by <i>Filter</i>.  Because the minifilter driver instances in the instance list can change at any time, two calls to <b>FltEnumerateInstanceInformationByFilter </b>with the same <i>Index</i> and <i>Filter</i> values are not guaranteed to return the same result. 

To enumerate all registered minifilter drivers, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a>. 

To list filter information for all registered minifilter drivers, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a>. 

To get filter information for a given minifilter driver, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543053">FltGetFilterInformation</a>. 

To enumerate all minifilter driver instances on a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>. 

To enumerate instances of all minifilter drivers on all volumes, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542090">FltEnumerateInstances</a>. 

To enumerate all volumes that are known to the Filter Manager, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542092">FltEnumerateVolumes</a>. 

.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542092">FltEnumerateVolumes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543053">FltGetFilterInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548172">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548176">INSTANCE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548185">INSTANCE_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548190">INSTANCE_PARTIAL_INFORMATION</a>
 

 

