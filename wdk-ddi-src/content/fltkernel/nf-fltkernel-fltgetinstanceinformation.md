---
UID: NF:fltkernel.FltGetInstanceInformation
title: FltGetInstanceInformation function (fltkernel.h)
description: The FltGetInstanceInformation routine returns information about a minifilter driver instance.
old-location: ifsk\fltgetinstanceinformation.htm
tech.root: ifsk
ms.assetid: eb8ba04a-dbf8-4964-8b45-2620447418b5
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_d476d1f7-fff3-45d1-91e9-25879ab9e90e.xml, FltGetInstanceInformation, FltGetInstanceInformation routine [Installable File System Drivers], fltkernel/FltGetInstanceInformation, ifsk.fltgetinstanceinformation
ms.topic: function
f1_keywords:
 - "fltkernel/FltGetInstanceInformation"
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
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetInstanceInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetInstanceInformation function


## -description


The <b>FltGetInstanceInformation</b> routine returns information about a minifilter driver instance. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. 


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
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_basic_information">INSTANCE_BASIC_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstanceFullInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_full_information">INSTANCE_FULL_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstancePartialInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_partial_information">INSTANCE_PARTIAL_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstanceAggregateStandardInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_aggregate_standard_information">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a> structure for the instance.  The <b>LegacyFilter</b> portion of the structure is not utilized. This structure is available starting with Windows Vista.

</td>
</tr>
</table>
 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter. 


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value. 


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer </i>points to. If the input value of <i>BufferSize</i> is too small, <b>FltGetInstanceInformation</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetInstanceInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following:

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>InformationClass</i> parameter.  For example, if <b>InstanceAggregateStandardInformation</b> is specified on the operating systems prior to Windows Vista, the routine will return STATUS_INVALID_PARAMETER.  This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Given a pointer to a minifilter instance, this routine returns information about the minifilter instance.  The type of instance information returned is determined by the <i>InformationClass</i> parameter. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratefilterinformation">FltEnumerateFilterInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyfilter">FltEnumerateInstanceInformationByFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyvolume">FltEnumerateInstanceInformationByVolume</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilterinformation">FltGetFilterInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_aggregate_standard_information">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_basic_information">INSTANCE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_full_information">INSTANCE_FULL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_partial_information">INSTANCE_PARTIAL_INFORMATION</a>
 

 

