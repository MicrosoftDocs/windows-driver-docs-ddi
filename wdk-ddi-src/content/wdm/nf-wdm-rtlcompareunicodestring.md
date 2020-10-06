---
UID: NF:wdm.RtlCompareUnicodeString
title: RtlCompareUnicodeString function (wdm.h)
description: The RtlCompareUnicodeString routine compares two Unicode strings.
old-location: kernel\rtlcompareunicodestring.htm
tech.root: kernel
ms.assetid: 82567434-be54-4436-a26e-9a89a532addf
ms.date: 04/30/2018
keywords: ["RtlCompareUnicodeString function"]
ms.keywords: RtlCompareUnicodeString, RtlCompareUnicodeString routine [Kernel-Mode Driver Architecture], k109_ddeef320-7510-446b-af6f-756c3999bec1.xml, kernel.rtlcompareunicodestring, wdm/RtlCompareUnicodeString
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
 - RtlCompareUnicodeString
 - wdm/RtlCompareUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlCompareUnicodeString
---

# RtlCompareUnicodeString function


## -description

The <b>RtlCompareUnicodeString</b> routine compares two Unicode strings.

## -parameters

### -param String1 

[in]
Pointer to the first string.

### -param String2 

[in]
Pointer to the second string.

### -param CaseInSensitive 

[in]
If <b>TRUE</b>, case should be ignored when doing the comparison.

## -returns

<b>RtlCompareUnicodeString</b> returns a signed value that gives the results of the comparison:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Zero</b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> equals <i>String2</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>< Zero</b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> is less than <i>String2</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>> Zero </b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> is greater than <i>String2</i>.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlcomparestring">RtlCompareString</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlequalstring">RtlEqualString</a>