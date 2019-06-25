---
UID: NF:ntifs.FsRtlValidateReparsePointBuffer
title: FsRtlValidateReparsePointBuffer function (ntifs.h)
description: The FsRtlValidateReparsePointBuffer routine verifies that the specified reparse point buffer is valid.
old-location: ifsk\fsrtlvalidatereparsepointbuffer.htm
tech.root: ifsk
ms.assetid: fb67b116-12f5-4eef-ab05-f2056ccec4e3
ms.date: 04/16/2018
ms.keywords: FsRtlValidateReparsePointBuffer, FsRtlValidateReparsePointBuffer routine [Installable File System Drivers], fsrtlref_809c9e16-62b6-4a08-82d5-d6e86e7844ff.xml, ifsk.fsrtlvalidatereparsepointbuffer, ntifs/FsRtlValidateReparsePointBuffer
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlValidateReparsePointBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlValidateReparsePointBuffer function


## -description


The <b>FsRtlValidateReparsePointBuffer</b> routine verifies that the specified reparse point buffer is valid.


## -parameters




### -param BufferLength [in]

The length of the reparse point buffer.


### -param ReparseBuffer [in]

The reparse point buffer to be validated.


## -returns



The<b> FsRtlValidateReparsePointBuffer</b> returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The buffer is valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_REPARSE_DATA_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The buffer is not valid, such as if the buffer is too long or the length of the buffer and the data length in its header are not consistent.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_REPARSE_TAG_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The buffer has an invalid reparse tag.

</td>
</tr>
</table>
 




## -remarks



For more information about reparse points, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/reparse-points-in-a-file-system-filter-driver">Reparse Points in a File System Filter Driver</a>.

Reparse tags contain several bits that cannot be set except by system components. For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=179582">Reparse Point Tags</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_reparse_data_buffer">REPARSE_DATA_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_reparse_guid_data_buffer">REPARSE_GUID_DATA_BUFFER</a>
 

 

