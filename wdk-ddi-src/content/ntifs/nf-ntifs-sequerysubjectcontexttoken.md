---
UID: NF:ntifs.SeQuerySubjectContextToken
title: SeQuerySubjectContextToken macro (ntifs.h)
description: The SeQuerySubjectContextToken macro retrieves the access token for a security subject context.
old-location: ifsk\sequerysubjectcontexttoken.htm
tech.root: ifsk
ms.date: 02/25/2021
keywords: ["SeQuerySubjectContextToken macro"]
ms.keywords: SeQuerySubjectContextToken, SeQuerySubjectContextToken function [Installable File System Drivers], ifsk.sequerysubjectcontexttoken, ntifs/SeQuerySubjectContextToken, seref_5b274dd0-4f8e-4f4c-b7ff-9de9b3da9213.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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

## -parameters

### -param SubjectContext

[in] Pointer to a [**SECURITY_SUBJECT_CONTEXT**](../wdm/ns-wdm-_security_subject_context.md) structure containing the subject context to query.

## -returns

**SeQuerySubjectContextToken** returns the effective token from **SubjectContext**. The effective token is the client token, if present; otherwise it is the primary (process) token.

## -remarks

The access token pointer returned by **SeQuerySubjectContextToken** can be passed to [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md).

**SeQuerySubjectContextToken** does not affect the lock status or access token of the subject context.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

[**PsDereferenceImpersonationToken**](nf-ntifs-psdereferenceimpersonationtoken.md)

[**PsDereferencePrimaryToken**](nf-ntifs-psdereferenceprimarytoken.md)

[**SECURITY_SUBJECT_CONTEXT**](../wdm/ns-wdm-_security_subject_context.md)

[**SeQueryAuthenticationIdToken**](nf-ntifs-sequeryauthenticationidtoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**SeTokenIsAdmin**](nf-ntifs-setokenisadmin.md)

[**SeTokenIsRestricted**](nf-ntifs-setokenisrestricted.md)