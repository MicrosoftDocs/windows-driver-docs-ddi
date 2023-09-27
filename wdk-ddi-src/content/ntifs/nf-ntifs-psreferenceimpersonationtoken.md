---
UID: NF:ntifs.PsReferenceImpersonationToken
title: PsReferenceImpersonationToken function (ntifs.h)
description: Learn more about the PsReferenceImpersonationToken function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["PsReferenceImpersonationToken function"]
ms.keywords: PsReferenceImpersonationToken, PsReferenceImpersonationToken routine [Installable File System Drivers], ifsk.psreferenceimpersonationtoken, ntifs/PsReferenceImpersonationToken, psref_150f4e7c-56c2-4108-b5c9-0882f9027252.xml
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
 - PsReferenceImpersonationToken
 - ntifs/PsReferenceImpersonationToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsReferenceImpersonationToken
---

# PsReferenceImpersonationToken function

## -description

The **PsReferenceImpersonationToken** routine increments the reference count of the impersonation token for the specified thread.

## -parameters

### -param Thread [in, out]

Address of the thread whose impersonation token's reference count is to be incremented.

### -param CopyOnOpen [out]

Pointer to a caller-allocated Boolean variable. On return, this parameter receives TRUE if the token cannot be opened directly. In this case, the token must be duplicated, and the duplicate token must be used instead. If the token can be opened directly, this parameter receives FALSE.

### -param EffectiveOnly [out]

Pointer to a caller-allocated Boolean variable. On return, this parameter receives FALSE if the thread is allowed to enable groups and privileges that are currently disabled in the client security context, TRUE otherwise.

### -param ImpersonationLevel [out]

Pointer to a caller-allocated SECURITY_IMPERSONATION_LEVEL variable. On return, this parameter receives a value that specifies the impersonation level at which the thread is allowed to access the token.

## -returns

**PsReferenceImpersonationToken** returns a pointer to the impersonation token for the given thread. If the thread is not currently impersonating a client, a NULL pointer is returned.

## -remarks

If the thread is currently impersonating a client, **PsReferenceImpersonationToken** increments the reference count of the impersonation token and returns a pointer to the token. If the returned pointer is non-**NULL**, the impersonation token's reference count must be decremented by calling one of the following functions:

* **ObDereferenceObject**, for Windows 2000
* **PsDereferenceImpersonationToken**, for Microsoft Windows XP or later

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)

[**PsDereferenceImpersonationToken**](nf-ntifs-psdereferenceimpersonationtoken.md)

[**PsImpersonateClient**](nf-ntifs-psimpersonateclient.md)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)
