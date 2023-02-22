---
UID: NF:ntifs.SeUnlockSubjectContext
title: SeUnlockSubjectContext function (ntifs.h)
description: Learn more about the SeUnlockSubjectContext routine.
tech.root: ifsk
ms.date: 02/21/2023
keywords: ["SeUnlockSubjectContext function"]
ms.keywords: SeUnlockSubjectContext, SeUnlockSubjectContext routine [Installable File System Drivers], ifsk.seunlocksubjectcontext, ntifs/SeUnlockSubjectContext, seref_a07c19ad-03a8-403d-9844-9e85862377ab.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SeUnlockSubjectContext
 - ntifs/SeUnlockSubjectContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeUnlockSubjectContext
---

# SeUnlockSubjectContext function (ntifs.h)

## -description

The **SeUnlockSubjectContext** routine unlocks the tokens of a captured subject context that were locked by a call to **SeLockSubjectContext**.

## -parameters

### -param SubjectContext [in]

Pointer to a SECURITY_SUBJECT_CONTEXT structure whose tokens are to be unlocked.

## -remarks

**SeUnlockSubjectContext** releases the read locks on the tokens in the captured subject context.

Each call to **SeLockSubjectContext** must be matched by a subsequent call to **SeUnlockSubjectContext**.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context)

[**SeCaptureSubjectContext**](nf-ntifs-secapturesubjectcontext.md)

[**SeCaptureSubjectContextEx**](nf-ntifs-secapturesubjectcontextex.md)

[**SeLockSubjectContext**](nf-ntifs-selocksubjectcontext.md)

[**SePrivilegeCheck**](nf-ntifs-seprivilegecheck.md)

[**SeQueryAuthenticationIdToken**](nf-ntifs-sequeryauthenticationidtoken.md)

[**SeQuerySubjectContextToken**](nf-ntifs-sequerysubjectcontexttoken.md)

[**SeReleaseSubjectContext**](nf-ntifs-sereleasesubjectcontext.md)
