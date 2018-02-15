---
UID: NF:ntstrsafe.RtlUnicodeStringPrintf
title: RtlUnicodeStringPrintf function
author: windows-driver-content
description: The RtlUnicodeStringPrintf function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringprintf.htm
old-project: kernel
ms.assetid: a646a63a-9a92-49ae-adfc-97d6b726caac
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: safestrings_9ad0c4dc-1e0a-41b3-a5d8-e5d80e876226.xml, ntstrsafe/RtlUnicodeStringPrintf, kernel.rtlunicodestringprintf, RtlUnicodeStringPrintf, RtlUnicodeStringPrintf function [Kernel-Mode Driver Architecture]
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
-	RtlUnicodeStringPrintf
product: Windows
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
---

# RtlUnicodeStringPrintf function


## -description


The <b>RtlUnicodeStringPrintf</b> function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure.


## -syntax


````
NTSTATUS RtlUnicodeStringPrintf(
  _Out_ PUNICODE_STRING  DestinationString,
  _In_  NTSTRSAFE_PCWSTR pszFormat,
                         ...
);
````


## -parameters




### -param DestinationString [out]

A pointer to a <b>UNICODE_STRING</b> structure that receives a formatted string. <b>RtlUnicodeStringPrintf</b> creates this string from the formatting string that <i>pszFormat</i> specifies and the function's argument list. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH.


### -param pszFormat [in]

A pointer to a null-terminated text string that contains <b>printf</b>-styled formatting directives.


### -param param

TBD




####### - ...

Optional. A list of arguments that the function interprets, based on formatting directives that the <i>pszFormat</i> string contains.


## -returns



<b>RtlUnicodeStringPrintf</b> returns one of the following NTSTATUS values. 

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
This <i>warning</i> status means that the operation did not complete because of insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

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
 

<b>RtlUnicodeStringPrintf</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of the <b>UNICODE_STRING</b> structure that the <i>DestinationString</i> parameter points to are invalid.</li>
<li>The destination buffer is already full.</li>
<li>A <b>NULL</b> pointer is present.</li>
<li>The destination buffer's length is zero, but a nonzero length source string is present.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringPrintf</b> function uses the destination buffer's size to ensure that the string formatting operation does not write past the end of the buffer. The function does not terminate the resultant string with a null character.

If the format string and destination string overlap, the behavior of the function is undefined.

The <i>pszFormat</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringprintfex.md">RtlUnicodeStringPrintfEx</a> function.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringprintfex.md">RtlUnicodeStringPrintfEx</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringvprintf.md">RtlUnicodeStringVPrintf</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringvprintfex.md">RtlUnicodeStringVPrintfEx</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringPrintf function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

