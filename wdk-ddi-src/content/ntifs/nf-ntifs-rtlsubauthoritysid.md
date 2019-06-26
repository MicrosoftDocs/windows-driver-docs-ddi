---
UID: NF:ntifs.RtlSubAuthoritySid
title: RtlSubAuthoritySid function (ntifs.h)
description: The RtlSubAuthoritySid routine returns a pointer to a specified subauthority of a security identifier (SID).
old-location: ifsk\rtlsubauthoritysid.htm
tech.root: ifsk
ms.assetid: bd3f84ad-d617-4744-b423-1d82da3b05c0
ms.date: 04/16/2018
ms.keywords: RtlSubAuthoritySid, RtlSubAuthoritySid routine [Installable File System Drivers], ifsk.rtlsubauthoritysid, ntifs/RtlSubAuthoritySid, rtlref_d901f9ac-d7c4-49e1-871e-75aee9fa8c2b.xml
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
- RtlSubAuthoritySid
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlSubAuthoritySid function


## -description


The <b>RtlSubAuthoritySid</b> routine returns a pointer to a specified subauthority of a security identifier (SID). 


## -parameters




### -param Sid [in]

Pointer to the SID structure. The SID must have been initialized by calling <b>RtlInitializeSid</b>.


### -param SubAuthority

<p>Zero-based index indicating which subauthority is being specified. This value is not validated against the number of subauthorities in the SID. </p>




## -returns



If the call to <b>RtlSubAuthoritySid</b> succeeds, the return value is a pointer to the specified SID subauthority. The subauthority value is a relative identifier. (The relative identifier, or RID, is the portion of a SID that identifies a user or group in relation to the authority that issued the SID.) 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlinitializesid">RtlInitializeSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid">SID</a>
 

 

