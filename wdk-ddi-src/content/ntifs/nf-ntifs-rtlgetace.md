---
UID: NF:ntifs.RtlGetAce
title: RtlGetAce function
author: windows-driver-content
description: The RtlGetAce routine obtains a pointer to an access control entry (ACE) in an access control list (ACL).
old-location: ifsk\rtlgetace.htm
old-project: ifsk
ms.assetid: f528d20a-16f8-401f-a6e6-ab165a40e18a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlGetAce, RtlGetAce routine [Installable File System Drivers], ifsk.rtlgetace, ntifs/RtlGetAce, rtlref_e018acc3-f776-4d15-9e0b-9e34d286a746.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlGetAce
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlGetAce function


## -description


The <b>RtlGetAce</b> routine obtains a pointer to an access control entry (ACE) in an access control list (ACL). 


## -parameters




### -param Acl [in]

Pointer to an ACL containing the ACE to be retrieved. 


### -param AceIndex [in]

Specifies the ACE to which a pointer is retrieved. A value of zero corresponds to the first ACE in the ACL, 1 to the second ACE, and so on. 


### -param Ace [out]

Pointer to a caller-allocated variable to receive the address of the ACE within the ACL. 


## -returns



<b>RtlGetAce</b> returns STATUS_SUCCESS or an error status code such as STATUS_INVALID_PARAMETER. 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552151">RtlCreateAcl</a>
 

 

