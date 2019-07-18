---
UID: NF:fltkernel.FltEnumerateInstanceInformationByDeviceObject
title: FltEnumerateInstanceInformationByDeviceObject function (fltkernel.h)
description: The FltEnumerateInstanceInformationByDeviceObject routine provides information about minifilter driver instances and legacy filter drivers that are attached to the volume related to a specified device object.
old-location: ifsk\fltenumerateinstanceinformationbydeviceobject.htm
tech.root: ifsk
ms.assetid: 3E7754A3-3A7A-4036-B524-CBA40EF22048
ms.date: 04/16/2018
ms.keywords: FltEnumerateInstanceInformationByDeviceObject, FltEnumerateInstanceInformationByDeviceObject routine [Installable File System Drivers], fltkernel/FltEnumerateInstanceInformationByDeviceObject, ifsk.fltenumerateinstanceinformationbydeviceobject
ms.topic: function
f1_keywords:
 - "fltkernel/FltEnumerateInstanceInformationByDeviceObject"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltEnumerateInstanceInformationByDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltEnumerateInstanceInformationByDeviceObject function


## -description


The <b>FltEnumerateInstanceInformationByDeviceObject</b> routine provides information about minifilter driver instances and legacy filter drivers that are attached to the volume related to a specified device object.


## -parameters




### -param DeviceObject [in]

The device object for the related file object or volume.


### -param Index [in]

Zero-based index of the minifilter driver instance or legacy filter driver for which the information is requested.


### -param InformationClass [in]

Type of information to be returned for the minifilter driver instance or legacy filter driver. This parameter can have one of the following values.

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
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltuserstructures/ns-fltuserstructures-_instance_basic_information">INSTANCE_BASIC_INFORMATION</a> structure for a minifilter instance.  Legacy filter drivers are ignored.

</td>
</tr>
<tr>
<td>
<b>InstanceFullInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltuserstructures/ns-fltuserstructures-_instance_full_information">INSTANCE_FULL_INFORMATION</a> structure for a minifilter instance.  Legacy filter drivers are ignored.

</td>
</tr>
<tr>
<td>
<b>InstancePartialInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltuserstructures/ns-fltuserstructures-_instance_partial_information">INSTANCE_PARTIAL_INFORMATION</a> structure for a minifilter instance.  Legacy filter drivers are ignored.

</td>
</tr>
<tr>
<td>
<b>InstanceAggregateStandardInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltuserstructures/ns-fltuserstructures-_instance_aggregate_standard_information">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a> structure for a minifilter driver instance or legacy filter driver.

</td>
</tr>
</table>
 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter.


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value.


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer </i>points to. If the input value of <i>BufferSize</i> is too small, <b>FltEnumerateInstanceInformationByDeviceObject</b> returns <b>STATUS_BUFFER_TOO_SMALL</b> and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>.


## -returns



<b>FltEnumerateInstanceInformationByDeviceObject</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following: 

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
The buffer that the <i>Buffer</i> parameter points to is not large enough to store the requested information. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
A matching minifilter instance was found, but it is being torn down.  Note that this return value does not apply to legacy filter drivers because legacy filter drivers cannot be unloaded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>InformationClass</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
There are no more entries in the volume's instance/filter list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_VOLUME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No related volume was found for <i>DeviceObject</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
<i>DeviceObject</i>  is not a valid volume device object.

-or-

The volume related to <i>DeviceObject</i> was registered but   does not have any filter instances attached.

</td>
</tr>
</table>
 




## -remarks



Using the <i>Index</i> parameter is simply a way for <b>FltEnumerateInstanceInformationByDeviceObject</b> to select among minifilter driver instances and legacy filter drivers in the instance/filter list for the volume that is related to <i>DeviceObject</i>. Because the minifilter driver instances in the instance/filter list can change at any time, two calls to <b>FltEnumerateInstanceInformationByDeviceObject</b> with the same <i>Index</i> and <i>DeviceObject</i> values are not guaranteed to return the same result.

This routine will return both legacy filter driver information and minifilter driver instance information when the value of the <i>InformationClass</i> parameter is <b>InstanceAggregateStandardInformation</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyfilter">FltEnumerateInstanceInformationByFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyvolume">FltEnumerateInstanceInformationByVolume</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyvolumename">FltEnumerateInstanceInformationByVolumeName</a>
 

 

