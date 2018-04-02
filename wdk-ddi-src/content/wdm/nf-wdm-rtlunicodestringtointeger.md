---
UID: NF:wdm.RtlUnicodeStringToInteger
title: RtlUnicodeStringToInteger function
author: windows-driver-content
description: The RtlUnicodeStringToInteger routine converts a Unicode string representation of a number to the equivalent integer value.
old-location: kernel\rtlunicodestringtointeger.htm
old-project: kernel
ms.assetid: d9357864-d49b-44fe-b884-64c6da609789
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUnicodeStringToInteger, RtlUnicodeStringToInteger routine [Kernel-Mode Driver Architecture], k109_862feacf-64af-4aae-87b5-264ef277ea22.xml, kernel.rtlunicodestringtointeger, wdm/RtlUnicodeStringToInteger
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlUnicodeStringToInteger
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlUnicodeStringToInteger function


## -description


The <b>RtlUnicodeStringToInteger</b> routine converts a Unicode string representation of a number to the equivalent integer value.


## -parameters




### -param String [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the number representation to convert to the equivalent integer value.


### -param Base [in, optional]

A numeric value that indicates the base (or radix) of the number that the Unicode string represents. This parameter value is optional and can be set to zero.

If <i>Base</i> is zero, <b>RtlUnicodeStringToInteger</b> checks the prefix of the Unicode string to determine the base of the number:

<ul>
<li>
If the prefix is "0x", <b>RtlUnicodeStringToInteger</b> interprets the number in the string as a hexadecimal integer.

</li>
<li>
If the prefix is "0o", <b>RtlUnicodeStringToInteger</b> interprets the number in the string as an octal integer.

</li>
<li>
If the prefix is "0b", <b>RtlUnicodeStringToInteger</b> interprets the number in the string as a binary integer.

</li>
</ul>
If the Unicode string does not contain any of these prefixes, <b>RtlUnicodeStringToInteger</b> treats the string as a base-10 integer.


### -param Value [out]

A pointer to a ULONG variable to which <b>RtlUnicodeStringToInteger</b> writes the integer value that results from conversion of the Unicode string.


## -returns



If the conversion is successful, the <b>RtlUnicodeStringToInteger</b> routine returns STATUS_SUCCESS and sets *<i>Value</i> to the integer value represented by the number in the Unicode string. If the string is not empty, but does not start with a valid number representation, the routine returns STATUS_SUCCESS and sets *<i>Value</i> to zero. If the string is empty, the routine fails and returns STATUS_INVALID_PARAMETER.




## -remarks



This routine skips any white space at the start of the input string to find the start of the number.

If the first non-white space character in the string is a hyphen (-), the integer value written to *<i>Value</i> is negative; otherwise, if the first character is a "+" or there is no sign character, the integer value written to *<i>Value</i> is positive.

 If the string does not contain a valid number, or if the first digit in the string is preceded by a non-white space character other than '+' or '-', the routine sets the output value to zero and returns STATUS_SUCCESS.

A substring that contains one or more valid digits is terminated by any character that is not a valid digit. For example, if <i>Base</i> = 2, valid digits are '0' and '1'. If <i>Base</i> = 8, valid digits are '0' to '7'. If <i>Base</i> = 10, valid digits are '0' to '9'. If <i>Base</i> = 16, valid digits are '0' to '9', 'a' to 'f', and 'A' to 'F'.

The following table contains examples of output values that result from various combinations of input strings and <i>Base</i> parameter values.

<table>
<tr>
<th>Input string</th>
<th>Base</th>
<th>Output value</th>
</tr>
<tr>
<td>"123"</td>
<td>10</td>
<td>123</td>
</tr>
<tr>
<td>"  -345"</td>
<td>10</td>
<td>-345</td>
</tr>
<tr>
<td>"xyz"</td>
<td>10</td>
<td>0</td>
</tr>
<tr>
<td>"   +678abc"</td>
<td>10</td>
<td>678</td>
</tr>
<tr>
<td>"   +678abc"</td>
<td>16</td>
<td>6785724</td>
</tr>
<tr>
<td>"007"</td>
<td>10</td>
<td>7</td>
</tr>
<tr>
<td>"789"</td>
<td>8</td>
<td>7</td>
</tr>
<tr>
<td>"FGH"</td>
<td>16</td>
<td>15</td>
</tr>
<tr>
<td>"      "</td>
<td>10</td>
<td>0</td>
</tr>
</table>
 

A related routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff561941">RtlIntegerToUnicodeString</a>, converts an integer value to the equivalent Unicode string representation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561941">RtlIntegerToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

