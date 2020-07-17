---
UID: NF:fltkernel.FltClose
title: FltClose function (fltkernel.h)
description: FltClose closes a file handle that was opened by FltCreateFile or FltCreateFileEx.
old-location: ifsk\fltclose.htm
tech.root: ifsk
ms.assetid: fd5967cc-fb30-4882-9567-4617b9f9e723
ms.date: 04/16/2018
keywords: ["FltClose function"]
ms.keywords: FltApiRef_a_to_d_f50e2397-1161-4e6e-9688-2baa417f6845.xml, FltClose, FltClose function [Installable File System Drivers], fltkernel/FltClose, ifsk.fltclose
f1_keywords:
 - "fltkernel/FltClose"
 - "FltClose"
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
- FltClose
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltClose function


## -description


<b>FltClose</b> closes a file handle that was opened by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex">FltCreateFileEx</a>. 


## -parameters




### -param FileHandle [in]

Handle created by a successful call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex">FltCreateFileEx</a>. 


## -returns



<b>FltClose</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>FileHandle</i> was not a valid file handle. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltClose</b> is only for closing file handles opened by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex">FltCreateFileEx</a>. It should not be used to close arbitrary handles. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex">FltCreateFileEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>
 

 

