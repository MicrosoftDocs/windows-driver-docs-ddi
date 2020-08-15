---
UID: NF:ntifs.SeTokenIsRestricted
title: SeTokenIsRestricted function (ntifs.h)
description: The SeTokenIsRestricted routine determines whether a token contains a list of restricting security identifiers (SID).
old-location: ifsk\setokenisrestricted.htm
tech.root: ifsk
ms.assetid: 111ba3a7-1321-4c69-9aae-f1ff5df9fab6
ms.date: 04/16/2018
keywords: ["SeTokenIsRestricted function"]
ms.keywords: SeTokenIsRestricted, SeTokenIsRestricted routine [Installable File System Drivers], ifsk.setokenisrestricted, ntifs/SeTokenIsRestricted, seref_f16e3f4e-1fcb-4232-8fe2-e46ef238b7e4.xml
f1_keywords:
 - "ntifs/SeTokenIsRestricted"
 - "SeTokenIsRestricted"
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
- SeTokenIsRestricted
targetos: Windows
req.typenames: 
---

# SeTokenIsRestricted function


## -description


The <b>SeTokenIsRestricted</b> routine determines whether a token contains a list of restricting security identifiers (SID).


## -parameters




### -param Token 
[in]
Pointer to the access token to test.


## -returns



<b>SeTokenIsRestricted</b> returns <b>TRUE</b> if the token contains a list of restricting SIDs, <b>FALSE</b> otherwise.




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
 

 

