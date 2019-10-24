---
UID: NF:ntifs.RtlConvertSidToUnicodeString
title: RtlConvertSidToUnicodeString function (ntifs.h)
description: The RtlConvertSidToUnicodeString routine generates a printable Unicode string representation of a security identifier (SID).
old-location: ifsk\rtlconvertsidtounicodestring.htm
tech.root: ifsk
ms.assetid: 5dea6764-9ca0-4d38-9900-174637c4f648
ms.date: 04/16/2018
ms.keywords: RtlConvertSidToUnicodeString, RtlConvertSidToUnicodeString routine [Installable File System Drivers], ifsk.rtlconvertsidtounicodestring, ntifs/RtlConvertSidToUnicodeString, rtlref_4b2b8867-c248-49e9-9b38-de3f9449a504.xml
ms.topic: function
f1_keywords:
 - "ntifs/RtlConvertSidToUnicodeString"
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later Windows operating systems.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlConvertSidToUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlConvertSidToUnicodeString function


## -description


The <b>RtlConvertSidToUnicodeString</b> routine generates a printable Unicode string representation of a security identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>). 


## -parameters




### -param UnicodeString [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure to contain the generated Unicode string.  The <i>UnicodeString->MaximumLength</i> member is set only if <i>AllocateDestinationString</i> is <b>TRUE</b>.


### -param Sid [in]

A pointer to the SID structure that is to be converted to Unicode (the SID structure is unaffected).


### -param AllocateDestinationString [in]

A Boolean flag that indicates whether this routine will allocate the UnicodeString buffer. If <b>TRUE</b>, only the <i>UnicodeString->Buffer</i> member is allocated and the rest of the <i>UnicodeString</i> structure must be allocated by the caller.


## -returns



The <b>RtlConvertSidToUnicodeString</b> routine can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS </b></dt>
</dl>
</td>
<td width="60%">
The conversion was successful. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW </b></dt>
</dl>
</td>
<td width="60%">
This is returned if <i>AllocateDestinationString</i> is <b>FALSE</b> and the caller supplied <i>UnicodeString</i> buffer is too small to hold the converted Unicode string. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY </b></dt>
</dl>
</td>
<td width="60%">
This is returned if <i>AllocateDestinationString</i> is <b>TRUE</b> and there is insufficient memory to allocate the <i>UnicodeString</i> buffer. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SID </b></dt>
</dl>
</td>
<td width="60%">
The specified <i>SID</i> structure is not structurally valid. 

</td>
</tr>
</table>
 




## -remarks



The generated Unicode string will take one of two forms.  If the value of the IdentifierAuthority member of the <i>SID</i> is less than or equal to 2^32, the IdentifierAuthority member will be generated as decimal. For example, a <i>SID</i> with an IdentifierAuthority of 281,736 generates:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre> S-1-281736-12-72-9-110</pre>
</td>
</tr>
</table></span></div>
Otherwise the IdentifierAuthority will be generated as hexadecimal. For example, a <i>SID</i> with an IdentifierAuthority of 173,495,281,736 generates:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre> S-1-0x28651FE848-12-72-9-110</pre>
</td>
</tr>
</table></span></div>
All other members in the <i>SID</i> will be generated as decimal.

If <i>AllocateDestinationString</i> is <b>TRUE</b>, the allocated buffer must be deallocated by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

