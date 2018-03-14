---
UID: NF:ntstrsafe.RtlUnicodeStringInitEx
title: RtlUnicodeStringInitEx function
author: windows-driver-content
description: The RtlUnicodeStringInitEx function initializes a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringinitex.htm
old-project: kernel
ms.assetid: d57fee0b-2dd3-4fad-bc7e-d413c08e2441
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlUnicodeStringInitEx, RtlUnicodeStringInitEx function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringinitex, ntstrsafe/RtlUnicodeStringInitEx, safestrings_fab7496b-3acf-416d-8425-6936a73f1ca7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows XP with Service Pack 1 (SP1).
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
-	RtlUnicodeStringInitEx
product: Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---

# RtlUnicodeStringInitEx function


## -description


The <b>RtlUnicodeStringInitEx</b> function initializes a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure.


## -syntax


````
NTSTATUS RtlUnicodeStringInitEx(
  _Out_    PUNICODE_STRING  DestinationString,
  _In_opt_ NTSTRSAFE_PCWSTR pszSrc,
  _In_     DWORD            dwFlags
);
````


## -parameters




### -param DestinationString [out]

Optional. A pointer to a <b>UNICODE_STRING</b> structure to be initialized. The <i>pszSrc</i> pointer is copied into the <i>DestinationString</i> parameter's <b>UNICODE_STRING</b> structure. The maximum number of characters in the string that <i>pszSrc</i> points to is NTSTRSAFE_UNICODE_STRING_MAX_CCH. <i>DestinationString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param pszSrc [in, optional]

Optional. A pointer to a null-terminated string constant. This string pointer will be copied to the <b>Buffer</b> member of the <b>UNICODE_STRING</b> structure pointed to by the <i>DestinationString</i> parameter. This string pointer can be <b>NULL</b>.


### -param dwFlags [in]

The following flag is defined: 





#### STRSAFE_IGNORE_NULLS

If this flag is set, the source pointer can be <b>NULL</b>. <b>RtlUnicodeStringInitEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")), which can be copied.


## -returns



<b>RtlUnicodeStringInitEx</b> returns one of the following NTSTATUS values. 

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
This <i>success</i> status means that source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.

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
 

<b>RtlUnicodeStringInitEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The length of the string that the <i>pszSrc</i> parameter points to is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH characters.</li>
<li>The <i>DestinationString</i> pointer is <b>NULL</b>, but the <i>pszSrc</i> pointer is not <b>NULL</b>.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringInitEx</b> function does the following:

<ul>
<li>
Sets the <b>Length</b> member of the <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure to the length, in bytes, of the string that the <i>pszSrc</i> parameter points to. 

</li>
<li>
Sets the <b>MaximumLength</b> member of the <b>UNICODE_STRING</b> structure to the length, in bytes, of the string that the <i>pszSrc</i> parameter points to plus 2 bytes. 

</li>
<li>
Sets the <b>Buffer</b> member of the <b>UNICODE_STRING</b> structure to the address that the <i>pszSrc</i> parameter specifies.

</li>
</ul>
The <i>DestinationString</i> pointer cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinit.md">RtlUnicodeStringInit</a>



 

 


