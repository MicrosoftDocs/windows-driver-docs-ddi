---
UID: NF:ntifs.SeTokenIsRestricted
title: SeTokenIsRestricted function
author: windows-driver-content
description: The SeTokenIsRestricted routine determines whether a token contains a list of restricting security identifiers (SID).
old-location: ifsk\setokenisrestricted.htm
old-project: ifsk
ms.assetid: 111ba3a7-1321-4c69-9aae-f1ff5df9fab6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SeTokenIsRestricted, SeTokenIsRestricted routine [Installable File System Drivers], ifsk.setokenisrestricted, ntifs/SeTokenIsRestricted, seref_f16e3f4e-1fcb-4232-8fe2-e46ef238b7e4.xml
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
-	SeTokenIsRestricted
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeTokenIsRestricted function


## -description


The <b>SeTokenIsRestricted</b> routine determines whether a token contains a list of restricting security identifiers (SID).


## -parameters




### -param Token [in]

Pointer to the access token to test.


## -returns



<b>SeTokenIsRestricted</b> returns <b>TRUE</b> if the token contains a list of restricting SIDs, <b>FALSE</b> otherwise.




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551893">PsDereferenceImpersonationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551896">PsDereferencePrimaryToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556688">SeQueryAuthenticationIdToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556698">SeQuerySubjectContextToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556720">SeTokenIsAdmin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556724">SeTokenIsRestricted</a>
 

 

