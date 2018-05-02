---
UID: NF:fltkernel.FltGetVolumeGuidName
title: FltGetVolumeGuidName function
author: windows-driver-content
description: The FltGetVolumeGuidName routine returns the volume name for a given volume, in volume globally unique identifier (GUID) format.
old-location: ifsk\fltgetvolumeguidname.htm
old-project: ifsk
ms.assetid: 911d8b07-1313-4c4b-8d16-188857943327
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_b3c6abed-dbf8-44a2-92d6-470806b9a80f.xml, FltGetVolumeGuidName, FltGetVolumeGuidName routine [Installable File System Drivers], fltkernel/FltGetVolumeGuidName, ifsk.fltgetvolumeguidname
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetVolumeGuidName
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetVolumeGuidName function


## -description


The <b>FltGetVolumeGuidName</b> routine returns the volume name for a given volume, in volume globally unique identifier (GUID) format. 


## -parameters




### -param Volume [in]

Opaque pointer for the volume. Must be a local file system volume. This parameter is required and cannot be <b>NULL</b>. 


### -param VolumeGuidName [out]

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that receives the volume's GUID name. This parameter is required and cannot be <b>NULL</b>. 


### -param BufferSizeNeeded [out, optional]

Pointer to a caller-allocated variable that receives the size, in bytes, of the requested volume GUID name. If <b>FltGetVolumeGuidName</b> returns STATUS_BUFFER_TOO_SMALL, you can use the value of the variable to determine the required size for the structure that the <i>VolumeGuidName</i> parameter points to. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltGetVolumeGuidName</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

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
The buffer pointed to by the <i>VolumeGuidName</i> parameter is too small to hold the volume GUID. If the caller provides a non-<b>NULL</b> value for the <i>BufferSizeNeeded</i> parameter, this parameter receives the required buffer size. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltGetVolumeGuidName</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <i>Volume</i> parameter is a handle for a network volume. This is an error code. 

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



The returned volume GUID name is expressed in the following format: 

<b>\??\Volume{</b><i>GUID</i><b>}</b>

where <i>GUID</i> is a globally unique identifier that identifies the volume. 

This format, which is the same as that used by the mount manager, is described in <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 

<b>FltGetVolumeGuidName</b> cannot safely be called from a pre-mount or post-mount callback. It cannot safely be called because even when the post-mount callback is called, the mount processing has not been completed by the I/O manager, and this causes a deadlock with the mount manager in certain cases.

On Windows Vista and later, a minifilter driver can safely call <b>FltGetVolumeGuidName</b> from its <i>InstanceSetupCallback</i> routine (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551096">PFLT_INSTANCE_SETUP_CALLBACK</a>) because the callback is called on the first I/O operation for a new volume after all of the mount processing is completed. 

On Windows operating systems earlier than Windows Vista, <b>FltGetVolumeGuidName</b> cannot safely be called from an <i>InstanceSetupCallback</i> routine because the mount manager might issue a file I/O operation while holding a lock, which can cause a deadlock. 

It is important to note that the volume GUID is not the same as the volume object ID. The <i>volume GUID</i>, or <i>unique volume name</i>, is a file system-independent value; it is assigned to the underlying storage volume by the mount manager. The <i>volume object ID</i> is assigned to the file system volume by the file system. 

To get the volume object ID for a volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>, specifying <b>FileFsObjectIdInformation</b> for the <i>FsInformationClass</i> parameter. 

<b>FltGetVolumeGuidName</b> is roughly equivalent to the Win32 <b>GetVolumeNameForVolumeMountPoint</b> function. (<b>GetVolumeNameForVolumeMountPoint</b> is documented in the Microsoft Windows SDK.) 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540274">FILE_FS_OBJECTID_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551096">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>
 

 

