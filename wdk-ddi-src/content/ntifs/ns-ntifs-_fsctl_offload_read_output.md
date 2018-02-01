---
UID: NS:ntifs._FSCTL_OFFLOAD_READ_OUTPUT
title: "_FSCTL_OFFLOAD_READ_OUTPUT"
author: windows-driver-content
description: The FSCTL_OFFLOAD_READ_OUTPUT structure contains the output for the FSCTL_OFFLOAD_READ control code request.
old-location: ifsk\fsctl_offload_read_output.htm
old-project: ifsk
ms.assetid: 418E66FA-BECD-4F9F-B28C-962995C637B9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/FSCTL_OFFLOAD_READ_OUTPUT, FSCTL_OFFLOAD_READ_OUTPUT, PFSCTL_OFFLOAD_READ_OUTPUT, OFFLOAD_READ_FLAG_CANNOT_OFFLOAD_BEYOND_CURRENT_RANGE, ntifs/PFSCTL_OFFLOAD_READ_OUTPUT, _FSCTL_OFFLOAD_READ_OUTPUT, FSCTL_OFFLOAD_READ_OUTPUT structure [Installable File System Drivers], OFFLOAD_READ_FLAG_ALL_ZERO_BEYOND_CURRENT_RANGE, OFFLOAD_READ_FLAG_FILE_TOO_SMALL, *PFSCTL_OFFLOAD_READ_OUTPUT, PFSCTL_OFFLOAD_READ_OUTPUT structure pointer [Installable File System Drivers], ifsk.fsctl_offload_read_output
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FSCTL_OFFLOAD_READ_OUTPUT
product: Windows
targetos: Windows
req.typenames: FSCTL_OFFLOAD_READ_OUTPUT, *PFSCTL_OFFLOAD_READ_OUTPUT
---

# _FSCTL_OFFLOAD_READ_OUTPUT structure


## -description


The <b>FSCTL_OFFLOAD_READ_OUTPUT</b> structure contains the output for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451101">FSCTL_OFFLOAD_READ</a> control code request.


## -syntax


````
typedef struct _FSCTL_OFFLOAD_READ_OUTPUT {
  ULONG     Size;
  ULONG     Flags;
  ULONGLONG TransferLength;
  UCHAR     Token[512];
} FSCTL_OFFLOAD_READ_OUTPUT, *PFSCTL_OFFLOAD_READ_OUTPUT;
````


## -struct-fields




### -field Size

The size of this structure. Set this member to <b>sizeof</b>(FSCTL_OFFLOAD_READ_OUTPUT).


### -field Flags

 Result flags. This value is a bitwise <b>OR</b> combination of these values:
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
The file to read from is too small for an offload operation.

</td>
</tr>
<tr>
<td width="40%"><a id="OFFLOAD_READ_FLAG_ALL_ZERO_BEYOND_CURRENT_RANGE"></a><a id="offload_read_flag_all_zero_beyond_current_range"></a><dl>
<dt><b>OFFLOAD_READ_FLAG_ALL_ZERO_BEYOND_CURRENT_RANGE</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The range extending beyond the selected range contains all zeros.

</td>
</tr>
<tr>
<td width="40%"><a id="OFFLOAD_READ_FLAG_CANNOT_OFFLOAD_BEYOND_CURRENT_RANGE"></a><a id="offload_read_flag_cannot_offload_beyond_current_range"></a><dl>
<dt><b>OFFLOAD_READ_FLAG_CANNOT_OFFLOAD_BEYOND_CURRENT_RANGE</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
The offload operation cannot complete beyond the selected range. An non-offloaded read method should be used to complete the operation.

</td>
</tr>
</table> 


### -field TransferLength

The length, in bytes, of data represented by <b>Token</b>.


### -field Token

A byte array that contains a token structure, <a href="..\ntddstor\ns-ntddstor-_storage_offload_token.md">STORAGE_OFFLOAD_TOKEN</a>, representing a file data within a range specified in <a href="..\ntifs\ns-ntifs-_fsctl_offload_read_input.md">FSCTL_OFFLOAD_READ_INPUT</a>. The contents of <b>Token</b>  must remain unmodified between offload operations.


## -remarks


If the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451101">FSCTL_OFFLOAD_READ</a> operation is successful, the storage device's copy provider returns, in <b>FSCTL_OFFLOAD_READ_OUTPUT</b>, a unique token value identifying the portion of file data read. 

The  copy provider retains the data read for the duration in the <b>TokenTimeToLive</b> member of the <a href="..\ntifs\ns-ntifs-_fsctl_offload_read_input.md">FSCTL_OFFLOAD_READ_INPUT</a> structure.

<b>Token</b> represents  a contiguous region of the file beginning with the requested offset in the <b>FileOffset</b> member of <a href="..\ntifs\ns-ntifs-_fsctl_offload_read_input.md">FSCTL_OFFLOAD_READ_INPUT</a>. The resulting length copied, <b>TransferLength</b>, may be smaller than what was originally specified in <b>CopyLength</b> member of <b>FSCTL_OFFLOAD_READ_INPUT</b>. A smaller value indicates that  <b>Token</b> was able to logically represent less data than was requested.

 If less data than requested was transferred, the read operation  may be completed by performing another <a href="https://msdn.microsoft.com/library/windows/hardware/hh451101">FSCTL_OFFLOAD_READ</a> request. The next request uses updated <b>FileOffset</b> member in the <a href="..\ntifs\ns-ntifs-_fsctl_offload_read_input.md">FSCTL_OFFLOAD_READ_INPUT</a> structure with the value in <b>TransferLength</b> and an adjusted read length of the previous length minus the value in <b>TransferLength</b>. Also, an incomplete read operation can be completed through a non-offloaded read method, using the <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a> routine, for example.



## -see-also

<a href="..\ntifs\ns-ntifs-_fsctl_offload_read_input.md">FSCTL_OFFLOAD_READ_INPUT</a>

<a href="..\ntddstor\ns-ntddstor-_storage_offload_token.md">STORAGE_OFFLOAD_TOKEN</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451101">FSCTL_OFFLOAD_READ</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSCTL_OFFLOAD_READ_OUTPUT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

