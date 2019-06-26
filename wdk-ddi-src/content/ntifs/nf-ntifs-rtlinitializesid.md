---
UID: NF:ntifs.RtlInitializeSid
title: RtlInitializeSid function (ntifs.h)
description: The RtlInitializeSid routine initializes a security identifier (SID) structure.
old-location: ifsk\rtlinitializesid.htm
tech.root: ifsk
ms.assetid: 6b87483f-8d5e-4e1d-839d-2271990dcbaa
ms.date: 04/16/2018
ms.keywords: RtlInitializeSid, RtlInitializeSid routine [Installable File System Drivers], ifsk.rtlinitializesid, ntifs/RtlInitializeSid, rtlref_fbcc1ed7-4929-415f-9644-b8d9521a5c1a.xml
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlInitializeSid
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInitializeSid function


## -description


The <b>RtlInitializeSid</b> routine initializes a security identifier (SID) structure. 


## -parameters




### -param Sid [out]

Pointer to a caller-allocated SID structure to be initialized. 


### -param IdentifierAuthority [in]

Pointer to an SID_IDENTIFIER_AUTHORITY structure to set in the SID structure. 


### -param SubAuthorityCount [in]

Number of subauthorities to set in the SID. Subauthority values must be set separately, as described in the following Remarks section. 


## -returns



<b>RtlInitializeSid</b> returns one of the following:

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
The SID was successfully initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>SubAuthorityCount</i> value is invalid.

</td>
</tr>
</table>
 




## -remarks



Although <b>RtlInitializeSid</b> sets the number of subauthorities for the SID, it does not set the subauthority values. This must be done separately by calling <b>RtlSubAuthoritySid</b>. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlsubauthoritysid">RtlSubAuthoritySid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid_identifier_authority">SID_IDENTIFIER_AUTHORITY</a>
 

 

