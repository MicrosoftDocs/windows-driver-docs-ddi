---
UID: NF:ntifs.SeReleaseSubjectContext
title: SeReleaseSubjectContext function (ntifs.h)
description: Learn more about the SeReleaseSubjectContext routine.
old-location: ifsk\sereleasesubjectcontext.htm
tech.root: ifsk
ms.date: 02/21/2013
keywords: ["SeReleaseSubjectContext function"]
ms.keywords: SeReleaseSubjectContext, SeReleaseSubjectContext routine [Installable File System Drivers], ifsk.sereleasesubjectcontext, ntifs/SeReleaseSubjectContext, seref_f46fe5d3-13d1-4907-85b4-47eb78116fe0.xml
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
 - SeReleaseSubjectContext
 - ntifs/SeReleaseSubjectContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeReleaseSubjectContext
---

# SeReleaseSubjectContext function (ntifs.h)

## -description

The **SeReleaseSubjectContext** routine releases a subject security context captured by an earlier call to **SeCaptureSubjectContext**.

## -parameters

### -param SubjectContext [in, out]

Pointer to the captured security context.

## -remarks

File systems must call **SeCaptureSubjectContext** before performing access validation or generating audit messages. This is necessary to provide a consistent security context to routines such as **SeQueryAuthenticationIdToken**, **SeQuerySubjectContextToken**, and **SePrivilegeCheck**. After these operations have been performed, the captured context should be released as soon as possible by calling **SeReleaseSubjectContext**.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context)

[**SeCaptureSubjectContext**](nf-ntifs-secapturesubjectcontext.md)

[**SeCaptureSubjectContextEx**](nf-ntifs-secapturesubjectcontextex.md)

[**SeLockSubjectContext**](nf-ntifs-selocksubjectcontext.md)

[**SePrivilegeCheck**](nf-ntifs-seprivilegecheck.md)

[**SeQueryAuthenticationIdToken**](nf-ntifs-sequeryauthenticationidtoken.md)

[**SeQuerySubjectContextToken**](nf-ntifs-sequerysubjectcontexttoken.md)

[**SeUnlockSubjectContext**](nf-ntifs-seunlocksubjectcontext.md)
