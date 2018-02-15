---
UID: NF:ntstrsafe.RtlUnicodeStringCbCopyN
title: RtlUnicodeStringCbCopyN function
author: windows-driver-content
description: The RtlUnicodeStringCbCopyN function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string.
old-location: kernel\rtlunicodestringcbcopyn.htm
old-project: kernel
ms.assetid: 296a936b-83e3-457d-bfa8-e361da7706bf
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntstrsafe/RtlUnicodeStringCbCopyN, RtlUnicodeStringCbCopyN, safestrings_7fb0b8bb-9687-4fdb-899d-5fdaa6cf1c0c.xml, kernel.rtlunicodestringcbcopyn, RtlUnicodeStringCbCopyN function [Kernel-Mode Driver Architecture]
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
-	RtlUnicodeStringCbCopyN
product: Windows
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
---

# RtlUnicodeStringCbCopyN function


## -description


The <b>RtlUnicodeStringCbCopyN</b> function copies a string from one <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure to another while limiting the size of the copied string.


## -syntax


````
NTSTATUS RtlUnicodeStringCbCopyN(
  _Out_ PUNICODE_STRING  DestinationString,
  _In_  PCUNICODE_STRING SourceString,
  _In_  size_t           cbToCopy
);
````


## -parameters




### -param DestinationString [out]

A pointer to a <b>UNICODE_STRING</b> structure that receives the copied string. The string that the <i>SourceString</i> parameter's <b>UNICODE_STRING</b> structure points to is copied to the buffer that the <i>DestinationString</i> parameter's <b>UNICODE_STRING</b> structure points to. The maximum number of bytes in the <i>DestinationString </i>structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).


### -param SourceString [in]

A pointer to a <b>UNICODE_STRING</b> structure that contains the string to be copied. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).


### -param cbToCopy [in]

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
This <i>success</i> status means source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the copy operation did not complete due to insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

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
For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringCbCopyN</b> function uses the destination buffer's size to ensure that the copy operation does not write past the end of the buffer. The function does <u>not</u> terminate the resultant string with a null character value (that is, with zero).

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcbcopynex.md">RtlUnicodeStringCbCopyNEx</a> function.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcbcopynex.md">RtlUnicodeStringCbCopyNEx</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcchcopyn.md">RtlUnicodeStringCchCopyN</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringCbCopyN function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

