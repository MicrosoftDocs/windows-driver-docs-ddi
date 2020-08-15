---
UID: NF:wdm.RtlAppendUnicodeToString
title: RtlAppendUnicodeToString function (wdm.h)
description: The RtlAppendUnicodeToString routine concatenates the supplied Unicode string to a buffered Unicode string.
old-location: kernel\rtlappendunicodetostring.htm
tech.root: kernel
ms.assetid: 688f033b-1f0e-4f0a-9ccd-457ba726d728
ms.date: 04/30/2018
keywords: ["RtlAppendUnicodeToString function"]
ms.keywords: RtlAppendUnicodeToString, RtlAppendUnicodeToString routine [Kernel-Mode Driver Architecture], k109_7bbe9676-db08-4bf2-b2d5-37b257621336.xml, kernel.rtlappendunicodetostring, wdm/RtlAppendUnicodeToString
f1_keywords:
 - "wdm/RtlAppendUnicodeToString"
 - "RtlAppendUnicodeToString"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlAppendUnicodeToString
targetos: Windows
req.typenames: 
---

# RtlAppendUnicodeToString function


## -description


The <b>RtlAppendUnicodeToString</b> routine concatenates the supplied Unicode string to a buffered Unicode string. 


## -parameters




### -param Destination 
[in, out]
A pointer to the buffered string. 


### -param Source 
[in, optional]
A pointer to the null-terminated string to append to the <i>Destination</i> string.


## -returns



<b>RtlAppendUnicodeToString</b> can return one of the following:

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
The source string was successfully appended to the destination string, and the destination string length was updated to include the appended bytes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The destination string buffer is too small to allow the source string to be appended, so the destination string length is not updated and the contents of the destination string buffer are not changed.

</td>
</tr>
</table>
 




## -remarks



<b>RtlAppendUnicodeToString</b> appends the source string to the end of the destination string.

If the destination buffer is not large enough to contain the string that would result from concatenating the source and destination strings (not including the null character that terminates the source string), the routine returns STATUS_BUFFER_TOO_SMALL and leaves the destination string unchanged.

The <i>Destination</i> buffer must be resident if the caller is running at IRQL >= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlappendunicodestringtostring">RtlAppendUnicodeStringToString</a>
 

 

