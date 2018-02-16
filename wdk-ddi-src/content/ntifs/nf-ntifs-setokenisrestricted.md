---
UID: NF:ntifs.SeTokenIsRestricted
title: SeTokenIsRestricted function
author: windows-driver-content
description: The SeTokenIsRestricted routine determines whether a token contains a list of restricting security identifiers (SID).
old-location: ifsk\setokenisrestricted.htm
old-project: ifsk
ms.assetid: 111ba3a7-1321-4c69-9aae-f1ff5df9fab6
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.setokenisrestricted, ntifs/SeTokenIsRestricted, seref_f16e3f4e-1fcb-4232-8fe2-e46ef238b7e4.xml, SeTokenIsRestricted routine [Installable File System Drivers], SeTokenIsRestricted
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeTokenIsRestricted
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeTokenIsRestricted function


## -description


The <b>SeTokenIsRestricted</b> routine determines whether a token contains a list of restricting security identifiers (SID).


## -syntax


````
BOOLEAN SeTokenIsRestricted(
  _In_ PACCESS_TOKEN Token
);
````


## -parameters




### -param Token [in]

Pointer to the access token to test.


## -returns



<b>SeTokenIsRestricted</b> returns <b>TRUE</b> if the token contains a list of restricting SIDs, <b>FALSE</b> otherwise.




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>



<a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>



<a href="..\ntifs\nf-ntifs-psdereferenceimpersonationtoken.md">PsDereferenceImpersonationToken</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>



<a href="..\ntifs\nf-ntifs-setokenisadmin.md">SeTokenIsAdmin</a>



<a href="..\ntifs\nf-ntifs-psdereferenceprimarytoken.md">PsDereferencePrimaryToken</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeTokenIsRestricted routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

