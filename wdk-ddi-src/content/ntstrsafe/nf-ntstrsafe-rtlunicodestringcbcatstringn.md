---
UID: NF:ntstrsafe.RtlUnicodeStringCbCatStringN
title: RtlUnicodeStringCbCatStringN function
author: windows-driver-content
description: The RtlUnicodeStringCbCatStringN function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string.
old-location: kernel\rtlunicodestringcbcatstringn.htm
old-project: kernel
ms.assetid: bc2139d2-9d59-4d19-a4b5-ce0a993a9846
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlunicodestringcbcatstringn, RtlUnicodeStringCbCatStringN, RtlUnicodeStringCbCatStringN function [Kernel-Mode Driver Architecture], safestrings_54ef3816-fbca-461c-b250-4c0fca04c2ed.xml, ntstrsafe/RtlUnicodeStringCbCatStringN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ntstrsafe.lib
-	Ntstrsafe.dll
apiname:
-	RtlUnicodeStringCbCatStringN
product: Windows
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
---

# RtlUnicodeStringCbCatStringN function


## -description


The <b>RtlUnicodeStringCbCatStringN </b>function concatenates two strings when the destination string is contained in a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure, while limiting the size of the appended string.


## -syntax


````
NTSTATUS RtlUnicodeStringCbCatStringN(
  _Inout_ PUNICODE_STRING  DestinationString,
  _In_    NTSTRSAFE_PCWSTR pszSrc,
  _In_    size_t           cbToAppend
);
````


## -parameters




### -param DestinationString [in, out]

A pointer to a <b>UNICODE_STRING</b> structure. This structure includes a buffer that, on input, contains a destination string to which the source string will be concatenated. On output, this buffer is the destination buffer that contains the entire resultant string. The source string (excluding the terminating null) is added to the end of the destination string. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).


### -param pszSrc [in]

A caller-supplied pointer to a null-terminated string. This string will be concatenated to the end of the destination string that is contained in the <b>UNICODE_STRING</b> structure that <i>DestinationString</i> points to.


### -param cbToAppend [in]

The maximum number of bytes to append to the string that the <i>DestinationString</i> parameter describes.


## -returns



<b>RtlUnicodeStringCbCatStringN</b> returns one of the following NTSTATUS values. 

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
This <i>success</i> status means that source data was present, the strings were concatenated without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means that the concatenation operation did not complete because of insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

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
 

<b>RtlUnicodeStringCbCatStringN</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of the <b>UNICODE_STRING</b> structure are invalid.</li>
<li>The destination buffer is already full.</li>
<li>A buffer pointer is <b>NULL</b>.</li>
<li>The destination buffer's length is zero, but a nonzero length source string is present.</li>
<li>The <i>cbToAppend</i> parameter's value is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringCbCatStringN </b>function uses the destination buffer's size to ensure that the concatenation operation does not write past the end of the buffer. The function does <u>not</u> terminate the resultant string with a null character value (that is, with zero).

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>pszSrc</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcbcatstringnex.md">RtlUnicodeStringCbCatStringNEx</a> function.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcchcatstringn.md">RtlUnicodeStringCchCatStringN</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcbcatstringnex.md">RtlUnicodeStringCbCatStringNEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringCbCatStringN function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

