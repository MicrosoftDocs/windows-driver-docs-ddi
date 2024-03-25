---
UID: NF:ntifs.SeCreateClientSecurity
title: SeCreateClientSecurity function (ntifs.h)
description: Learn more about the SeCreateClientSecurity function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["SeCreateClientSecurity function"]
ms.keywords: SeCreateClientSecurity, SeCreateClientSecurity routine [Installable File System Drivers], ifsk.secreateclientsecurity, ntifs/SeCreateClientSecurity, seref_3b2ae680-788b-4ecb-b747-427f8fd3b4bf.xml
req.header: ntifs.h
req.include-header: Ntifs.h
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
 - SeCreateClientSecurity
 - ntifs/SeCreateClientSecurity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeCreateClientSecurity
---

# SeCreateClientSecurity function

## -description

The **SeCreateClientSecurity** routine initializes a security client context structure with the information needed to call **SeImpersonateClientEx**.

## -parameters

### -param ClientThread [in]

Pointer to the thread of the client to be impersonated.

### -param ClientSecurityQos [in]

Pointer to a caller-allocated SECURITY_QUALITY_OF_SERVICE structure indicating what form of impersonation is to be performed.

### -param RemoteSession

Set to TRUE if the server of the client's request is remote.

### -param ClientContext [out]

Pointer to a caller-allocated SECURITY_CLIENT_CONTEXT structure to be initialized.

## -returns

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The security client context was successfully initialized. |
| STATUS_BAD_IMPERSONATION_LEVEL | The client to be impersonated is currently impersonating a client of its own, and one of the following is true: (1) The client's effective token cannot be passed on for use by another server, because its impersonation level is **SecurityAnonymous** or **SecurityIdentification**. (2) **ServerIsRemote** is TRUE, and the client thread is impersonating its client at other than **SecurityDelegation** level. |

## -remarks

**SeCreateClientSecurity** initializes a client security context block to represent a client's security context.

If the **ContextTrackingMode** member of **ClientSecurityQos** is set to SECURITY_DYNAMIC_TRACKING and **ServerIsRemote** is set to FALSE, **SeCreateClientSecurity** uses a reference to the client's effective token. Otherwise, **SeCreateClientSecurity** creates a copy of the client's token.

Each call to **SeCreateClientSecurity** must be matched by a subsequent call to **SeDeleteClientSecurity**.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**SeDeleteClientSecurity**](nf-ntifs-sedeleteclientsecurity.md)

[**SeImpersonateClientEx**](nf-ntifs-seimpersonateclientex.md)
