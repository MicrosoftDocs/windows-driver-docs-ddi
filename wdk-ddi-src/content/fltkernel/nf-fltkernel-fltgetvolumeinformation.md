---
UID: NF:fltkernel.FltGetVolumeInformation
title: FltGetVolumeInformation function
author: windows-driver-content
description: The FltGetVolumeInformation routine provides information about a given volume.
old-location: ifsk\fltgetvolumeinformation.htm
old-project: ifsk
ms.assetid: e25a7114-c1e5-4432-82a1-4c2e82d9fbc6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_79337a57-aa20-42b8-a85b-8268ef108564.xml, FltGetVolumeInformation, FltGetVolumeInformation routine [Installable File System Drivers], fltkernel/FltGetVolumeInformation, ifsk.fltgetvolumeinformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetVolumeInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetVolumeInformation function


## -description


The <b>FltGetVolumeInformation</b> routine provides information about a given volume.


## -parameters




### -param Volume [in]

Opaque pointer for the volume.  This parameter is required and cannot be <b>NULL</b>.


### -param InformationClass [in]

Type of information requested. This parameter is required and must be one of the following values. 

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
The <i>Buffer</i> parameter receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541631">FILTER_VOLUME_BASIC_INFORMATION</a> structure for the volume.

</td>
</tr>
<tr>
<td>
<b>FilterVolumeStandardInformation</b>

</td>
<td>
The <i>Buffer</i> parameter receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541647">FILTER_VOLUME_STANDARD_INFORMATION</a> structure for the volume.  This structure is available starting with Windows Vista.

</td>
</tr>
</table>
 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter.  This parameter is required and cannot be <b>NULL</b>.


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value.  This parameter is required.


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer </i>points to. If the input value of <i>BufferSize</i> is too small, <b>FltGetVolumeInformation </b>returns STATUS_BUFFER_TOO_SMALL and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>.


## -returns



<b>FltGetVolumeInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS status code, such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>InformationClass</i> parameter.  For example, if <b>FilterVolumeStandardInformation</b> is specified on an operating system prior to Windows Vista, the routine will return STATUS_INVALID_PARAMETER.  This is an error code.

</td>
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
</table>
 




## -remarks



Given an opaque volume pointer, such as that returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542092">FltEnumerateVolumes</a> routine, the <b>FltGetVolumeInformation</b> routine provides information about the volume pointed to by the opaque volume pointer, passed through the <i>Volume</i> parameter.  Note that the caller must eventually release the opaque volume pointer by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a> routine.

The <b>FltGetVolumeInformation</b> routine returns information for a single volume.  However, given a list of opaque volume pointers, the routine can be iteratively used to create a list of corresponding volume information structures.  In such a list, it is possible for two or more of the structures to contain identical volume names.  For more information, see <a href="https://msdn.microsoft.com/c05982dc-4124-4f9a-93b8-0e56ac296d1b">Understanding Volume Enumerations with Duplicate Volume Names</a>.

To list volume information for all volumes that are known to the filter manager, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542091">FltEnumerateVolumeInformation</a>. 

The following list contains related information, which may be of use:

<ul>
<li>
 To enumerate all registered minifilter drivers in the system, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a> routine.

</li>
<li>
 To obtain information about minifilter driver instances attached to a given volume, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a> routine.

</li>
<li>
 To enumerate minifilter driver instances for a given minifilter driver or volume, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542090">FltEnumerateInstances</a> routine.

</li>
<li>
 To enumerate all volumes in the system, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542092">FltEnumerateVolumes</a> routine.

</li>
<li>
 To obtain an opaque pointer for the volume represented by a given volume device object (VDO), call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543197">FltGetVolumeFromDeviceObject</a> routine.

</li>
<li>
 To obtain an opaque pointer for the volume that a given file stream resides on, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543206">FltGetVolumeFromFileObject</a> routine.

</li>
<li>
 To obtain an opaque pointer for the volume that a given minifilter driver instance is attached to, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543214">FltGetVolumeFromInstance</a> routine.

</li>
<li>
 To obtain an opaque pointer for the volume whose name matches a given volume name, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543220">FltGetVolumeFromName</a> routine.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541631">FILTER_VOLUME_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541647">FILTER_VOLUME_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542090">FltEnumerateInstances</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542091">FltEnumerateVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542092">FltEnumerateVolumes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543197">FltGetVolumeFromDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543206">FltGetVolumeFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543214">FltGetVolumeFromInstance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543220">FltGetVolumeFromName</a>
 

 

