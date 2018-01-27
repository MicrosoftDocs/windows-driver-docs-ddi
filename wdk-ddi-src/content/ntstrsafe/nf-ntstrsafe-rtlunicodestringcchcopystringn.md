---
UID: NF:ntstrsafe.RtlUnicodeStringCchCopyStringN
title: RtlUnicodeStringCchCopyStringN function
author: windows-driver-content
description: The RtlUnicodeStringCchCopyStringN function copies a string into a UNICODE_STRING structure while limiting the size of the copied string.
old-location: kernel\rtlunicodestringcchcopystringn.htm
old-project: kernel
ms.assetid: 28ff3697-e2b3-4818-99d3-0b1f7a098282
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: safestrings_d48eb8f3-535f-4829-aed4-6bde1b4733e3.xml, kernel.rtlunicodestringcchcopystringn, RtlUnicodeStringCchCopyStringN function [Kernel-Mode Driver Architecture], RtlUnicodeStringCchCopyStringN, ntstrsafe/RtlUnicodeStringCchCopyStringN
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
-	RtlUnicodeStringCchCopyStringN
product: Windows
targetos: Windows
req.typenames: *PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE
---

# RtlUnicodeStringCchCopyStringN function


## -description


The <b>RtlUnicodeStringCchCopyStringN</b> function copies a string into a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure while limiting the size of the copied string.


## -syntax


````
NTSTATUS RtlUnicodeStringCchCopyStringN(
  _Out_ PUNICODE_STRING  DestinationString,
  _In_  NTSTRSAFE_PCWSTR pszSrc,
  _In_  size_t           cchToCopy
);
````


## -parameters




### -param DestinationString [out]

A pointer to a <b>UNICODE_STRING</b> structure that receives the copied string. The string that the <i>pszSrc </i>parameter points to (excluding the terminating <b>NULL</b>) is copied into the buffer that the <i>DestinationString</i> parameter's <b>UNICODE_STRING</b> structure points to. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH.


### -param pszSrc [in]

A pointer to the string to be copied. 


### -param cchToCopy [in]

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
</ul>For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.



## -remarks


The <b>RtlUnicodeStringCchCopyN</b> function uses the destination buffer's size to ensure that the copy operation does not write past the end of the buffer. The function does not terminate the resultant string with a null character.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>pszSrc </i>and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcchcopynex.md">RtlUnicodeStringCchCopyNEx</a> function.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcchcopyn.md">RtlUnicodeStringCchCopyN</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcchcopynex.md">RtlUnicodeStringCchCopyNEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringCchCopyStringN function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

