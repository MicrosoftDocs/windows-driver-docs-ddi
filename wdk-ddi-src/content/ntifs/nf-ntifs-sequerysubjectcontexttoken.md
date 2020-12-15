---
UID: NF:ntifs.SeQuerySubjectContextToken
title: SeQuerySubjectContextToken macro (ntifs.h)
description: The SeQuerySubjectContextToken macro retrieves the access token for a security subject context.
old-location: ifsk\sequerysubjectcontexttoken.htm
tech.root: ifsk
ms.date: 04/16/2018
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

The <b>SeQuerySubjectContextToken</b> macro retrieves the access token for a security subject context.

## -parameters

### -param SubjectContext 

[in]
Pointer to the subject context to query.

## -remarks

The access token pointer returned by <b>SeQuerySubjectContextToken</b> can be passed to <b>SeQueryInformationToken</b>. 

<b>SeQuerySubjectContextToken</b> does not affect the lock status or access token of the subject context.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psdereferenceimpersonationtoken">PsDereferenceImpersonationToken</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psdereferenceprimarytoken">PsDereferencePrimaryToken</a>



<a href="/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryauthenticationidtoken">SeQueryAuthenticationIdToken</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokenisadmin">SeTokenIsAdmin</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokenisrestricted">SeTokenIsRestricted</a>
