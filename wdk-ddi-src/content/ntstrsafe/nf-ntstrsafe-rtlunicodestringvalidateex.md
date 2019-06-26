---
UID: NF:ntstrsafe.RtlUnicodeStringValidateEx
title: RtlUnicodeStringValidateEx function (ntstrsafe.h)
description: The RtlUnicodeStringValidateEx function validates the contents of a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringvalidateex.htm
tech.root: kernel
ms.assetid: 864935c4-28b8-4738-ac83-e51e6988248b
ms.date: 04/30/2018
ms.keywords: RtlUnicodeStringValidateEx, RtlUnicodeStringValidateEx function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringvalidateex, ntstrsafe/RtlUnicodeStringValidateEx, safestrings_dcb45919-f329-4637-b09b-f944ad034502.xml
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ntstrsafe.lib
- Ntstrsafe.dll
api_name:
- RtlUnicodeStringValidateEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringValidateEx function


## -description


The <b>RtlUnicodeStringValidateEx</b> function validates the contents of a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure.


## -parameters




### -param SourceString [in]

Optional. A pointer to a <b>UNICODE_STRING</b> structure to be validated. This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param dwFlags [in]

The following flag is defined: 





#### STRSAFE_IGNORE_NULLS

If this flag is set, the source pointer can be <b>NULL</b>. <b>RtlUnicodeStringValidateEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")). 


## -returns



<b>RtlUnicodeStringValidateEx</b> returns one of the following NTSTATUS values. 

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
This <i>success</i> status means that the function completed successfully.

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
 

If STRSAFE_IGNORE_NULLS is not set in dwFlags, <b>RtlUnicodeStringValidateEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li><i>SourceString</i>-><b>Length</b> % sizeof(WCHAR) does not equal zero.</li>
<li><i>SourceString</i>-><b>MaximumLength</b> % sizeof(WCHAR) does not equal zero.</li>
<li><i>SourceString</i>-><b>Length</b> is greater than <i>SourceString</i>-><b>MaximumLength</b>.</li>
<li><i>SourceString</i>-><b>MaximumLength</b> is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).</li>
<li><i>SourceString</i>-><b>Buffer</b> equals <b>NULL</b> but <i>SourceString</i>->Length or <i>SourceString</i>-><b>MaximumLength</b> does not equal zero.</li>
<li>An invalid flag is specified for <i>dwFlags</i>.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.




## -remarks



The <i>SourceString</i> pointer cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringvalidate">RtlUnicodeStringValidate</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

