---
UID: NF:wdm.RtlAppendUnicodeStringToString
title: RtlAppendUnicodeStringToString function (wdm.h)
description: The RtlAppendUnicodeStringToString routine concatenates two Unicode strings.
old-location: kernel\rtlappendunicodestringtostring.htm
tech.root: kernel
ms.assetid: fb076688-ae8e-430b-ac06-dfef7284591d
ms.date: 04/30/2018
ms.keywords: RtlAppendUnicodeStringToString, RtlAppendUnicodeStringToString routine [Kernel-Mode Driver Architecture], k109_4c17620f-086f-4a0d-aa7a-6bc46d0a0f21.xml, kernel.rtlappendunicodestringtostring, wdm/RtlAppendUnicodeStringToString
f1_keywords:
 - "wdm/RtlAppendUnicodeStringToString"
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
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlAppendUnicodeStringToString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlAppendUnicodeStringToString function


## -description


The <b>RtlAppendUnicodeStringToString</b> routine concatenates two Unicode strings. 


## -parameters




### -param Destination [in, out]

Pointer to a buffered Unicode string.


### -param Source [in]

Pointer to the buffered string to be concatenated. 


## -returns



<b>RtlAppendUnicodeStringToString</b> can return one of the following:

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
The source string was successfully appended to the destination counted string. The destination string length is updated to include the appended bytes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The destination string length is too small to allow the source string to be concatenated. Accordingly, the destination string length is not updated.

</td>
</tr>
</table>
 




## -remarks



<b>RtlAppendUnicodeStringToString</b> copies bytes from the source to the specified destination string, after the current contents of the destination string and the destination length is incremented by the number of bytes copied.

The <i>Destination</i> and <i>Source</i> buffers must be resident if the caller is running at IRQL >= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlappendunicodetostring">RtlAppendUnicodeToString</a>
 

 

