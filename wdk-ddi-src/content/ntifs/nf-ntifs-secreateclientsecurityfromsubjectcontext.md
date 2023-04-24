---
UID: NF:ntifs.SeCreateClientSecurityFromSubjectContext
title: SeCreateClientSecurityFromSubjectContext function (ntifs.h)
description: Learn more about the SeCreateClientSecurityFromSubjectContext routine.
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["SeCreateClientSecurityFromSubjectContext function"]
ms.keywords: SeCreateClientSecurityFromSubjectContext, SeCreateClientSecurityFromSubjectContext routine [Installable File System Drivers], ifsk.secreateclientsecurityfromsubjectcontext, ntifs/SeCreateClientSecurityFromSubjectContext, seref_fac27935-a941-48f6-a27b-7ca56bd1f9e2.xml
req.header: ntifs.h
req.include-header: Ntifs.h
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
 - SeCreateClientSecurityFromSubjectContext
 - ntifs/SeCreateClientSecurityFromSubjectContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeCreateClientSecurityFromSubjectContext
---

# SeCreateClientSecurityFromSubjectContext function

## -description

The **SeCreateClientSecurityFromSubjectContext** routine retrieves the access token for a security subject context and uses the result to initialize a security client context with the information needed to call **SeImpersonateClientEx**.

## -parameters

### -param SubjectContext [in]

Pointer to the security subject context of the client to be impersonated.

### -param ClientSecurityQos [in]

Pointer to a caller-allocated SECURITY_QUALITY_OF_SERVICE structure indicating what form of impersonation is to be performed.

### -param ServerIsRemote [in]

Set to TRUE if the server of the client's request is remote.

### -param ClientContext [out]

Pointer to a caller-allocated SECURITY_CLIENT_CONTEXT structure to be initialized.

## -returns

**SeCreateClientSecurityFromSubjectContext** returns STATUS_SUCCESS when it successfully initializes the security client context.

It returns STATUS_BAD_IMPERSONATION_LEVEL when the client to be impersonated is currently impersonating a client of its own, and one of the following is true:

* The client's effective token cannot be passed on for use by another server, because its impersonation level is **SecurityAnonymous** or **SecurityIdentification**.

* **ServerIsRemote** is TRUE, and the client thread is impersonating its client at other than **SecurityDelegation** level.

## -remarks

**SeCreateClientSecurityFromSubjectContext** initializes a client security context block to represent a client's security context.

If the **ContextTrackingMode** member of **ClientSecurityQos** is set to SECURITY_DYNAMIC_TRACKING and **ServerIsRemote** is set to **FALSE**, **SeCreateClientSecurityFromSubjectContext** uses a reference to the client's effective token. Otherwise, **SeCreateClientSecurityFromSubjectContext** creates a copy of the client's token.

Each call to **SeCreateClientSecurityFromSubjectContext** must be matched by a subsequent call to **SeDeleteClientSecurity**.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**SECURITY_SUBJECT_CONTEXT**/(/windows-hardware/drivers/kernel/eprocess##security_subject_context)

[**SeDeleteClientSecurity**/(nf-ntifs-sedeleteclientsecurity.md)

[**SeImpersonateClientEx**/(nf-ntifs-seimpersonateclientex.md)
