---
UID: NF:wudfwdm.RtlIntegerToUnicodeString
title: RtlIntegerToUnicodeString function
author: windows-driver-content
description: The RtlIntegerToUnicodeString routine converts an unsigned integer value to a null-terminated string of one or more Unicode characters in the specified base.
old-location: kernel\rtlintegertounicodestring.htm
old-project: kernel
ms.assetid: d9c82a97-a8fb-4c23-aa9c-23711d98fd8b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlIntegerToUnicodeString, RtlIntegerToUnicodeString routine [Kernel-Mode Driver Architecture], k109_2ed50455-f426-4072-be25-cab15c4c79cc.xml, kernel.rtlintegertounicodestring, wdm/RtlIntegerToUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfwdm.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlIntegerToUnicodeString
product: Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT
req.product: Windows 10 or later.
---

# RtlIntegerToUnicodeString function


## -description


The <b>RtlIntegerToUnicodeString</b> routine converts an unsigned integer value to a null-terminated string of one or more Unicode characters in the specified base.


## -syntax


````
NTSTATUS RtlIntegerToUnicodeString(
  _In_     ULONG           Value,
  _In_opt_ ULONG           Base,
  _Inout_  PUNICODE_STRING String
);
````


## -parameters




### -param Value [in]

Specifies the ULONG value to convert. 


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

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that receives the string representation of <i>Value</i>. The buffer specified by the <i>Buffer</i>  of <i>String</i> must be large enough to hold the result. 


## -returns



<b>RtlIntegerToUnicodeString</b> returns an NTSTATUS value. Possible return values include:

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

<a href="..\wudfwdm\nf-wudfwdm-rtlunicodestringtointeger.md">RtlUnicodeStringToInteger</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlappendunicodestringtostring.md">RtlAppendUnicodeStringToString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlIntegerToUnicodeString routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

