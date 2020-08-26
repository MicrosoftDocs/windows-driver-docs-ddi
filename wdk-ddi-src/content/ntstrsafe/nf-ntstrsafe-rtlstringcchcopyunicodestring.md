---
UID: NF:ntstrsafe.RtlStringCchCopyUnicodeString
title: RtlStringCchCopyUnicodeString function (ntstrsafe.h)
description: The RtlStringCchCopyUnicodeString function copies the contents of a UNICODE_STRING structure to a specified destination.
old-location: kernel\rtlstringcchcopyunicodestring.htm
tech.root: kernel
ms.assetid: acc4051f-dcd4-443d-ad6b-02e6b0c1cad4
ms.date: 04/30/2018
keywords: ["RtlStringCchCopyUnicodeString function"]
ms.keywords: RtlStringCchCopyUnicodeString, RtlStringCchCopyUnicodeString function [Kernel-Mode Driver Architecture], kernel.rtlstringcchcopyunicodestring, ntstrsafe/RtlStringCchCopyUnicodeString, safestrings_99b6e156-5c40-41e1-a02b-400a20cbd74d.xml
f1_keywords:
 - "ntstrsafe/RtlStringCchCopyUnicodeString"
 - "RtlStringCchCopyUnicodeString"
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
- RtlStringCchCopyUnicodeString
targetos: Windows
req.typenames: 
---

# RtlStringCchCopyUnicodeString function


## -description


The <b>RtlStringCchCopyUnicodeString</b> function copies the contents of a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure to a specified destination.


## -parameters




### -param pszDest 
[out]
A pointer to a buffer that receives the copied string. The string that the <i>SourceString</i> parameter's <b>UNICODE_STRING</b> structure points to is copied to the buffer at <i>pszDest</i> and terminated with a null character. 


### -param cchDest 
[in]
The size, in characters, of the destination buffer. The buffer must be large enough for the string and the terminating null character. The maximum number of characters is NTSTRSAFE_MAX_CCH.


### -param SourceString 
[in]
A pointer to a <b>UNICODE_STRING</b> structure that contains the string to be copied. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH.


## -returns



<b>RtlStringCchCopyUnicodeString</b> returns one of the following NTSTATUS values.

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
 

<b>RtlStringCchCopyUnicodeString</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of the <b>UNICODE_STRING</b> structure are invalid.</li>
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer (which <i>pszDest</i> points to) is already full.</li>
<li>A buffer pointer is <b>NULL</b>.</li>
<li>The destination buffer's length is zero, but a nonzero length source string is present.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlStringCchCopyUnicodeString</b> function uses the destination buffer's size (which <i>cchDest</i> specifies) to ensure that the copy operation does not write past the end of the buffer.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString </i>and <i>pszDest</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchcopyunicodestringex">RtlStringCchCopyUnicodeStringEx</a> function.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcopyunicodestring">RtlStringCbCopyUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchcopyunicodestringex">RtlStringCchCopyUnicodeStringEx</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

