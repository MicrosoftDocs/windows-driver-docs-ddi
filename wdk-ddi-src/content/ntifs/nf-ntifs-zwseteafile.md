---
UID: NF:ntifs.ZwSetEaFile
title: ZwSetEaFile function (ntifs.h)
description: The ZwSetEaFile routine sets extended-attribute (EA) values for a file.
old-location: kernel\zwseteafile.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ZwSetEaFile function"]
ms.keywords: ZwSetEaFile, ZwSetEaFile routine [Kernel-Mode Driver Architecture], kernel.zwseteafile, ntifs/ZwSetEaFile
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000   and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwSetEaFile
 - ntifs/ZwSetEaFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwSetEaFile
---

# ZwSetEaFile function


## -description

The <b>ZwSetEaFile</b> routine sets extended-attribute (EA) values for a file.

## -parameters

### -param FileHandle 

[in]
The handle for the file on which the operation is to be performed.

### -param IoStatusBlock 

[out]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and other information about the requested operation.

### -param Buffer 

[in]
A pointer to a caller-supplied, <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_full_ea_information">FILE_FULL_EA_INFORMATION</a>-structured input buffer that contains the extended attribute values to be set.

### -param Length 

[in]
Length, in bytes, of the buffer that the <i>Buffer</i> parameter points to.

## -returns

<b>ZwSetEaFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_EA_LIST_INCONSISTENT</dt>
</dl>
</td>
<td width="60%">
The EaList parameter is not formatted correctly. This is an error code.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_full_ea_information">FILE_FULL_EA_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-zwqueryeafile">ZwQueryEaFile</a>
