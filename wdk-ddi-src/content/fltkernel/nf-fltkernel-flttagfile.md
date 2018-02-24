---
UID: NF:fltkernel.FltTagFile
title: FltTagFile function
author: windows-driver-content
description: FltTagFile sets a reparse tag on a file or directory.
old-location: ifsk\flttagfile.htm
old-project: ifsk
ms.assetid: fbc8b596-1299-4dfa-953b-5730905f0e30
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltTagFile function [Installable File System Drivers], FltTagFile, FltApiRef_p_to_z_01cd7989-387a-4a7c-a45a-3a60a8b126c0.xml, ifsk.flttagfile, fltkernel/FltTagFile
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltTagFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltTagFile function


## -description


<b>FltTagFile</b> sets a reparse tag on a file or directory. 


## -syntax


````
NTSTATUS FltTagFile(
  _In_     PFLT_INSTANCE InitiatingInstance,
  _In_     PFILE_OBJECT  FileObject,
  _In_     ULONG         FileTag,
  _In_opt_ GUID          *Guid,
  _In_     PVOID         DataBuffer,
  _In_     USHORT        DataBufferLength
);
````


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

Not all file systems support reparse points. The NTFS file system supports them; the FAT file system does not. Minifilter drivers can determine whether a file system supports reparse points by calling <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>, specifying FileFsAttributeInformation for the <i>FsInformation</i> parameter, and examining the FILE_SUPPORTS_REPARSE_POINTS bit flag in the returned <a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a> structure. 

To remove an existing reparse point, call <a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>. 

For more information about reparse points, see the Microsoft Windows SDK documentation. 




## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_tag_data_buffer.md">FLT_TAG_DATA_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>



<a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>



<a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>



<a href="..\ntifs\ns-ntifs-_reparse_guid_data_buffer.md">REPARSE_GUID_DATA_BUFFER</a>



<a href="..\ntifs\nf-ntifs-isreparsetagmicrosoft.md">IsReparseTagMicrosoft</a>



<a href="..\fltkernel\nf-fltkernel-fltfscontrolfile.md">FltFsControlFile</a>



<a href="..\ntifs\ns-ntifs-_reparse_guid_data_buffer.md">REPARSE_GUID_DATA_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>



<a href="..\fltkernel\nf-fltkernel-fltfscontrolfile.md">FltFsControlFile</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltTagFile function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

