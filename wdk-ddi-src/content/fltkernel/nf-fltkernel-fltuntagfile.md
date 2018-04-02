---
UID: NF:fltkernel.FltUntagFile
title: FltUntagFile function
author: windows-driver-content
description: FltUntagFile removes a reparse point from a file or directory.
old-location: ifsk\fltuntagfile.htm
old-project: ifsk
ms.assetid: 728a9879-681b-4244-b931-7945a05e3d40
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_p_to_z_c1e51b69-c780-46bd-b3f0-b78cdc9c3b3f.xml, FltUntagFile, FltUntagFile function [Installable File System Drivers], fltkernel/FltUntagFile, ifsk.fltuntagfile
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
-	FltUntagFile
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
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



Minifilter drivers should use <b>FltUntagFile</b> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a> to delete a reparse point. 

A minifilter driver can set a reparse tag on a file or directory by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544589">FltTagFile</a>. 

For more information about reparse points, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544820">FLT_TAG_DATA_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544589">FltTagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549452">IsReparseTagMicrosoft</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549462">IsReparseTagNameSurrogate</a>
 

 

