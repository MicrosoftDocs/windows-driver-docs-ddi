---
UID: NF:fltkernel.FltTagFile
title: FltTagFile function (fltkernel.h)
description: FltTagFile sets a reparse tag on a file or directory.
old-location: ifsk\flttagfile.htm
tech.root: ifsk
ms.assetid: fbc8b596-1299-4dfa-953b-5730905f0e30
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_01cd7989-387a-4a7c-a45a-3a60a8b126c0.xml, FltTagFile, FltTagFile function [Installable File System Drivers], fltkernel/FltTagFile, ifsk.flttagfile
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
-	FltTagFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltTagFile function


## -description


<b>FltTagFile</b> sets a reparse tag on a file or directory. 


## -parameters




### -param InitiatingInstance [in]

Opaque instance pointer for the minifilter driver instance that initiated this I/O request. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

Pointer to a file object for the file or directory on which to set a reparse point. The file object must be opened for FILE_WRITE_DATA access. This parameter is required and cannot be <b>NULL</b>. 


### -param FileTag [in]

Reparse point tag. If an existing reparse tag is being modified, the tag specified in this parameter must match the tag of the reparse point to be modified. 


### -param Guid [in, optional]

GUID that uniquely identifies the type of reparse point. If <i>FileTag</i> is not a Microsoft tag, this parameter is required and cannot be <b>NULL</b>. If an existing reparse tag is being modified, the GUID specified in this parameter must match the GUID of the reparse point to be modified. 


### -param DataBuffer [in]

Pointer to a buffer that contains user-defined data for the reparse point. 


### -param DataBufferLength [in]

Size, in bytes, of the buffer that <i>DataBuffer </i>points to. 


## -returns



<b>FltTagFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltTagFile</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The file system does not support reparse points. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>FileTag</i> is not a Microsoft tag, and <b>NULL</b> was specified for <i>Guid</i>. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_REPARSE_TAG_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The reparse tag specified by the caller did not match the tag of the reparse point to be modified. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REPARSE_ATTRIBUTE_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
The reparse GUID specified by the caller did not match the GUID of the reparse point to be modified. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Minifilter drivers should use <b>FltTagFile</b> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a> to set a reparse point. 

Not all file systems support reparse points. The NTFS file system supports them; the FAT file system does not. Minifilter drivers can determine whether a file system supports reparse points by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>, specifying FileFsAttributeInformation for the <i>FsInformation</i> parameter, and examining the FILE_SUPPORTS_REPARSE_POINTS bit flag in the returned <a href="https://msdn.microsoft.com/library/windows/hardware/ff540251">FILE_FS_ATTRIBUTE_INFORMATION</a> structure. 

To remove an existing reparse point, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544608">FltUntagFile</a>. 

For more information about reparse points, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540251">FILE_FS_ATTRIBUTE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544820">FLT_TAG_DATA_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542988">FltFsControlFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544608">FltUntagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549452">IsReparseTagMicrosoft</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549462">IsReparseTagNameSurrogate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552012">REPARSE_DATA_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552014">REPARSE_GUID_DATA_BUFFER</a>
 

 

