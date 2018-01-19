---
UID: NF:ntifs.RtlConvertSidToUnicodeString
title: RtlConvertSidToUnicodeString function
author: windows-driver-content
description: The RtlConvertSidToUnicodeString routine generates a printable Unicode string representation of a security identifier (SID).
old-location: ifsk\rtlconvertsidtounicodestring.htm
old-project: ifsk
ms.assetid: 5dea6764-9ca0-4d38-9900-174637c4f648
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlConvertSidToUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlConvertSidToUnicodeString
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# RtlConvertSidToUnicodeString function



## -description
The <b>RtlConvertSidToUnicodeString</b> routine generates a printable Unicode string representation of a security identifier (<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>). 



## -syntax

````
NTSTATUS RtlConvertSidToUnicodeString(
  _Inout_ PUNICODE_STRING UnicodeString,
  _In_    PSID            Sid,
  _In_    BOOLEAN         AllocateDestinationString
);
````


## -parameters

### -param UnicodeString [in, out]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure to contain the generated Unicode string.  The <i>UnicodeString-&gt;MaximumLength</i> member is set only if <i>AllocateDestinationString</i> is <b>TRUE</b>.


### -param Sid [in]

A pointer to the SID structure that is to be converted to Unicode (the SID structure is unaffected).


### -param AllocateDestinationString [in]

A Boolean flag that indicates whether this routine will allocate the UnicodeString buffer. If <b>TRUE</b>, only the <i>UnicodeString-&gt;Buffer</i> member is allocated and the rest of the <i>UnicodeString</i> structure must be allocated by the caller.


## -returns
The <b>RtlConvertSidToUnicodeString</b> routine can return one of the following values:
<dl>
<dt><b>STATUS_SUCCESS </b></dt>
</dl>The conversion was successful. 
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW </b></dt>
</dl>This is returned if <i>AllocateDestinationString</i> is <b>FALSE</b> and the caller supplied <i>UnicodeString</i> buffer is too small to hold the converted Unicode string. 
<dl>
<dt><b>STATUS_NO_MEMORY </b></dt>
</dl>This is returned if <i>AllocateDestinationString</i> is <b>TRUE</b> and there is insufficient memory to allocate the <i>UnicodeString</i> buffer. 
<dl>
<dt><b>STATUS_INVALID_SID </b></dt>
</dl>The specified <i>SID</i> structure is not structurally valid. 

 


## -remarks
The generated Unicode string will take one of two forms.  If the value of the IdentifierAuthority member of the <i>SID</i> is less than or equal to 2^32, the IdentifierAuthority member will be generated as decimal. For example, a <i>SID</i> with an IdentifierAuthority of 281,736 generates:

Otherwise the IdentifierAuthority will be generated as hexadecimal. For example, a <i>SID</i> with an IdentifierAuthority of 173,495,281,736 generates:

All other members in the <i>SID</i> will be generated as decimal.

If <i>AllocateDestinationString</i> is <b>TRUE</b>, the allocated buffer must be deallocated by using <a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlConvertSidToUnicodeString routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

