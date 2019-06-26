---
UID: NF:ntstrsafe.RtlUnicodeStringCchCopyStringNEx
title: RtlUnicodeStringCchCopyStringNEx function (ntstrsafe.h)
description: The RtlUnicodeStringCchCopyStringNEx function copies a string into a UNICODE_STRING structure while limiting the size of the copied string.
old-location: kernel\rtlunicodestringcchcopystringnex.htm
tech.root: kernel
ms.assetid: abbb1afd-b5a4-4be2-9cca-c5c5d7e0aa51
ms.date: 04/30/2018
ms.keywords: RtlUnicodeStringCchCopyStringNEx, RtlUnicodeStringCchCopyStringNEx function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringcchcopystringnex, ntstrsafe/RtlUnicodeStringCchCopyStringNEx, safestrings_3c97192f-198f-4ab5-8c56-7a73d501be0b.xml
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows XP with Service Pack 1 (SP1).
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
- RtlUnicodeStringCchCopyStringNEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringCchCopyStringNEx function


## -description


The <b>RtlUnicodeStringCchCopyStringNEx</b> function copies a string into a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure while limiting the size of the copied string.


## -parameters




### -param DestinationString [out]

Optional. A pointer to a <b>UNICODE_STRING</b> structure that receives the copied string. The string that the <i>pszSrc </i>parameter points to (excluding the terminating null) is copied into the buffer that the <i>DestinationString</i> parameter's <b>UNICODE_STRING</b> structure points to. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH. <i>DestinationString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param pszSrc [in]

Optional. A pointer to the string to be copied. This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param cchToCopy [in]

The number of characters to be copied from the source to the destination. 


### -param RemainingString [out, optional]

Optional. If the caller supplies a non-<b>NULL</b> pointer to a <b>UNICODE_STRING</b> structure, the function sets this structure's <b>Buffer</b> member to the end of the concatenated string, sets the structure's <b>Length</b> member to zero, and sets the structure's <b>MaximumLength</b> member to the number of bytes that are remaining in the destination buffer. <i>RemainingString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param dwFlags [in]

One or more flags and, optionally, a fill byte. The flags are defined as follows:





#### STRSAFE_FILL_BEHIND

If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the last character in the string.



#### STRSAFE_IGNORE_NULLS

If this flag is set, the source or destination pointer, or both, can be <b>NULL</b>. <b>RtlUnicodeStringCchCopyStringNEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")), which can be copied. <b>NULL</b> destination buffer pointers cannot receive nonempty strings.



#### STRSAFE_FILL_ON_FAILURE

If this flag is set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer. This operation overwrites any preexisting buffer contents.



#### STRSAFE_NULL_ON_FAILURE

If this flag is set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents.



#### STRSAFE_NO_TRUNCATION

If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.



#### STRSAFE_ZERO_LENGTH_ON_FAILURE

If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the destination string length is set to zero bytes.


## -returns



<b>RtlUnicodeStringCchCopyStringNEx</b> returns one of the following NTSTATUS values. 

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
This <i>success</i> status means source data was present, and the strings were concatenated without truncation.

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
 

<b>RtlUnicodeStringCchCopyStringNEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of a <b>UNICODE_STRING</b> structure are invalid.</li>
<li>An invalid flag is specified in <i>dwFlags</i>.</li>
<li>The destination buffer is already full.</li>
<li>A buffer pointer is <b>NULL</b> and the STRSAFE_IGNORE_NULLS flag is not specified in <i>dwFlags</i>.</li>
<li>The destination buffer pointer is <b>NULL</b>, but the buffer size is not zero.</li>
<li>The destination buffer pointer is <b>NULL</b>, or its length is zero, but a nonzero length source string is present.</li>
<li>The <i>cchToCopy</i> parameter's value is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringCchCopyStringNEx</b> function uses the destination buffer's size to ensure that the copy operation does not write past the end of the buffer. By default, the function does <u>not</u> terminate the resultant string with a null character value (that is, with zero). As an option, the caller can use the STRSAFE_FILL_BEHIND flag and a fill byte value of zero to null-terminate a resultant string that does not occupy the entire destination buffer.

<b>RtlUnicodeStringCchCopyStringNEx</b> adds to the functionality of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringcchcopystringn">RtlUnicodeStringCchCopyStringN</a> function by returning a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that identifies the end of the destination string and the number of bytes that are left unused in that string. You can pass flags to <b>RtlUnicodeStringCchCopyStringNEx</b> for additional control.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>pszSrc</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set in <i>dwFlags</i>. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be <b>NULL</b>. If the <i>DestinationString</i> pointer is <b>NULL</b>, the <i>pszSrc</i> pointer must be <b>NULL</b> or point to an empty string.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringcbcopystringnex">RtlUnicodeStringCbCopyStringNEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringcchcopystringn">RtlUnicodeStringCchCopyStringN</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

