---
UID: NF:ntifs.SeTokenIsAdmin
title: SeTokenIsAdmin function (ntifs.h)
description: The SeTokenIsAdmin routine determines whether a token contains the local administrators group.
old-location: ifsk\setokenisadmin.htm
tech.root: ifsk
ms.assetid: 7d0a5d28-175a-44a7-888f-d11dc3f55904
ms.date: 04/16/2018
keywords: ["SeTokenIsAdmin function"]
ms.keywords: SeTokenIsAdmin, SeTokenIsAdmin routine [Installable File System Drivers], ifsk.setokenisadmin, ntifs/SeTokenIsAdmin, seref_e621b2f6-c7c3-4df0-90d4-87a42080e1bd.xml
f1_keywords:
 - "ntifs/SeTokenIsAdmin"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeTokenIsAdmin
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeTokenIsAdmin function


## -description


The <b>SeTokenIsAdmin</b> routine determines whether a token contains the local administrators group.


## -parameters




### -param Token [in]

Pointer to the token.


## -returns



<b>SeTokenIsAdmin</b> returns <b>TRUE</b> if the token contains the local administrators group, <b>FALSE</b> otherwise.




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psdereferenceimpersonationtoken">PsDereferenceImpersonationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psdereferenceprimarytoken">PsDereferencePrimaryToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryauthenticationidtoken">SeQueryAuthenticationIdToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequerysubjectcontexttoken">SeQuerySubjectContextToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokenisadmin">SeTokenIsAdmin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokenisrestricted">SeTokenIsRestricted</a>
 

 

