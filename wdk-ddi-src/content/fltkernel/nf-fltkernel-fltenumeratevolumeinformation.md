---
UID: NF:fltkernel.FltEnumerateVolumeInformation
title: FltEnumerateVolumeInformation function (fltkernel.h)
description: The FltEnumerateVolumeInformation routine provides information about volumes that are known to the filter manager.
old-location: ifsk\fltenumeratevolumeinformation.htm
tech.root: ifsk
ms.assetid: cdec7faa-299c-4a4e-a037-9900bc3cffa1
ms.date: 04/16/2018
keywords: ["FltEnumerateVolumeInformation function"]
ms.keywords: FltApiRef_e_to_o_2fec9273-857a-4c22-b970-27882f88d58d.xml, FltEnumerateVolumeInformation, FltEnumerateVolumeInformation routine [Installable File System Drivers], fltkernel/FltEnumerateVolumeInformation, ifsk.fltenumeratevolumeinformation
f1_keywords:
 - "fltkernel/FltEnumerateVolumeInformation"
 - "FltEnumerateVolumeInformation"
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
- FltEnumerateVolumeInformation
targetos: Windows
req.typenames: 
---

# FltEnumerateVolumeInformation function


## -description


The <b>FltEnumerateVolumeInformation</b> routine provides information about volumes that are known to the filter manager.


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param Index [in]

Zero-based index of the volume for which the information is requested.


### -param InformationClass [in]

Type of information requested. This parameter can have one of the following values. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FilterVolumeBasicInformation</b>

</td>
<td>
The <i>Buffer </i>parameter receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_filter_volume_basic_information">FILTER_VOLUME_BASIC_INFORMATION</a> structure for the volume. 

</td>
</tr>
<tr>
<td>
<b>FilterVolumeStandardInformation</b>

</td>
<td>
The <i>Buffer</i> parameter receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_filter_volume_standard_information">FILTER_VOLUME_STANDARD_INFORMATION</a> structure for the volume.  This structure is available starting with Windows Vista.

</td>
</tr>
</table>
 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter.


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value.


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer </i>points to. If the input value of <i>BufferSize</i> is too small, <b>FltEnumerateVolumeInformation</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>.


## -returns



<b>FltEnumerateVolumeInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

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
A matching volume was found, but it is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>InformationClass</i> parameter. For example, if <b>FilterVolumeStandardInformation</b> is specified on an operating system prior to Windows Vista, the routine returns STATUS_INVALID_PARAMETER.  This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
There are no more entries in the global list of volumes. This is a warning code. 

</td>
</tr>
</table>
 




## -remarks



Using the <i>Index</i> parameter is simply a way for the <b>FltEnumerateVolumeInformation</b> routine to select among volumes in the filter manager's global list of volumes. Two calls to <b>FltEnumerateVolumeInformation</b> with the same value of the <i>Index</i> parameter do not necessarily return the same result because volumes can be mounted or dismounted at any time. 

If <b>FltEnumerateVolumeInformation</b> is used to create a list of volume information structures, it is possible for two or more of these structures to contain identical volume names.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/understanding-volume-enumerations-with-duplicate-volume-names">Understanding Volume Enumerations with Duplicate Volume Names</a>.

To enumerate all registered minifilter drivers, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratefilters">FltEnumerateFilters</a>. 

To enumerate all volumes that are known to the filter manager, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratevolumes">FltEnumerateVolumes</a>. 

To list filter information for all registered minifilter drivers, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratefilterinformation">FltEnumerateFilterInformation</a>. 

To get filter information for a given minifilter driver, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilterinformation">FltGetFilterInformation</a>. 

To enumerate all instances of a given minifilter driver, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyfilter">FltEnumerateInstanceInformationByFilter</a>. 

To enumerate all minifilter driver instances on a given volume, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyvolume">FltEnumerateInstanceInformationByVolume</a>. 

To enumerate instances of all minifilter drivers on all volumes, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstances">FltEnumerateInstances</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_filter_volume_basic_information">FILTER_VOLUME_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_filter_volume_standard_information">FILTER_VOLUME_STANDARD_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratefilterinformation">FltEnumerateFilterInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratefilters">FltEnumerateFilters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyfilter">FltEnumerateInstanceInformationByFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyvolume">FltEnumerateInstanceInformationByVolume</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstances">FltEnumerateInstances</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratevolumes">FltEnumerateVolumes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilterinformation">FltGetFilterInformation</a>
 

 

