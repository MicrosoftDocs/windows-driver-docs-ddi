---
UID: NF:ntifs.SeLockSubjectContext
title: SeLockSubjectContext function (ntifs.h)
description: Learn more about the SeLockSubjectContext function.
old-location: ifsk\selocksubjectcontext.htm
tech.root: ifsk
ms.date: 02/13/2023
keywords: ["SeLockSubjectContext function"]
ms.keywords: SeLockSubjectContext, SeLockSubjectContext routine [Installable File System Drivers], ifsk.selocksubjectcontext, ntifs/SeLockSubjectContext, seref_ea4696ab-8343-4d15-866c-15720d009db8.xml
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
 - SeLockSubjectContext
 - ntifs/SeLockSubjectContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeLockSubjectContext
---

# SeLockSubjectContext function (ntifs.h)

## -description

The **SeLockSubjectContext** routine locks the primary and impersonation tokens of a captured subject context.

## -parameters

### -param SubjectContext [in]

Pointer to the [**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess) structure. This opaque structure is obtained from the operating system in a call to [**SeCaptureSubjectContextEx**](nf-ntifs-secapturesubjectcontextex.md)
 or [**SeCaptureSubjectContext**](nf-ntifs-secapturesubjectcontext.md).

## -remarks

**SeLockSubjectContext** acquires read locks on the primary and impersonation tokens of a captured subject context. Each call to **SeLockSubjectContext** must be matched by a subsequent call to [**SeUnlockSubjectContext**](nf-ntifs-seunlocksubjectcontext.md).

To capture a subject context, use [**SeCaptureSubjectContextEx**](nf-ntifs-secapturesubjectcontextex.md)
 or [**SeCaptureSubjectContext**](nf-ntifs-secapturesubjectcontext.md).

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Microsoft Windows SDK.

## -see-also

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess)

[**SeCaptureSubjectContextEx**](nf-ntifs-secapturesubjectcontextex.md)

[**SeUnlockSubjectContext**](nf-ntifs-seunlocksubjectcontext.md)
