---
UID: NF:wdm.RtlIntPtrToUnicodeString
title: RtlIntPtrToUnicodeString macro
author: windows-driver-content
description: The RtlIntPtrToUnicodeString routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base.
old-location: kernel\rtlintptrtounicodestring.htm
tech.root: kernel
ms.assetid: 9bcd278f-b6eb-4e88-8255-f2724bfca285
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlIntPtrToUnicodeString, RtlIntPtrToUnicodeString routine [Kernel-Mode Driver Architecture], k109_8ec9aafc-288e-4814-a22b-8b8e973689be.xml, kernel.rtlintptrtounicodestring, wdm/RtlIntPtrToUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlIntPtrToUnicodeString
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

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that receives the string representation of <i>Value</i>. The buffer specified by the <i>Buffer</i> of <i>String</i> must be large enough to hold the result. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561736">RtlAppendUnicodeStringToString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561941">RtlIntegerToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562973">RtlUnicodeStringToInteger</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

