---
UID: NF:wdm.RtlInt64ToUnicodeString
title: RtlInt64ToUnicodeString function (wdm.h)
description: The RtlInt64ToUnicodeString routine converts a specified unsigned 64-bit integer value to a Unicode string that represents the value in a specified base.
old-location: kernel\rtlint64tounicodestring.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlInt64ToUnicodeString function"]
ms.keywords: RtlInt64ToUnicodeString, RtlInt64ToUnicodeString routine [Kernel-Mode Driver Architecture], k109_b6248e50-c6e8-4c61-a9f0-83fb434bd69c.xml, kernel.rtlint64tounicodestring, wdm/RtlInt64ToUnicodeString
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
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlInt64ToUnicodeString
 - wdm/RtlInt64ToUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlInt64ToUnicodeString
---

# RtlInt64ToUnicodeString function


## -description

The <b>RtlInt64ToUnicodeString</b> routine converts a specified unsigned 64-bit integer value to a Unicode string that represents the value in a specified base.

## -parameters

### -param Value 

[in]
Specifies the ULONGLONG value to convert.

### -param Base 

[in, optional]
Specifies the base to use when converting <i>Value</i> to a string. The possible values are:

<table>
<tr>
<th>Value</th>
<th>Base</th>
</tr>
<tr>
<td>
16

</td>
<td>
Hexadecimal

</td>
</tr>
<tr>
<td>
8

</td>
<td>
Octal

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Binary

</td>
</tr>
<tr>
<td>
0 or 10

</td>
<td>
Decimal

</td>
</tr>
</table>

### -param String 

[in, out]
Pointer to the <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that receives the string representation of <i>Value</i>. The buffer specified by the <i>Buffer</i>  of <i>String</i> must be large enough to hold the result.

## -returns

<b>RtlInt64ToUnicodeString</b> returns an NTSTATUS value. Possible return values include :

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
The routine successfully converted <i>Value</i> to a Unicode string.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
<i>Value</i> is too large to convert, or the <b>UNICODE_STRING</b> structure is too small to hold the result.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified code base is not valid. The only valid values are 0, 2, 8, 10, and 16.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlappendunicodestringtostring">RtlAppendUnicodeStringToString</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlunicodestringtointeger">RtlUnicodeStringToInteger</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
