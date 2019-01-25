---
UID: NF:fltkernel.FltGetVolumeProperties
title: FltGetVolumeProperties function (fltkernel.h)
description: The FltGetVolumeProperties routine returns volume property information for the given volume.
old-location: ifsk\fltgetvolumeproperties.htm
tech.root: ifsk
ms.assetid: 1e975626-fa47-456f-a2a9-48506c67cbe5
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_3afcdc71-3007-478e-8699-a1480ca118b8.xml, FltGetVolumeProperties, FltGetVolumeProperties routine [Installable File System Drivers], fltkernel/FltGetVolumeProperties, ifsk.fltgetvolumeproperties
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
-	FltGetVolumeProperties
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetVolumeProperties function


## -description


The <b>FltGetVolumeProperties</b> routine returns volume property information for the given volume. 


## -parameters




### -param Volume [in]

Opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>. 


### -param VolumeProperties [out]

Pointer to a caller-allocated buffer that receives the requested volume property information. If <i>Length</i> is zero on input, this parameter is ignored. Otherwise, this parameter is required and cannot be <b>NULL</b>. 


### -param VolumePropertiesLength

<p>Size, in bytes, of the buffer pointed to by the <i>VolumeProperties</i> parameter. This parameter is optional and can be zero. If it is zero, <i>LengthReturned</i> receives the size, in bytes, of the buffer needed to hold the volume properties. If this parameter is nonzero, it must be at least the value of <b>sizeof(</b>FLT_VOLUME_PROPERTIES<b>)</b>. </p>


### -param LengthReturned [out]

Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in <i>VolumeProperties</i>. If <b>FltGetVolumeProperties</b> returns STATUS_BUFFER_TOO_SMALL, or if <i>Length</i> is zero on input, this parameter instead receives the size, in bytes, of the buffer needed to hold the volume properties. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetVolumeProperties</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>VolumeProperties</i> parameter points to is large enough to hold the fixed portion of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544823">FLT_VOLUME_PROPERTIES</a> structure but not the <b>FileSystemDriverName</b>, <b>FileSystemDeviceName</b>, or <b>RealDeviceName</b> members. In this case, only the fixed portion of the volume information is returned in the buffer pointed to by the <i>VolumeProperties</i> parameter. The <i>LengthReturned</i> parameter receives the actual length, in bytes, of data returned. This is a warning code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>VolumeProperties</i> parameter points to is not large enough to hold the volume property information. The <i>LengthReturned</i> parameter receives the required buffer size. In this case, no volume information is returned. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltGetVolumeProperties</b> only returns information that can safely be queried during the mount process without risk of a system deadlock. Therefore, a minifilter driver commonly calls this routine from a post-mount callback function or an <i>InstanceSetupCallback</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551096">PFLT_INSTANCE_SETUP_CALLBACK</a>) routine to determine whether to attach to a given volume. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544823">FLT_VOLUME_PROPERTIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551096">PFLT_INSTANCE_SETUP_CALLBACK</a>
 

 

