---
UID: NF:ntifs.SeUnlockSubjectContext
title: SeUnlockSubjectContext function (ntifs.h)
description: The SeUnlockSubjectContext routine unlocks the tokens of a captured subject context that were locked by a call to SeLockSubjectContext.
old-location: ifsk\seunlocksubjectcontext.htm
tech.root: ifsk
ms.assetid: 5b0dda8f-52de-462b-8dab-8aed86e5dc0e
ms.date: 04/16/2018
keywords: ["SeUnlockSubjectContext function"]
ms.keywords: SeUnlockSubjectContext, SeUnlockSubjectContext routine [Installable File System Drivers], ifsk.seunlocksubjectcontext, ntifs/SeUnlockSubjectContext, seref_a07c19ad-03a8-403d-9844-9e85862377ab.xml
f1_keywords:
 - "ntifs/SeUnlockSubjectContext"
 - "SeUnlockSubjectContext"
req.header: ntifs.h
req.include-header: Ntifs.h, Wdm.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeUnlockSubjectContext
targetos: Windows
req.typenames: 
---

# SeUnlockSubjectContext function


## -description


The <b>SeUnlockSubjectContext</b> routine unlocks the tokens of a captured subject context that were locked by a call to <b>SeLockSubjectContext</b>.


## -parameters




### -param SubjectContext 
[in]
Pointer to a SECURITY_SUBJECT_CONTEXT structure whose tokens are to be unlocked.


## -remarks



<b>SeUnlockSubjectContext</b> releases the read locks on the tokens in the captured subject context.

Each call to <b>SeLockSubjectContext</b> must be matched by a subsequent call to <b>SeUnlockSubjectContext</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-secapturesubjectcontext">SeCaptureSubjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-selocksubjectcontext">SeLockSubjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seprivilegecheck">SePrivilegeCheck</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryauthenticationidtoken">SeQueryAuthenticationIdToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequerysubjectcontexttoken">SeQuerySubjectContextToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sereleasesubjectcontext">SeReleaseSubjectContext</a>
 

 

