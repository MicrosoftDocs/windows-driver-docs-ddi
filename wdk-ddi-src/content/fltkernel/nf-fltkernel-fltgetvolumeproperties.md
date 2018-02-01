---
UID: NF:fltkernel.FltGetVolumeProperties
title: FltGetVolumeProperties function
author: windows-driver-content
description: The FltGetVolumeProperties routine returns volume property information for the given volume.
old-location: ifsk\fltgetvolumeproperties.htm
old-project: ifsk
ms.assetid: 1e975626-fa47-456f-a2a9-48506c67cbe5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltGetVolumeProperties, fltkernel/FltGetVolumeProperties, FltGetVolumeProperties routine [Installable File System Drivers], ifsk.fltgetvolumeproperties, FltApiRef_e_to_o_3afcdc71-3007-478e-8699-a1480ca118b8.xml
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
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltGetVolumeProperties
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetVolumeProperties function


## -description


The <b>FltGetVolumeProperties</b> routine returns volume property information for the given volume. 


## -syntax


````
NTSTATUS FltGetVolumeProperties(
  _In_  PFLT_VOLUME            Volume,
  _Out_ PFLT_VOLUME_PROPERTIES VolumeProperties,
  _In_  ULONG                  Length,
  _Out_ PULONG                 LengthReturned
);
````


## -parameters




### -param Volume [in]

Opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>. 


### -param VolumeProperties [out]

Pointer to a caller-allocated buffer that receives the requested volume property information. If <i>Length</i> is zero on input, this parameter is ignored. Otherwise, this parameter is required and cannot be <b>NULL</b>. 


### -param VolumePropertiesLength

TBD


### -param LengthReturned [out]

Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in <i>VolumeProperties</i>. If <b>FltGetVolumeProperties</b> returns STATUS_BUFFER_TOO_SMALL, or if <i>Length</i> is zero on input, this parameter instead receives the size, in bytes, of the buffer needed to hold the volume properties. This parameter is required and cannot be <b>NULL</b>. 


#### - Length [in]

Size, in bytes, of the buffer pointed to by the <i>VolumeProperties</i> parameter. This parameter is optional and can be zero. If it is zero, <i>LengthReturned</i> receives the size, in bytes, of the buffer needed to hold the volume properties. If this parameter is nonzero, it must be at least the value of <b>sizeof(</b>FLT_VOLUME_PROPERTIES<b>)</b>. 


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
The buffer that the <i>VolumeProperties</i> parameter points to is large enough to hold the fixed portion of the <a href="..\fltkernel\ns-fltkernel-_flt_volume_properties.md">FLT_VOLUME_PROPERTIES</a> structure but not the <b>FileSystemDriverName</b>, <b>FileSystemDeviceName</b>, or <b>RealDeviceName</b> members. In this case, only the fixed portion of the volume information is returned in the buffer pointed to by the <i>VolumeProperties</i> parameter. The <i>LengthReturned</i> parameter receives the actual length, in bytes, of data returned. This is a warning code. 

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


<b>FltGetVolumeProperties</b> only returns information that can safely be queried during the mount process without risk of a system deadlock. Therefore, a minifilter driver commonly calls this routine from a post-mount callback function or an <i>InstanceSetupCallback</i> (<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>) routine to determine whether to attach to a given volume. 



## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_volume_properties.md">FLT_VOLUME_PROPERTIES</a>

<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetVolumeProperties routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

