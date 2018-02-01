---
UID: NF:fltkernel.FltEnumerateInstanceInformationByVolumeName
title: FltEnumerateInstanceInformationByVolumeName function
author: windows-driver-content
description: The FltEnumerateInstanceInformationByVolumeName routine provides information about minifilter driver instances and legacy filter drivers that are attached to the volume with the specified name.
old-location: ifsk\fltenumerateinstanceinformationbyvolumename.htm
old-project: ifsk
ms.assetid: BBABE50B-98FF-440E-B5B0-11C8F901D8FE
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltEnumerateInstanceInformationByVolumeName, ifsk.fltenumerateinstanceinformationbyvolumename, FltEnumerateInstanceInformationByVolumeName routine [Installable File System Drivers], fltkernel/FltEnumerateInstanceInformationByVolumeName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltEnumerateInstanceInformationByVolumeName
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltEnumerateInstanceInformationByVolumeName function


## -description


The <b>FltEnumerateInstanceInformationByVolumeName</b> routine provides information about minifilter driver instances and legacy filter drivers that are attached to the volume with the specified name.


## -syntax


````
NTSTATUS FltEnumerateInstanceInformationByVolumeName(
  _In_  PUNICODE_STRING            VolumeName,
  _In_  ULONG                      Index,
  _In_  INSTANCE_INFORMATION_CLASS InformationClass,
  _Out_ PVOID                      Buffer,
  _In_  ULONG                      BufferSize,
  _Out_ PULONG                     BytesReturned
);
````


## -parameters




### -param VolumeName [in]

The name of the volume to enumerate filter instances for.


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
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="..\fltuserstructures\ns-fltuserstructures-_instance_basic_information.md">INSTANCE_BASIC_INFORMATION</a> structure for a minifilter instance.  Legacy filter drivers are ignored.

</td>
</tr>
<tr>
<td>
<b>InstanceFullInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="..\fltuserstructures\ns-fltuserstructures-_instance_full_information.md">INSTANCE_FULL_INFORMATION</a> structure for a minifilter instance.  Legacy filter drivers are ignored.

</td>
</tr>
<tr>
<td>
<b>InstancePartialInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="..\fltuserstructures\ns-fltuserstructures-_instance_partial_information.md">INSTANCE_PARTIAL_INFORMATION</a> structure for a minifilter instance.  Legacy filter drivers are ignored.

</td>
</tr>
<tr>
<td>
<b>InstanceAggregateStandardInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="..\fltuserstructures\ns-fltuserstructures-_instance_aggregate_standard_information.md">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a> structure for a minifilter driver instance or legacy filter driver.

</td>
</tr>
</table> 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter.


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value.


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer </i>points to. If the input value of <i>BufferSize</i> is too small, <b>FltEnumerateInstanceInformationByVolumeName</b> returns <b>STATUS_BUFFER_TOO_SMALL</b> and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>.


## -returns


<b>FltEnumerateInstanceInformationByVolumeName</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following: 
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

-or-

<i>VolumeName</i> contains an invalid volume name.

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
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The volume specified in <i>VolumeName</i>  does not exist.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The path for the volume specified in <i>VolumeName</i>  does not exist.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_VOLUME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The volume specified by <i>VolumeName</i>   does not have any filter instances attached.

-or-

The volume specified by <i>VolumeName</i> is being removed from the system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The volume specified by <i>VolumeName</i> was registered but   does not have any filter instances attached.

</td>
</tr>
</table> 



## -remarks


Using the <i>Index</i> parameter is simply a way for <b>FltEnumerateInstanceInformationByVolumeName</b> to select among minifilter driver instances and legacy filter drivers in the instance/filter list for the volume that is specified by <i>VolumeName</i>. Because the minifilter driver instances in the instance/filter list can change at any time, two calls to <b>FltEnumerateInstanceInformationByVolumeName</b> with the same <i>Index</i> and <i>VolumeName</i> values are not guaranteed to return the same result.

This routine will return both legacy filter driver information and minifilter driver instance information when the value of the <i>InformationClass</i> parameter is <b>InstanceAggregateStandardInformation</b>.



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>

<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbydeviceobject.md">FltEnumerateInstanceInformationByDeviceObject</a>

<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltEnumerateInstanceInformationByVolumeName routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

