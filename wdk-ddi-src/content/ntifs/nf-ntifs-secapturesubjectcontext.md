---
UID: NF:ntifs.SeCaptureSubjectContext
title: SeCaptureSubjectContext function (ntifs.h)
description: The SeCaptureSubjectContext routine in ntifs.h captures the security context of the calling thread for access validation and auditing.
old-location: ifsk\secapturesubjectcontext.htm
tech.root: ifsk
ms.date: 02/09/2023
keywords: ["SeCaptureSubjectContext function"]
ms.keywords: SeCaptureSubjectContext, SeCaptureSubjectContext routine [Installable File System Drivers], ifsk.secapturesubjectcontext, ntifs/SeCaptureSubjectContext, seref_192d13d7-4841-4c3e-831f-c12fe3cde04f.xml
req.header: ntifs.h
req.include-header: Ntifs.h, Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
 - SeCaptureSubjectContext
 - ntifs/SeCaptureSubjectContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeCaptureSubjectContext
---

# SeCaptureSubjectContext function (ntifs.h)

## -description

**SeCaptureSubjectContext** takes a snapshot of the calling thread's context for access validation and auditing. See also [**SeCaptureSubjectContextEx**](nf-ntifs-secapturesubjectcontextex.md).

## -parameters

### -param SubjectContext [out]

Pointer to a caller-allocated [**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess) structure.

## -remarks

You must call **SeCaptureSubjectContext** before performing services such as access validation or generating audit messages. This is necessary to provide a consistent security context to routines such as the following:

* [**SeQueryAuthenticationIdToken**](nf-ntifs-sequeryauthenticationidtoken.md)
* [**SeQuerySubjectContextToken**](nf-ntifs-sequerysubjectcontexttoken.md)
* [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)
* [**SePrivilegeCheck**](nf-ntifs-seprivilegecheck.md)

After access validation, privilege checking, and audit generation services have been performed, release the captured context as soon as possible by calling [**SeReleaseSubjectContext**](nf-ntifs-sereleasesubjectcontext.md).

 **SeCaptureSubjectContext** locks tokens as necessary while taking the snapshot of the calling thread's security context.

On return, references to access tokens are contained in the structure that **SubjectContext** points to. The contents of that structure can change. To prevent this, call [**SeLockSubjectContext**](nf-ntifs-selocksubjectcontext.md) to lock the primary access token and any impersonation tokens associated with the structure. For example, when using routines that query token information more than once in the same security context (such as the ones previously listed), lock the subject context with **SeLockSubjectContext** to obtain consistent results.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Microsoft Windows SDK.

## -see-also

[**SeCaptureSubjectContextEx**](nf-ntifs-secapturesubjectcontextex.md)

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess)

[**SeLockSubjectContext**](nf-ntifs-selocksubjectcontext.md)

[**SePrivilegeCheck**](nf-ntifs-seprivilegecheck.md)

[**SeQueryAuthenticationIdToken**](nf-ntifs-sequeryauthenticationidtoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**SeQuerySubjectContextToken**](nf-ntifs-sequerysubjectcontexttoken.md)

[**SeReleaseSubjectContext**](nf-ntifs-sereleasesubjectcontext.md)

[**SeUnlockSubjectContext**](nf-ntifs-seunlocksubjectcontext.md)
