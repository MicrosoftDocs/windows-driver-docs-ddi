---
UID: NF:ntstrsafe.RtlUnicodeStringValidate
title: RtlUnicodeStringValidate function
author: windows-driver-content
description: The RtlUnicodeStringValidate function validates the contents of a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringvalidate.htm
tech.root: kernel
ms.assetid: 7c4f452e-df7b-401b-a62e-20e0b2164172
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlUnicodeStringValidate, RtlUnicodeStringValidate function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringvalidate, ntstrsafe/RtlUnicodeStringValidate, safestrings_65cec2b6-a948-423e-b7e3-786ae2a9ab1a.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ntstrsafe.lib
-	Ntstrsafe.dll
api_name:
-	RtlUnicodeStringValidate
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringValidate function


## -description


The <b>RtlUnicodeStringValidate</b> function validates the contents of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure.


## -parameters




### -param SourceString [in]

A pointer to a <b>UNICODE_STRING</b> structure to be validated. 


## -returns



<b>RtlUnicodeStringValidate</b> returns one of the following NTSTATUS values. 

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
 

<b>RtlUnicodeStringValidate</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li><i>SourceString</i>-&gt;<b>Length</b> % sizeof(WCHAR) does not equal zero.</li>
<li><i>SourceString</i>-&gt;<b>MaximumLength</b> % sizeof(WCHAR) does not equal zero.</li>
<li><i>SourceString</i>-&gt;<b>Length</b> is greater than <i>SourceString</i>-&gt;<b>MaximumLength</b>.</li>
<li><i>SourceString</i>-&gt;<b>MaximumLength</b> is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).</li>
<li><i>SourceString</i>-&gt;<b>Buffer</b> equals <b>NULL</b> but <i>SourceString</i>-&gt;<b>Length</b> or <i>SourceString</i>-&gt;<b>MaximumLength</b> does not equal zero.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.




## -remarks



The <i>SourceString</i> pointer cannot be <b>NULL</b>. If you need to specify a <b>NULL</b> pointer value, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562982">RtlUnicodeStringValidateEx</a> function.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562982">RtlUnicodeStringValidateEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

