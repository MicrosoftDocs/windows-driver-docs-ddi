---
UID: NF:ntstrsafe.RtlUnicodeStringCchCatStringNEx
title: RtlUnicodeStringCchCatStringNEx function
author: windows-driver-content
description: The RtlUnicodeStringCchCatStringNEx function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string.
old-location: kernel\rtlunicodestringcchcatstringnex.htm
old-project: kernel
ms.assetid: bad75e2f-35af-4e90-8638-28b0c362dad1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUnicodeStringCchCatStringNEx function [Kernel-Mode Driver Architecture], ntstrsafe/RtlUnicodeStringCchCatStringNEx, kernel.rtlunicodestringcchcatstringnex, safestrings_00095596-3520-437a-b089-f1cd7f39c6cb.xml, RtlUnicodeStringCchCatStringNEx
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ntstrsafe.lib
-	Ntstrsafe.dll
apiname:
-	RtlUnicodeStringCchCatStringNEx
product: Windows
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
---

# RtlUnicodeStringCchCatStringNEx function


## -description


The <b>RtlUnicodeStringCchCatStringNEx</b> function concatenates two strings when the destination string is contained in a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure, while limiting the size of the appended string.


## -syntax


````
NTSTATUS RtlUnicodeStringCchCatStringNEx(
  _Inout_   PUNICODE_STRING  DestinationString,
  _In_      NTSTRSAFE_PCWSTR pszSrc,
  _In_      size_t           cchToAppend,
  _Out_opt_ PUNICODE_STRING  RemainingString,
  _In_      DWORD            dwFlags
);
````


## -parameters




### -param DestinationString [in, out]

Optional. A pointer to a <b>UNICODE_STRING</b> structure. This structure includes a buffer that, on input, contains a string to which the source string will be concatenated. On output, this buffer is the destination buffer that contains the entire resultant string. The source string (excluding the terminating null) is added to the end of the destination string. The maximum number of characters in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH. <i>DestinationString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param pszSrc [in]

A caller-supplied pointer to a null-terminated string. This string will be concatenated to the end of the string that <i>DestinationString</i> describes. <i>pszSrc</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param cchToAppend [in]

The maximum number of characters to append to the string that the <i>DestinationString</i> parameter describes.


### -param RemainingString [out, optional]

Optional. If the caller supplies a non-<b>NULL</b> pointer to a <b>UNICODE_STRING</b> structure, the function sets this structure's <b>Buffer</b> member to the end of the concatenated string, sets the structure's <b>Length</b> member to zero, and sets the structure's <b>MaximumLength</b> member to the number of bytes that are remaining in the destination buffer. <i>RemainingString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param dwFlags [in]

One or more flags and, optionally, a fill byte. The flags are defined as follows:





#### STRSAFE_FILL_BEHIND

If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the last character in the string.



#### STRSAFE_IGNORE_NULLS

If this flag is set, the source or destination pointer, or both, can be <b>NULL</b>. <b>RtlUnicodeStringCchCatStringNEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")), which can be copied. <b>NULL</b> destination buffer pointers cannot receive nonempty strings.



#### STRSAFE_FILL_ON_FAILURE

If this flag is set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer. This operation overwrites any preexisting buffer contents.



#### STRSAFE_NULL_ON_FAILURE

If this flag is set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents.



#### STRSAFE_NO_TRUNCATION

If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.



#### STRSAFE_ZERO_LENGTH_ON_FAILURE

If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the destination string length is set to zero bytes.


## -returns



<b>RtlUnicodeStringCchCatStringNEx</b> returns one of the following NTSTATUS values. 

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
This <i>warning</i> status means that the concatenation operation did not complete because of insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the intended result.

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
 

<b>RtlUnicodeStringCchCatStringNEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of a <b>UNICODE_STRING</b> structure are invalid.</li>
<li>An invalid flag is specified in <i>dwFlags</i>.</li>
<li>The destination buffer is already full.</li>
<li>A buffer pointer is <b>NULL</b> and the STRSAFE_IGNORE_NULLS flag is not specified in <i>dwFlags</i>.</li>
<li>The destination buffer pointer is <b>NULL</b>, but the buffer size is not zero.</li>
<li>The destination buffer pointer is <b>NULL</b>, or its length is zero, but a nonzero length source string is present.</li>
<li>The <i>cchToAppend</i> parameter's value is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringCchCatStringNEx </b>function uses the destination buffer's size to ensure that the concatenation operation does not write past the end of the buffer. By default, the function does <u>not</u> terminate the resultant string with a null character value (that is, with zero). As an option, the caller can use the STRSAFE_FILL_BEHIND flag and a fill byte value of zero to null-terminate a resultant string that does not occupy the entire destination buffer.

<b>RtlUnicodeStringCchCatStringNEx </b>adds to the functionality of the <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcchcatstringn.md">RtlUnicodeStringCchCatStringN</a> function by returning a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that identifies the end of the destination string and the number of bytes that are left unused in that string. Flags can be passed to <b>RtlUnicodeStringCchCatStringNEx </b> for additional control.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>pszSrc</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set in <i>dwFlags</i>. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be <b>NULL</b>. If the <i>DestinationString</i> pointer is <b>NULL</b>, the <i>pszSrc</i> pointer must either be <b>NULL</b> or point to an empty string.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcchcatstringn.md">RtlUnicodeStringCchCatStringN</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcbcatstringnex.md">RtlUnicodeStringCbCatStringNEx</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringCchCatStringNEx function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

