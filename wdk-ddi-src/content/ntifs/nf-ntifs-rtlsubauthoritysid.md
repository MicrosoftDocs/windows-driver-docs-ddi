---
UID: NF:ntifs.RtlSubAuthoritySid
title: RtlSubAuthoritySid function
author: windows-driver-content
description: The RtlSubAuthoritySid routine returns a pointer to a specified subauthority of a security identifier (SID).
old-location: ifsk\rtlsubauthoritysid.htm
old-project: ifsk
ms.assetid: bd3f84ad-d617-4744-b423-1d82da3b05c0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlSubAuthoritySid, RtlSubAuthoritySid routine [Installable File System Drivers], ifsk.rtlsubauthoritysid, ntifs/RtlSubAuthoritySid, rtlref_d901f9ac-d7c4-49e1-871e-75aee9fa8c2b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlSubAuthoritySid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlSubAuthoritySid function


## -description


The <b>RtlSubAuthoritySid</b> routine returns a pointer to a specified subauthority of a security identifier (SID). 


## -syntax


````
PULONG RtlSubAuthoritySid(
  _In_ PSID  Sid,
  _In_ ULONG SubAuthorityCount
);
````


## -parameters




### -param Sid [in]

Pointer to the SID structure. The SID must have been initialized by calling <b>RtlInitializeSid</b>.


### -param SubAuthority

TBD




#### - SubAuthorityCount [in]

Zero-based index indicating which subauthority is being specified. This value is not validated against the number of subauthorities in the SID. 


## -returns



If the call to <b>RtlSubAuthoritySid</b> succeeds, the return value is a pointer to the specified SID subauthority. The subauthority value is a relative identifier. (The relative identifier, or RID, is the portion of a SID that identifies a user or group in relation to the authority that issued the SID.) 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\ntifs\nf-ntifs-rtlinitializesid.md">RtlInitializeSid</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSubAuthoritySid routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

