---
UID: NF:fltkernel.FltUntagFile
title: FltUntagFile function
author: windows-driver-content
description: FltUntagFile removes a reparse point from a file or directory.
old-location: ifsk\fltuntagfile.htm
old-project: ifsk
ms.assetid: 728a9879-681b-4244-b931-7945a05e3d40
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltUntagFile function [Installable File System Drivers], FltApiRef_p_to_z_c1e51b69-c780-46bd-b3f0-b78cdc9c3b3f.xml, FltUntagFile, ifsk.fltuntagfile, fltkernel/FltUntagFile
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
-	FltUntagFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltUntagFile function


## -description


<b>FltUntagFile</b> removes a reparse point from a file or directory. 


## -syntax


````
NTSTATUS FltUntagFile(
  _In_     PFLT_INSTANCE InitiatingInstance,
  _In_     PFILE_OBJECT  FileObject,
  _In_     ULONG         FileTag,
  _In_opt_ GUID          *Guid
);
````


## -parameters




### -param InitiatingInstance [in]

Opaque instance pointer for the minifilter driver instance that initiated this I/O request. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

Pointer to a file object for the file or directory from which the reparse point is to be removed. The file object must be opened for FILE_WRITE_DATA access. This parameter is required and cannot be <b>NULL</b>. 


### -param FileTag [in]

Reparse point tag. The tag specified in this parameter must match the tag of the reparse point to be removed. 


### -param Guid [in, optional]

Globally unique identifier (GUID) that uniquely identifies the type of reparse point. If <i>FileTag</i> is not a Microsoft tag, this parameter is required and cannot be <b>NULL</b>. The GUID specified in this parameter must match the GUID of the reparse point to be removed. 


## -returns


<b>FltUntagFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_REPARSE_TAG_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The reparse tag specified by the caller did not match the tag of the reparse point to be deleted. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REPARSE_ATTRIBUTE_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
The reparse GUID specified by the caller did not match the GUID of the reparse point to be deleted. This is an error code. 

</td>
</tr>
</table> 



## -remarks


Minifilter drivers should use <b>FltUntagFile</b> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a> to delete a reparse point. 

A minifilter driver can set a reparse tag on a file or directory by calling <a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>. 

For more information about reparse points, see the Microsoft Windows SDK documentation. 



## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_tag_data_buffer.md">FLT_TAG_DATA_BUFFER</a>

<a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>

<a href="..\ntifs\nf-ntifs-isreparsetagmicrosoft.md">IsReparseTagMicrosoft</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>

<a href="..\ntifs\nf-ntifs-isreparsetagnamesurrogate.md">IsReparseTagNameSurrogate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltUntagFile function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

