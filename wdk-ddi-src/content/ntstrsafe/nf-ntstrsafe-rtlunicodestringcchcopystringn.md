---
UID: NF:ntstrsafe.RtlUnicodeStringCchCopyStringN
title: RtlUnicodeStringCchCopyStringN function (ntstrsafe.h)
description: The RtlUnicodeStringCchCopyStringN function copies a string into a UNICODE_STRING structure while limiting the size of the copied string.
old-location: kernel\rtlunicodestringcchcopystringn.htm
tech.root: kernel
ms.assetid: 28ff3697-e2b3-4818-99d3-0b1f7a098282
ms.date: 04/30/2018
keywords: ["RtlUnicodeStringCchCopyStringN function"]
ms.keywords: RtlUnicodeStringCchCopyStringN, RtlUnicodeStringCchCopyStringN function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringcchcopystringn, ntstrsafe/RtlUnicodeStringCchCopyStringN, safestrings_d48eb8f3-535f-4829-aed4-6bde1b4733e3.xml
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
 - RtlUnicodeStringCchCopyStringN
 - ntstrsafe/RtlUnicodeStringCchCopyStringN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ntstrsafe.lib
 - Ntstrsafe.dll
api_name:
 - RtlUnicodeStringCchCopyStringN
---

# RtlUnicodeStringCchCopyStringN function


## -description

The <b>RtlUnicodeStringCchCopyStringN</b> function copies a string into a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure while limiting the size of the copied string.

## -parameters

### -param DestinationString 

[out]
A pointer to a <b>UNICODE_STRING</b> structure that receives the copied string. The string that the <i>pszSrc </i>parameter points to (excluding the terminating <b>NULL</b>) is copied into the buffer that the <i>DestinationString</i> parameter's <b>UNICODE_STRING</b> structure points to. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH.

### -param pszSrc 

[in]
A pointer to the string to be copied.

### -param cchToCopy 

[in]
The number of characters to be copied from the source to the destination.

## -returns

<b>RtlUnicodeStringCchCopyStringN</b> returns one of the following NTSTATUS.

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
This <i>warning</i> status means that the copy operation did not complete because of insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

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
 

<b>RtlUnicodeStringCchCopyStringN</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of the <b>UNICODE_STRING</b> structure are invalid.</li>
<li>The destination buffer is already full.</li>
<li>A buffer pointer is <b>NULL</b>.</li>
<li>The destination buffer's length is zero, but a nonzero length source string is present.</li>
<li>The <i>cchToCopy</i> parameter's value is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.

## -remarks

The <b>RtlUnicodeStringCchCopyN</b> function uses the destination buffer's size to ensure that the copy operation does not write past the end of the buffer. The function does not terminate the resultant string with a null character.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>pszSrc </i>and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcchcopynex">RtlUnicodeStringCchCopyNEx</a> function.

For more information about the safe string functions, see <a href="/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcchcopyn">RtlUnicodeStringCchCopyN</a>



<a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcchcopynex">RtlUnicodeStringCchCopyNEx</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>