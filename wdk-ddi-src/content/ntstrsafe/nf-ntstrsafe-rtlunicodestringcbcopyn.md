---
UID: NF:ntstrsafe.RtlUnicodeStringCbCopyN
title: RtlUnicodeStringCbCopyN function (ntstrsafe.h)
description: The RtlUnicodeStringCbCopyN function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string.
old-location: kernel\rtlunicodestringcbcopyn.htm
tech.root: kernel
ms.assetid: 296a936b-83e3-457d-bfa8-e361da7706bf
ms.date: 04/30/2018
keywords: ["RtlUnicodeStringCbCopyN function"]
ms.keywords: RtlUnicodeStringCbCopyN, RtlUnicodeStringCbCopyN function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringcbcopyn, ntstrsafe/RtlUnicodeStringCbCopyN, safestrings_7fb0b8bb-9687-4fdb-899d-5fdaa6cf1c0c.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlUnicodeStringCbCopyN
 - ntstrsafe/RtlUnicodeStringCbCopyN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ntstrsafe.lib
 - Ntstrsafe.dll
api_name:
 - RtlUnicodeStringCbCopyN
---

# RtlUnicodeStringCbCopyN function


## -description

The <b>RtlUnicodeStringCbCopyN</b> function copies a string from one <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure to another while limiting the size of the copied string.

## -parameters

### -param DestinationString 

[out]
A pointer to a <b>UNICODE_STRING</b> structure that receives the copied string. The string that the <i>SourceString</i> parameter's <b>UNICODE_STRING</b> structure points to is copied to the buffer that the <i>DestinationString</i> parameter's <b>UNICODE_STRING</b> structure points to. The maximum number of bytes in the <i>DestinationString </i>structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).

### -param SourceString 

[in]
A pointer to a <b>UNICODE_STRING</b> structure that contains the string to be copied. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).

### -param cbToCopy 

[in]
The number of bytes to be copied from the source to the destination.

## -returns

<b>RtlUnicodeStringCbCopyN</b> returns one of the following NTSTATUS values. 

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
This <i>success</i> status means source data was present, the string was copied without truncation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the copy operation did not complete due to insufficient buffer space. The destination buffer contains a truncated version of the intended result.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

</td>
</tr>
</table>
 

<b>RtlUnicodeStringCbCopyN</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of the <b>UNICODE_STRING</b> structure are invalid.</li>
<li>The destination buffer is already full.</li>
<li>A buffer pointer is <b>NULL</b>.</li>
<li>The destination buffer's length is zero, but a nonzero length source string is present.</li>
<li>The <i>cbToCopy</i> parameter's value is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.

## -remarks

The <b>RtlUnicodeStringCbCopyN</b> function uses the destination buffer's size to ensure that the copy operation does not write past the end of the buffer. The function does <u>not</u> terminate the resultant string with a null character value (that is, with zero).

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcbcopynex">RtlUnicodeStringCbCopyNEx</a> function.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcbcopynex">RtlUnicodeStringCbCopyNEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcchcopyn">RtlUnicodeStringCchCopyN</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>

