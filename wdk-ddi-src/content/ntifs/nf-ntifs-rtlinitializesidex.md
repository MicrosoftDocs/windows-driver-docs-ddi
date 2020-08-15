---
UID: NF:ntifs.RtlInitializeSidEx
title: RtlInitializeSidEx function (ntifs.h)
description: The RtlInitializeSidEx routine initializes a pre-allocated security identifier (SID) structure.
old-location: ifsk\rtlinitializesidex.htm
tech.root: ifsk
ms.assetid: 367D8BC1-07F4-474E-913A-5F825320A70C
ms.date: 04/16/2018
keywords: ["RtlInitializeSidEx function"]
ms.keywords: RtlInitializeSidEx, RtlInitializeSidEx routine [Installable File System Drivers], ifsk.rtlinitializesidex, ntifs/RtlInitializeSidEx
f1_keywords:
 - "ntifs/RtlInitializeSidEx"
 - "RtlInitializeSidEx"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows 10 and later.
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
- RtlInitializeSidEx
targetos: Windows
req.typenames: 
---

# RtlInitializeSidEx function


## -description


The <b>RtlInitializeSidEx</b> routine initializes a pre-allocated security identifier (SID) structure. 


## -parameters




### -param Sid 
[out]
Pointer to a caller-allocated SID structure to be initialized. 


### -param IdentifierAuthority 
[in]
Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid_identifier_authority">SID_IDENTIFIER_AUTHORITY</a> structure to set in the SID structure. 


### -param SubAuthorityCount 
[in]
Number of sub-authorities to set in the SID.


### -param param

<p>The values to set each sub-authority. The caller must specify the SubAuthorityCount argument.</p>




####### - ...

The values to set each sub-authority. The caller must specify the SubAuthorityCount argument.


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



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsubauthoritysid">RtlSubAuthoritySid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid_identifier_authority">SID_IDENTIFIER_AUTHORITY</a>
 

 

