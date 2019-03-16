---
UID: NF:fltkernel.FltQueryEaFile
title: FltQueryEaFile function (fltkernel.h)
description: FltQueryEaFile returns information about extended-attribute (EA) values for a file.
old-location: ifsk\fltqueryeafile.htm
tech.root: ifsk
ms.assetid: 3981ab65-2d21-4188-88dc-04eb7aff0869
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_cfb86d4e-84c0-4ab7-a813-094420e437cc.xml, FltQueryEaFile, FltQueryEaFile function [Installable File System Drivers], fltkernel/FltQueryEaFile, ifsk.fltqueryeafile
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP3, Windows Server 2003 SP1, and later versions of the Windows operating system.
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
- FltQueryEaFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltQueryEaFile function


## -description


<b>FltQueryEaFile</b> returns information about extended-attribute (EA) values for a file. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the minifilter driver instance that the <i>QueryEa</i> operation is to be sent to. The instance must be attached to the volume where the file resides. 


### -param FileObject [in]

File object pointer for the file. 


### -param ReturnedEaData [out]

Pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>-structured input buffer where the extended attribute values are to be returned. 


### -param Length [in]

Length, in bytes, of the buffer that the <i>ReturnedEaData</i> parameter points to. 


### -param ReturnSingleEntry [in]

Set to <b>TRUE</b> if <b>FltQueryEaFile</b> should return only the first entry that is found. 


### -param EaList [in, optional]

Pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540295">FILE_GET_EA_INFORMATION</a>-structured input buffer specifying the extended attributes to be queried. This parameter is optional and can be <b>NULL</b>. 


### -param EaListLength [in]

Length, in bytes, of the buffer that the <i>EaList</i> parameter points to. 


### -param EaIndex [in, optional]

Index of the entry at which to begin scanning the file's extended-attribute list. This parameter is ignored if the <i>EaList</i> parameter points to a nonempty list. This parameter is optional and can be <b>NULL</b>. 


### -param RestartScan [in]

Set to <b>TRUE</b> if <b>FltQueryEaFile</b> should begin the scan at the first entry in the file's extended-attribute list. If this parameter is not set to <b>TRUE</b>, the scan is resumed from a previous call to <b>FltQueryEaFile</b>. 


### -param LengthReturned [out, optional]

Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the <i>ReturnedEaData</i> buffer. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltQueryEaFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_EAS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The file system does not support extended attributes. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The instance or volume is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltQueryEaFile</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540295">FILE_GET_EA_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544500">FltSetEaFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548252">IoCheckEaBufferValidity</a>
 

 

