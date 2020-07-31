---
UID: NF:fltkernel.FltUntagFile
title: FltUntagFile function (fltkernel.h)
description: FltUntagFile removes a reparse point from a file or directory.
old-location: ifsk\fltuntagfile.htm
tech.root: ifsk
ms.assetid: 728a9879-681b-4244-b931-7945a05e3d40
ms.date: 04/16/2018
keywords: ["FltUntagFile function"]
ms.keywords: FltApiRef_p_to_z_c1e51b69-c780-46bd-b3f0-b78cdc9c3b3f.xml, FltUntagFile, FltUntagFile function [Installable File System Drivers], fltkernel/FltUntagFile, ifsk.fltuntagfile
f1_keywords:
 - "fltkernel/FltUntagFile"
 - "FltUntagFile"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltUntagFile
targetos: Windows
req.typenames: 
---

# FltUntagFile function


## -description


<b>FltUntagFile</b> removes a reparse point from a file or directory. 


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



Minifilter drivers should use <b>FltUntagFile</b> instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-delete-reparse-point">FSCTL_DELETE_REPARSE_POINT</a> to delete a reparse point. 

A minifilter driver can set a reparse tag on a file or directory by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-flttagfile">FltTagFile</a>. 

For more information about reparse points, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_tag_data_buffer">FLT_TAG_DATA_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-delete-reparse-point">FSCTL_DELETE_REPARSE_POINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-get-reparse-point">FSCTL_GET_REPARSE_POINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-reparse-point">FSCTL_SET_REPARSE_POINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-flttagfile">FltTagFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-isreparsetagmicrosoft">IsReparseTagMicrosoft</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-isreparsetagnamesurrogate">IsReparseTagNameSurrogate</a>
 

 

