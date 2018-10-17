---
UID: NF:ntifs.PsDereferenceImpersonationToken
title: PsDereferenceImpersonationToken function
author: windows-driver-content
description: The PsDereferenceImpersonationToken routine decrements the reference count of an impersonation token.
old-location: ifsk\psdereferenceimpersonationtoken.htm
tech.root: ifsk
ms.assetid: 8320d4d1-f282-4977-96e7-de6f63d86ec4
ms.date: 4/16/2018
ms.keywords: PsDereferenceImpersonationToken, PsDereferenceImpersonationToken routine [Installable File System Drivers], ifsk.psdereferenceimpersonationtoken, ntifs/PsDereferenceImpersonationToken, psref_8d62cb23-83a3-45fd-8b35-f7e38dd1548d.xml
ms.topic: function
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
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsDereferenceImpersonationToken
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsDereferenceImpersonationToken function


## -description


The <b>PsDereferenceImpersonationToken</b> routine decrements the reference count of an impersonation token.


## -parameters




### -param ImpersonationToken [in]

Pointer to the impersonation token whose reference count is to be decremented. If this is a <b>NULL</b> pointer, <b>PsDereferenceImpersonationToken</b> does nothing.


## -returns



None




## -remarks



If the token's reference count reaches zero, the token is deleted.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551907">PsImpersonateClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551929">PsReferenceImpersonationToken</a>
 

 

