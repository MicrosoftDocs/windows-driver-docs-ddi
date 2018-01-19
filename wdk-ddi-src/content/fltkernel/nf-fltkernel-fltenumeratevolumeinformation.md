---
UID: NF:fltkernel.FltEnumerateVolumeInformation
title: FltEnumerateVolumeInformation function
author: windows-driver-content
description: The FltEnumerateVolumeInformation routine provides information about volumes that are known to the filter manager.
old-location: ifsk\fltenumeratevolumeinformation.htm
old-project: ifsk
ms.assetid: cdec7faa-299c-4a4e-a037-9900bc3cffa1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltEnumerateVolumeInformation
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
req.alt-api: FltEnumerateVolumeInformation
req.alt-loc: FltMgr.lib,FltMgr.dll
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
req.typenames: EXpsFontRestriction
---

# FltEnumerateVolumeInformation function



## -description
The <b>FltEnumerateVolumeInformation</b> routine provides information about volumes that are known to the filter manager.



## -syntax

````
NTSTATUS FltEnumerateVolumeInformation(
  _In_  PFLT_FILTER                     Filter,
  _In_  ULONG                           Index,
  _In_  FILTER_VOLUME_INFORMATION_CLASS InformationClass,
  _Out_ PVOID                           Buffer,
  _In_  ULONG                           BufferSize,
  _Out_ PULONG                          BytesReturned
);
````


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
The <i>Buffer </i>parameter receives a <a href="..\fltuserstructures\ns-fltuserstructures-_filter_volume_basic_information.md">FILTER_VOLUME_BASIC_INFORMATION</a> structure for the volume. 

</td>
</tr>
<tr>
<td>
<b>FilterVolumeStandardInformation</b>

</td>
<td>
The <i>Buffer</i> parameter receives a <a href="..\fltuserstructures\ns-fltuserstructures-_filter_volume_standard_information.md">FILTER_VOLUME_STANDARD_INFORMATION</a> structure for the volume.  This structure is available starting with Windows Vista.

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
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer that the <i>Buffer</i> parameter points to is not large enough to store the requested information. This is an error code. 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>A matching volume was found, but it is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid value was specified for the <i>InformationClass</i> parameter. For example, if <b>FilterVolumeStandardInformation</b> is specified on an operating system prior to Windows Vista, the routine returns STATUS_INVALID_PARAMETER.  This is an error code. 
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>There are no more entries in the global list of volumes. This is a warning code. 

 


## -remarks
Using the <i>Index</i> parameter is simply a way for the <b>FltEnumerateVolumeInformation</b> routine to select among volumes in the filter manager's global list of volumes. Two calls to <b>FltEnumerateVolumeInformation</b> with the same value of the <i>Index</i> parameter do not necessarily return the same result because volumes can be mounted or dismounted at any time. 

If <b>FltEnumerateVolumeInformation</b> is used to create a list of volume information structures, it is possible for two or more of these structures to contain identical volume names.  For more information, see <a href="https://msdn.microsoft.com/c05982dc-4124-4f9a-93b8-0e56ac296d1b">Understanding Volume Enumerations with Duplicate Volume Names</a>.

To enumerate all registered minifilter drivers, call <a href="..\fltkernel\nf-fltkernel-fltenumeratefilters.md">FltEnumerateFilters</a>. 

To enumerate all volumes that are known to the filter manager, call <a href="..\fltkernel\nf-fltkernel-fltenumeratevolumes.md">FltEnumerateVolumes</a>. 

To list filter information for all registered minifilter drivers, call <a href="..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md">FltEnumerateFilterInformation</a>. 

To get filter information for a given minifilter driver, call <a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>. 

To enumerate all instances of a given minifilter driver, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>. 

To enumerate all minifilter driver instances on a given volume, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>. 

To enumerate instances of all minifilter drivers on all volumes, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstances.md">FltEnumerateInstances</a>. 


## -see-also
<dl>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_filter_volume_basic_information.md">FILTER_VOLUME_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_filter_volume_standard_information.md">FILTER_VOLUME_STANDARD_INFORMATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md">FltEnumerateFilterInformation</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltenumeratefilters.md">FltEnumerateFilters</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltenumerateinstances.md">FltEnumerateInstances</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltenumeratevolumes.md">FltEnumerateVolumes</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltEnumerateVolumeInformation routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

