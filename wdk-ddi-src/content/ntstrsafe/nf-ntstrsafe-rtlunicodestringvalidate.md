---
UID: NF:ntstrsafe.RtlUnicodeStringValidate
title: RtlUnicodeStringValidate function
author: windows-driver-content
description: The RtlUnicodeStringValidate function validates the contents of a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringvalidate.htm
old-project: kernel
ms.assetid: 7c4f452e-df7b-401b-a62e-20e0b2164172
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlunicodestringvalidate, RtlUnicodeStringValidate, RtlUnicodeStringValidate function [Kernel-Mode Driver Architecture], safestrings_65cec2b6-a948-423e-b7e3-786ae2a9ab1a.xml, ntstrsafe/RtlUnicodeStringValidate
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
-	RtlUnicodeStringValidate
product: Windows
targetos: Windows
req.typenames: "*PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE"
---

# RtlUnicodeStringValidate function


## -description


The <b>RtlUnicodeStringValidate</b> function validates the contents of a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure.


## -syntax


````
NTSTATUS RtlUnicodeStringValidate(
  _In_ PCUNICODE_STRING SourceString
);
````


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
</ul>For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.



## -remarks


The <i>SourceString</i> pointer cannot be <b>NULL</b>. If you need to specify a <b>NULL</b> pointer value, use the <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringvalidateex.md">RtlUnicodeStringValidateEx</a> function.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringvalidateex.md">RtlUnicodeStringValidateEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringValidate function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

