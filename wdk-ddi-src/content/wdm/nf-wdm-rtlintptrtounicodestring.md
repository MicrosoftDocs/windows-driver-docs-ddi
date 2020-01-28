---
UID: NF:wdm.RtlIntPtrToUnicodeString
title: RtlIntPtrToUnicodeString macro (wdm.h)
description: The RtlIntPtrToUnicodeString routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base.
old-location: kernel\rtlintptrtounicodestring.htm
tech.root: kernel
ms.assetid: 9bcd278f-b6eb-4e88-8255-f2724bfca285
ms.date: 04/30/2018
ms.keywords: RtlIntPtrToUnicodeString, RtlIntPtrToUnicodeString routine [Kernel-Mode Driver Architecture], k109_8ec9aafc-288e-4814-a22b-8b8e973689be.xml, kernel.rtlintptrtounicodestring, wdm/RtlIntPtrToUnicodeString
f1_keywords:
 - "wdm/RtlIntPtrToUnicodeString"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlIntPtrToUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntPtrToUnicodeString macro


## -description


The <b>RtlIntPtrToUnicodeString</b> routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base.


## -parameters




### -param Value [in]

Specifies the ULONG_PTR value to convert. 


### -param Base [in, optional]

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
 


### -param String [in, out]

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that receives the string representation of <i>Value</i>. The buffer specified by the <i>Buffer</i> of <i>String</i> must be large enough to hold the result. 

## -remarks

**RtlIntPtrToUnicodeString** returns an NTSTATUS value. Possible return values include :

|Return code| Description |
|---|---|
|STATUS_SUCCESS  |The routine successfully converted Value to a Unicode string.|
|STATUS_BUFFER_OVERFLOW | Value is too large to convert, or the UNICODE_STRING structure is too small to hold the result.|
|STATUS_INVALID_PARAMETER | The specified code base is not valid. The only valid values are 0, 2, 8, 10, and 16.|
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlappendunicodestringtostring">RtlAppendUnicodeStringToString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlintegertounicodestring">RtlIntegerToUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlunicodestringtointeger">RtlUnicodeStringToInteger</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

