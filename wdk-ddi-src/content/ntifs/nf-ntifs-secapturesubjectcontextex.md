---
UID: NF:ntifs.SeCaptureSubjectContextEx
tech.root: ifsk
title: SeCaptureSubjectContextEx
ms.date: 02/09/2023
targetos: Windows
description: Learn more about the SeCaptureSubjectContextEx function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntifs.h
api_name:
 - SeCaptureSubjectContextEx
f1_keywords:
 - SeCaptureSubjectContextEx
 - ntifs/SeCaptureSubjectContextEx
dev_langs:
 - c++
helpviewer_keywords:
 - SeCaptureSubjectContextEx
---

## -description

**SeCaptureSubjectContextEx** takes a snapshot of the calling thread's security context for access validation and auditing.

## -parameters

### -param Thread

[in] The thread from which to capture the thread token. This parameter is optional. When it's NULL, **SeCaptureSubjectContextEx** doesn't capture an impersonation token.

### -param Process

 [in] Pointer to the [ID of the process](/windows-hardware/drivers/kernel/eprocess) from which to capture the primary token.

### -param SubjectContext

[out] Pointer to a caller-allocated [**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess) structure in **SeCaptureSubjectContextEx** will write the snapshot of the calling thread's security profile, which contains references to access tokens.

## -remarks

 You must call **SeCaptureSubjectContextEx** before performing services such as access validation or generating audit messages. This is necessary to provide a consistent security context to routines such as the following:

* [**SeQueryAuthenticationIdToken**](nf-ntifs-sequeryauthenticationidtoken.md)
* [**SeQuerySubjectContextToken**](nf-ntifs-sequerysubjectcontexttoken.md)
* [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)
* [**SePrivilegeCheck**](nf-ntifs-seprivilegecheck.md)

After access validation, privilege checking, and audit generation services have been performed, release the captured context as soon as possible by calling [**SeReleaseSubjectContext**](nf-ntifs-sereleasesubjectcontext.md).

 **SeCaptureSubjectContextEx** locks tokens as necessary while taking the snapshot of the calling thread's security context.

On return, references to access tokens are contained in the structure that **SubjectContext** points to. The contents of that structure can change. To prevent this, call [**SeLockSubjectContext**](nf-ntifs-selocksubjectcontext.md) to lock the primary access token and any impersonation tokens associated with the structure. For example, when using routines that query token information more than once in the same security context (such as the ones previously listed), lock the subject context with **SeLockSubjectContext** to obtain consistent results.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Microsoft Windows SDK.

## -see-also

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess)

[**SeLockSubjectContext**](nf-ntifs-selocksubjectcontext.md)

[**SePrivilegeCheck**](nf-ntifs-seprivilegecheck.md)

[**SeQueryAuthenticationIdToken**](nf-ntifs-sequeryauthenticationidtoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**SeQuerySubjectContextToken**](nf-ntifs-sequerysubjectcontexttoken.md)

[**SeReleaseSubjectContext**](nf-ntifs-sereleasesubjectcontext.md)

[**SeUnlockSubjectContext**](nf-ntifs-seunlocksubjectcontext.md)
