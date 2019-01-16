---
UID: NS:ntifs._FSCTL_OFFLOAD_WRITE_OUTPUT
title: "_FSCTL_OFFLOAD_WRITE_OUTPUT"
description: The FSCTL_OFFLOAD_WRITE_OUTPUT structure contains the output for the FSCTL_OFFLOAD_WRITE control code request.
old-location: ifsk\fsctl_offload_write_output.htm
tech.root: ifsk
ms.assetid: 7293940B-A316-43C5-A5E8-6ED70EC6FDF8
ms.date: 04/16/2018
ms.keywords: "*PFSCTL_OFFLOAD_WRITE_OUTPUT, FSCTL_OFFLOAD_WRITE_OUTPUT, FSCTL_OFFLOAD_WRITE_OUTPUT structure [Installable File System Drivers], OFFLOAD_READ_FLAG_FILE_TOO_SMALL, PFSCTL_OFFLOAD_WRITE_OUTPUT, PFSCTL_OFFLOAD_WRITE_OUTPUT structure pointer [Installable File System Drivers], _FSCTL_OFFLOAD_WRITE_OUTPUT, ifsk.fsctl_offload_write_output, ntifs/FSCTL_OFFLOAD_WRITE_OUTPUT, ntifs/PFSCTL_OFFLOAD_WRITE_OUTPUT"
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FSCTL_OFFLOAD_WRITE_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: FSCTL_OFFLOAD_WRITE_OUTPUT, *PFSCTL_OFFLOAD_WRITE_OUTPUT
---

# _FSCTL_OFFLOAD_WRITE_OUTPUT structure


## -description


The <b>FSCTL_OFFLOAD_WRITE_OUTPUT</b> structure contains the output for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451122">FSCTL_OFFLOAD_WRITE</a> control code request.


## -struct-fields




### -field Size

The size of this structure. Set this member to <b>sizeof</b>(FSCTL_OFFLOAD_WRITE_OUTPUT).


### -field Flags

 Result flags for the offload write operation. This value is either 0 or the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="OFFLOAD_READ_FLAG_FILE_TOO_SMALL"></a><a id="offload_read_flag_file_too_small"></a><dl>
<dt><b>OFFLOAD_READ_FLAG_FILE_TOO_SMALL</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
The file to write to is too small for an offload operation.

</td>
</tr>
</table>
 


### -field LengthWritten

The length of data written for the transfer specified in <a href="https://msdn.microsoft.com/library/windows/hardware/hh451126">FSCTL_OFFLOAD_WRITE_INPUT</a>.


## -remarks



 The resulting length written, <b>LengthWritten</b>, may be smaller than what was originally specified in the <b>CopyLength</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451126">FSCTL_OFFLOAD_WRITE_INPUT</a>. A smaller value indicates that less data was able to be logically written with the specified <b>Token</b> than was requested.

 If less data than requested was written, the write operation  may be completed by performing another <a href="https://msdn.microsoft.com/library/windows/hardware/hh451122">FSCTL_OFFLOAD_WRITE</a> request. The next request uses an updated <b>FileOffset</b> member in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451126">FSCTL_OFFLOAD_WRITE_INPUT</a> structure with the value in <b>LengthWritten</b> and an adjusted write length of the previous length minus the value in <b>LengthWritten</b>. Also, an incomplete write operation can be completed through a non-offloaded write method, using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567121">ZwWriteFile</a> routine, for example.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451122">FSCTL_OFFLOAD_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451126">FSCTL_OFFLOAD_WRITE_INPUT</a>
 

 

