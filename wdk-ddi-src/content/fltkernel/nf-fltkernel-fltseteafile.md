---
UID: NF:fltkernel.FltSetEaFile
title: FltSetEaFile function (fltkernel.h)
description: FltSetEaFile sets extended-attribute (EA) values for a file.
old-location: ifsk\fltseteafile.htm
tech.root: ifsk
ms.assetid: 06427ef2-43e9-46c1-92e5-ab1b6146cc43
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_7e886e7f-a5f4-4a87-9322-7818e31c84af.xml, FltSetEaFile, FltSetEaFile function [Installable File System Drivers], fltkernel/FltSetEaFile, ifsk.fltseteafile
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltSetEaFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSetEaFile function


## -description


<b>FltSetEaFile</b> sets extended-attribute (EA) values for a file. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the minifilter driver instance that the SetEa operation is to be sent to. The instance must be attached to the volume where the file resides. 


### -param FileObject [in]

File object pointer for the file. 


### -param EaBuffer [in]

Pointer to a caller-supplied, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>-structured input buffer that contains the extended attribute (EA) values to be set. 


### -param Length [in]

Length, in bytes, of the buffer that the <i>EaBuffer</i> parameter points to. 


## -returns



<b>FltSetEaFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
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
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543435">FltQueryEaFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548252">IoCheckEaBufferValidity</a>
 

 

