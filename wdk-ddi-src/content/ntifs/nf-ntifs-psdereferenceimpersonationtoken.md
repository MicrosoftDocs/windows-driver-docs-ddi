---
UID: NF:ntifs.PsDereferenceImpersonationToken
title: PsDereferenceImpersonationToken function
author: windows-driver-content
description: The PsDereferenceImpersonationToken routine decrements the reference count of an impersonation token.
old-location: ifsk\psdereferenceimpersonationtoken.htm
old-project: ifsk
ms.assetid: 8320d4d1-f282-4977-96e7-de6f63d86ec4
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: psref_8d62cb23-83a3-45fd-8b35-f7e38dd1548d.xml, ifsk.psdereferenceimpersonationtoken, PsDereferenceImpersonationToken routine [Installable File System Drivers], ntifs/PsDereferenceImpersonationToken, PsDereferenceImpersonationToken
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsDereferenceImpersonationToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsDereferenceImpersonationToken function


## -description


The <b>PsDereferenceImpersonationToken</b> routine decrements the reference count of an impersonation token.


## -syntax


````
VOID PsDereferenceImpersonationToken(
  _In_ PACCESS_TOKEN ImpersonationToken
);
````


## -parameters




### -param ImpersonationToken [in]

Pointer to the impersonation token whose reference count is to be decremented. If this is a <b>NULL</b> pointer, <b>PsDereferenceImpersonationToken</b> does nothing.


## -returns



None




## -remarks



If the token's reference count reaches zero, the token is deleted.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\ntifs\nf-ntifs-psimpersonateclient.md">PsImpersonateClient</a>



<a href="..\ntifs\nf-ntifs-psreferenceimpersonationtoken.md">PsReferenceImpersonationToken</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsDereferenceImpersonationToken routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

