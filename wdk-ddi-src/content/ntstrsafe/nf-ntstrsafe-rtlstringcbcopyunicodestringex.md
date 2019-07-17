---
UID: NF:ntstrsafe.RtlStringCbCopyUnicodeStringEx
title: RtlStringCbCopyUnicodeStringEx function (ntstrsafe.h)
description: The RtlStringCbCopyUnicodeStringEx function copies the contents of a UNICODE_STRING structure to a specified destination.
old-location: kernel\rtlstringcbcopyunicodestringex.htm
tech.root: kernel
ms.assetid: 146f0e43-a9de-4d4d-8b8f-219c22cfa871
ms.date: 04/30/2018
ms.keywords: RtlStringCbCopyUnicodeStringEx, RtlStringCbCopyUnicodeStringEx function [Kernel-Mode Driver Architecture], kernel.rtlstringcbcopyunicodestringex, ntstrsafe/RtlStringCbCopyUnicodeStringEx, safestrings_38290608-dda4-4827-bcd2-3a0bef015690.xml
ms.topic: function
f1_keywords:
 - "ntstrsafe/RtlStringCbCopyUnicodeStringEx"
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
- RtlStringCbCopyUnicodeStringEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlStringCbCopyUnicodeStringEx function


## -description


The <b>RtlStringCbCopyUnicodeStringEx</b> function copies the contents of a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure to a specified destination. 


## -parameters




### -param pszDest [out]

Optional. A pointer to a buffer that receives the copied string. The string that the <i>SourceString</i> parameter's <b>UNICODE_STRING</b> structure points to is copied to the buffer at <i>pszDest</i> and terminated with a null character. This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>. 


### -param cbDest [in]

The size, in bytes, of the destination buffer. The buffer must be large enough for the string and the terminating null character. The maximum number of bytes in the buffer is NTSTRSAFE_MAX_CCH * sizeof(WCHAR).


### -param SourceString [in]

Optional. A pointer to a <b>UNICODE_STRING</b> structure that contains the string to be copied. The maximum number of bytes in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR). This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param ppszDestEnd [out]

Optional. If the caller supplies a non-<b>NULL</b> address pointer, then after the copy operation completes, the function loads that address with a pointer to the destination buffer's resulting <b>NULL</b> string terminator. 


### -param pcbRemaining [out, optional]

Optional. If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused bytes that are in the buffer that <i>pszDest</i> points to, including bytes that are used for the terminating null character.


### -param dwFlags [in]

One or more flags and, optionally, a fill byte. The flags are defined as follows: 





#### STRSAFE_FILL_BEHIND_NULL

If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the terminating null character. 



#### STRSAFE_IGNORE_NULLS

If this flag is set, either the source or destination pointer, or both, can be <b>NULL</b>. <b>RtlStringCbCopyUnicodeStringEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")), which can be copied. <b>NULL</b> destination buffer pointers cannot receive nonempty strings. 



#### STRSAFE_FILL_ON_FAILURE

If this flag is set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer, and the buffer is null-terminated. This operation overwrites any preexisting buffer contents. 



#### STRSAFE_NULL_ON_FAILURE

If this flag is set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents. 



#### STRSAFE_NO_TRUNCATION

If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.


## -returns



<b>RtlStringCbCopyUnicodeStringEx</b> returns one of the following NTSTATUS values. 

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
This <i>warning</i> status means that the copy operation did not complete because of insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the copied string.

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
 

<b>RtlStringCbCopyUnicodeStringEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of the <b>UNICODE_STRING</b> structure are invalid.</li>
<li>An invalid flag is specified in dwFlags.</li>
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer (which <i>pszDest</i> points to) is already full.</li>
<li>A buffer pointer is <b>NULL</b> and the STRSAFE_IGNORE_NULLS flag is not specified.</li>
<li>The destination buffer pointer is <b>NULL</b>, but the buffer size is not zero.</li>
<li>The destination buffer pointer is <b>NULL</b> or its length is zero, but a nonzero length source string is present.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlStringCbCopyUnicodeStringEx</b> function uses the destination buffer's size (which the <i>cbDest</i> parameter specifies) to ensure that the copy operation does not write past the end of the buffer.

<b>RtlStringCbCopyUnicodeStringEx</b> adds to the functionality of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcbcopyunicodestring">RtlStringCbCopyUnicodeString</a> function by returning a pointer to the end of the destination string and the number of bytes that are left unused in that string. You can pass flags to the function for additional control.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString </i>and <i>pszDest</i> pointers cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set in <i>dwFlags</i>. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be <b>NULL</b>. If the <i>pszDest</i> pointer is <b>NULL</b>, the <i>SourceString </i>pointer must be <b>NULL</b> or the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure must describe an empty string.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcbcopyunicodestring">RtlStringCbCopyUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcchcopyunicodestringex">RtlStringCchCopyUnicodeStringEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

