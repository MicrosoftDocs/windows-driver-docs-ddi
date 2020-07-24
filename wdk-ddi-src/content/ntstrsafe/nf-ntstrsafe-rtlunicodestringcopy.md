---
UID: NF:ntstrsafe.RtlUnicodeStringCopy
title: RtlUnicodeStringCopy function (ntstrsafe.h)
description: The RtlUnicodeStringCopy function copies a string from one UNICODE_STRING structure to another.
old-location: kernel\rtlunicodestringcopy.htm
tech.root: kernel
ms.assetid: 7cc94f22-37af-420c-824e-ca9c8a4b42be
ms.date: 04/30/2018
keywords: ["RtlUnicodeStringCopy function"]
ms.keywords: RtlUnicodeStringCopy, RtlUnicodeStringCopy function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringcopy, ntstrsafe/RtlUnicodeStringCopy, safestrings_d5885cd9-d024-4757-8458-14a787b11a9f.xml
f1_keywords:
 - "ntstrsafe/RtlUnicodeStringCopy"
 - "RtlUnicodeStringCopy"
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
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
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ntstrsafe.lib
- Ntstrsafe.dll
api_name:
- RtlUnicodeStringCopy
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringCopy function


## -description


The <b>RtlUnicodeStringCopy</b> function copies a string from one <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure to another.


## -parameters




### -param DestinationString [out]

A pointer to a <b>UNICODE_STRING</b> structure. The source string is copied to the destination string. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).


### -param SourceString [in]

A pointer to a <b>UNICODE_STRING</b> structure. This structure includes a buffer that contains the source string. This string will be copied to the destination string. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).


## -returns



<b>RtlUnicodeStringCopy</b> returns one of the following NTSTATUS values. 

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
This <i>success</i> status means that source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means that the copy operation did not complete because of insufficient buffer space. The destination buffer contains a truncated version of the source string.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.

</td>
</tr>
</table>
 

<b>RtlUnicodeStringCopy</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of a <b>UNICODE_STRING</b> structure are invalid.</li>
<li>The destination buffer is already full.</li>
<li>A buffer pointer is <b>NULL</b>.</li>
<li>The destination buffer's length is zero, but a nonzero length source string is present.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringCopy</b> function uses the destination buffer's size to ensure that the copy operation does not write past the end of the buffer. If the string must be truncated at the end of the destination buffer, the function does not terminate the resultant string with a null character.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcopyex">RtlUnicodeStringCopyEx</a> function.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcopyex">RtlUnicodeStringCopyEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

