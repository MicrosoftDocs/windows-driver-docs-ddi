---
UID: NF:ntifs.SeTokenIsAdmin
title: SeTokenIsAdmin function
author: windows-driver-content
description: The SeTokenIsAdmin routine determines whether a token contains the local administrators group.
old-location: ifsk\setokenisadmin.htm
old-project: ifsk
ms.assetid: 7d0a5d28-175a-44a7-888f-d11dc3f55904
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeTokenIsAdmin, SeTokenIsAdmin routine [Installable File System Drivers], ifsk.setokenisadmin, ntifs/SeTokenIsAdmin, seref_e621b2f6-c7c3-4df0-90d4-87a42080e1bd.xml
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
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeTokenIsAdmin
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeTokenIsAdmin function


## -description


The <b>SeTokenIsAdmin</b> routine determines whether a token contains the local administrators group.


## -syntax


````
BOOLEAN SeTokenIsAdmin(
  _In_ PACCESS_TOKEN Token
);
````


## -parameters




### -param Token [in]

Pointer to the token.


## -returns



<b>SeTokenIsAdmin</b> returns <b>TRUE</b> if the token contains the local administrators group, <b>FALSE</b> otherwise.




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\ntifs\nf-ntifs-psdereferenceprimarytoken.md">PsDereferencePrimaryToken</a>



<a href="..\ntifs\nf-ntifs-setokenisadmin.md">SeTokenIsAdmin</a>



<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>



<a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>



<a href="..\ntifs\nf-ntifs-psdereferenceimpersonationtoken.md">PsDereferenceImpersonationToken</a>



<a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeTokenIsAdmin routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

