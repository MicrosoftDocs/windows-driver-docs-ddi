---
UID: NF:fltkernel.FltGetVolumeFromName
title: FltGetVolumeFromName function
author: windows-driver-content
description: The FltGetVolumeFromName routine returns an opaque pointer for the volume whose name matches the value of the VolumeName parameter.
old-location: ifsk\fltgetvolumefromname.htm
tech.root: ifsk
ms.assetid: 813b914a-05d6-4e5a-9420-f87e94ee9e96
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_1132de70-bc75-48a2-b0ae-d5b6d67a0a07.xml, FltGetVolumeFromName, FltGetVolumeFromName routine [Installable File System Drivers], fltkernel/FltGetVolumeFromName, ifsk.fltgetvolumefromname
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetVolumeFromName
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetVolumeFromName function


## -description


\The <b>FltGetVolumeFromName</b> routine returns an opaque pointer for the volume whose name matches the value of the <i>VolumeName</i> parameter. 


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param VolumeName [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the volume name (for example, "\Device\HarddiskVolume1", "\DosDevices\D:", "\\??\D:", or "D:"). This parameter is required and cannot be <b>NULL</b>. 


### -param RetVolume [out]

Pointer to a caller-allocated variable that receives an opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetVolumeFromName</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not have FILE_READ_DATA access to the volume. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The volume is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>VolumeName</i> parameter. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_VOLUME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching volume was found. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltGetVolumeFromName</b> searches the Filter Manager's global list of volumes for a volume whose name matches <i>VolumeName</i>. The caller must have FILE_READ_DATA access to the volume. To locate the volume structure, <b>FltGetVolumeFromName</b> must first open the volume.

<b>FltGetVolumeFromName</b> adds a rundown reference to the opaque volume pointer returned in the <i>RetVolume</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>. Thus every successful call to <b>FltGetVolumeFromName</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To get the volume name for a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543249">FltGetVolumeName</a>. 

To get the volume GUID name for a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543230">FltGetVolumeGuidName</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543050">FltGetFilterFromName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543230">FltGetVolumeGuidName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543239">FltGetVolumeInstanceFromName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543249">FltGetVolumeName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

