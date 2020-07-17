---
UID: NF:ntifs.RtlLengthRequiredSid
title: RtlLengthRequiredSid function (ntifs.h)
description: The RtlLengthRequiredSid routine returns the length, in bytes, of the buffer required to store a security identifier (SID) with a specified number of subauthorities.
old-location: ifsk\rtllengthrequiredsid.htm
tech.root: ifsk
ms.assetid: 1d6aa888-8e61-4a0e-88ea-13842fc2fff2
ms.date: 04/16/2018
keywords: ["RtlLengthRequiredSid function"]
ms.keywords: RtlLengthRequiredSid, RtlLengthRequiredSid routine [Installable File System Drivers], ifsk.rtllengthrequiredsid, ntifs/RtlLengthRequiredSid, rtlref_78e8a660-8510-40bc-b221-747538423488.xml
f1_keywords:
 - "ntifs/RtlLengthRequiredSid"
 - "RtlLengthRequiredSid"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlLengthRequiredSid
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLengthRequiredSid function


## -description


The <b>RtlLengthRequiredSid</b> routine returns the length, in bytes, of the buffer required to store a security identifier (SID) with a specified number of subauthorities. 


## -parameters




### -param SubAuthorityCount [in]

The number of subauthorities to be stored in the SID. 


## -returns



<b>RtlLengthRequiredSid</b> returns the length, in bytes, of the buffer required to store the SID structure. 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlequalprefixsid">RtlEqualPrefixSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlequalsid">RtlEqualSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializesid">RtlInitializeSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtllengthsid">RtlLengthSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsubauthoritysid">RtlSubAuthoritySid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlvalidsid">RtlValidSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>
 

 

