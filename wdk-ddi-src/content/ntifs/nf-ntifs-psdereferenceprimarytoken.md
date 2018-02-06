---
UID: NF:ntifs.PsDereferencePrimaryToken
title: PsDereferencePrimaryToken function
author: windows-driver-content
description: The PsDereferencePrimaryToken routine decrements the reference count of a primary token.
old-location: ifsk\psdereferenceprimarytoken.htm
old-project: ifsk
ms.assetid: cff4bd05-b70d-4c07-a6c0-7ee4287aeab0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: psref_d3e4caeb-19a5-49d5-909a-5cb78a54f2e5.xml, ifsk.psdereferenceprimarytoken, ntifs/PsDereferencePrimaryToken, PsDereferencePrimaryToken, PsDereferencePrimaryToken routine [Installable File System Drivers]
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
-	PsDereferencePrimaryToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsDereferencePrimaryToken function


## -description


The <b>PsDereferencePrimaryToken</b> routine decrements the reference count of a primary token.


## -syntax


````
VOID PsDereferencePrimaryToken(
  _In_ PACCESS_TOKEN PrimaryToken
);
````


## -parameters




### -param PrimaryToken [in]

Pointer to the primary token whose reference count is to be decremented.


## -returns


None



## -remarks


If the token's reference count reaches zero, the token is deleted.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.



## -see-also

<a href="..\ntifs\nf-ntifs-psdereferenceimpersonationtoken.md">PsDereferenceImpersonationToken</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsDereferencePrimaryToken routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

