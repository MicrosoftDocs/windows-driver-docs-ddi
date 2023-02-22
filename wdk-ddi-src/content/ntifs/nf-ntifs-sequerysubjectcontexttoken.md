---
UID: NF:ntifs.SeQuerySubjectContextToken
title: SeQuerySubjectContextToken macro (ntifs.h)
description: Learn more about the SeQuerySubjectContextToken macro.
tech.root: ifsk
ms.date: 02/21/2023
keywords: ["SeQuerySubjectContextToken macro"]
ms.keywords: SeQuerySubjectContextToken, SeQuerySubjectContextToken function [Installable File System Drivers], ifsk.sequerysubjectcontexttoken, ntifs/SeQuerySubjectContextToken, seref_5b274dd0-4f8e-4f4c-b7ff-9de9b3da9213.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SeQuerySubjectContextToken
 - ntifs/SeQuerySubjectContextToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - SeQuerySubjectContextToken
---

# SeQuerySubjectContextToken macro

## -description

The **SeQuerySubjectContextToken** macro retrieves the access token for a security subject context.

## -syntax

```cpp
PACESS_TOKEN
SeQuerySubjectContextToken(SubjectContext);
```

## -parameters

### -param SubjectContext [in]

Pointer to an opaque [**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context) structure containing the subject context to query. This opaque structure was obtained from the operating system in a call to [**SeCaptureSubjectContextEx**](nf-ntifs-secapturesubjectcontextex.md)
 or [**SeCaptureSubjectContext**](nf-ntifs-secapturesubjectcontext.md). Drivers must not modify or try to directly access any members of this structure to make security decisions.

## -returns

**SeQuerySubjectContextToken** returns the effective token from **SubjectContext**. The effective token is the client token, if present; otherwise it is the primary (process) token.

## -remarks

**SeQuerySubjectContextToken** can return either a primary or impersonation token. Since drivers must not directly access any members of the [**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context) structure, you should first pass it to [**SeAccessCheck**](../wdm/nf-wdm-seaccesscheck.md) or [**SePrivilegeCheck**](nf-ntifs-seprivilegecheck.md) to avoid security issues in authorization; for example, if this is an impersonation token, it requires an impersonation level of **SecurityImpersonation** or higher. Once you've confirmed authorization status, you can then pass the access token pointer returned by **SeQuerySubjectContextToken** to [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md).

**SeQuerySubjectContextToken** does not affect the lock status or access token of the subject context.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**PsDereferenceImpersonationToken**](nf-ntifs-psdereferenceimpersonationtoken.md)

[**PsDereferencePrimaryToken**](nf-ntifs-psdereferenceprimarytoken.md)

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context)

[**SeQueryAuthenticationIdToken**](nf-ntifs-sequeryauthenticationidtoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**SeTokenIsAdmin**](nf-ntifs-setokenisadmin.md)

[**SeTokenIsRestricted**](nf-ntifs-setokenisrestricted.md)
