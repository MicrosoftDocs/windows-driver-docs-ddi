---
UID: NF:ntstrsafe.RtlUnicodeStringInit
title: RtlUnicodeStringInit function
description: The RtlUnicodeStringInit function initializes a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringinit.htm
tech.root: kernel
ms.assetid: 319d1d6e-a4a2-4c2c-9c30-948c5f03a2be
ms.date: 04/30/2018
ms.keywords: RtlUnicodeStringInit, RtlUnicodeStringInit function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringinit, ntstrsafe/RtlUnicodeStringInit, safestrings_7540072b-061a-46be-a2ea-72c4da1790dd.xml
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
-	RtlUnicodeStringInit
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringInit function


## -description


The <b>RtlUnicodeStringInit</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure.


## -parameters




### -param DestinationString [out]

A pointer to a <b>UNICODE_STRING</b> structure to be initialized. The <i>pszSrc </i>pointer is copied into the <i>DestinationString</i> parameter's <b>UNICODE_STRING</b> structure. The maximum number of characters in the string that <i>pszSrc</i> points to is NTSTRSAFE_UNICODE_STRING_MAX_CCH.


### -param pszSrc [in, optional]

Optional. A pointer to a null-terminated string constant. This string pointer will be copied to the <b>Buffer</b> member of the <b>UNICODE_STRING</b> structure pointed to by the <i>DestinationString</i> parameter. This string pointer can be <b>NULL</b>.


## -returns



<b>RtlUnicodeStringInit</b> returns one of the following NTSTATUS values.

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
 

<b>RtlUnicodeStringInit</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The length of the string that the <i>pszSrc</i> parameter points to is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH characters.</li>
<li>The <i>DestinationString</i> pointer is <b>NULL</b>, but the <i>pszSrc</i> pointer is not <b>NULL</b>.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringInit</b> function does the following:

<ul>
<li>
Sets the <b>Length</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that is pointed to by the <i>pszSrc</i> parameter to the length, in bytes, of the string that the <i>pszSrc</i> parameter points to.

</li>
<li>
Sets the <b>MaximumLength</b> member of the <b>UNICODE_STRING</b> structure to the length, in bytes, of the string that the <i>pszSrc</i> parameter points to plus 2 bytes. 

</li>
<li>
Sets the <b>Buffer</b> member of the <b>UNICODE_STRING</b> structure to the address that the <i>pszSrc</i> parameter specifies.

</li>
</ul>
The <i>DestinationString</i> pointer should not be <b>NULL</b>. If you need to specify <b>NULL</b> <i>DestinationString</i> pointer values, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562958">RtlUnicodeStringInitEx</a> function.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562958">RtlUnicodeStringInitEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

