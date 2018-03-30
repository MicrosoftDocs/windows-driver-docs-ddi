---
UID: NF:ntifs.PsDereferencePrimaryToken
title: PsDereferencePrimaryToken function
author: windows-driver-content
description: The PsDereferencePrimaryToken routine decrements the reference count of a primary token.
old-location: ifsk\psdereferenceprimarytoken.htm
old-project: ifsk
ms.assetid: cff4bd05-b70d-4c07-a6c0-7ee4287aeab0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PsDereferencePrimaryToken, PsDereferencePrimaryToken routine [Installable File System Drivers], ifsk.psdereferenceprimarytoken, ntifs/PsDereferencePrimaryToken, psref_d3e4caeb-19a5-49d5-909a-5cb78a54f2e5.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsDereferencePrimaryToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsDereferencePrimaryToken function


## -description


The <b>PsDereferencePrimaryToken</b> routine decrements the reference count of a primary token.


## -parameters




### -param PrimaryToken [in]

Pointer to the primary token whose reference count is to be decremented.


## -returns



None




## -remarks



If the token's reference count reaches zero, the token is deleted.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551893">PsDereferenceImpersonationToken</a>
 

 

