---
UID: NF:ntstrsafe.RtlUnicodeStringValidateEx
title: RtlUnicodeStringValidateEx function
author: windows-driver-content
description: The RtlUnicodeStringValidateEx function validates the contents of a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringvalidateex.htm
old-project: kernel
ms.assetid: 864935c4-28b8-4738-ac83-e51e6988248b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: safestrings_dcb45919-f329-4637-b09b-f944ad034502.xml, kernel.rtlunicodestringvalidateex, RtlUnicodeStringValidateEx function [Kernel-Mode Driver Architecture], RtlUnicodeStringValidateEx, ntstrsafe/RtlUnicodeStringValidateEx
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
-	RtlUnicodeStringValidateEx
product: Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---

# RtlUnicodeStringValidateEx function


## -description


The <b>RtlUnicodeStringValidateEx</b> function validates the contents of a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure.


## -syntax


````
NTSTATUS RtlUnicodeStringValidateEx(
  _In_ PCUNICODE_STRING SourceString,
  _In_ DWORD            dwFlags
);
````


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
<li><i>SourceString</i>-&gt;<b>Length</b> % sizeof(WCHAR) does not equal zero.</li>
<li><i>SourceString</i>-&gt;<b>MaximumLength</b> % sizeof(WCHAR) does not equal zero.</li>
<li><i>SourceString</i>-&gt;<b>Length</b> is greater than <i>SourceString</i>-&gt;<b>MaximumLength</b>.</li>
<li><i>SourceString</i>-&gt;<b>MaximumLength</b> is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).</li>
<li><i>SourceString</i>-&gt;<b>Buffer</b> equals <b>NULL</b> but <i>SourceString</i>-&gt;Length or <i>SourceString</i>-&gt;<b>MaximumLength</b> does not equal zero.</li>
<li>An invalid flag is specified for <i>dwFlags</i>.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.




## -remarks



The <i>SourceString</i> pointer cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringvalidate.md">RtlUnicodeStringValidate</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringValidateEx function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

