---
UID: NF:ntifs.SeQuerySubjectContextToken
title: SeQuerySubjectContextToken macro
author: windows-driver-content
description: The SeQuerySubjectContextToken macro retrieves the access token for a security subject context.
old-location: ifsk\sequerysubjectcontexttoken.htm
old-project: ifsk
ms.assetid: af326cb1-446a-49b7-a381-472deb9ecc82
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeQuerySubjectContextToken, SeQuerySubjectContextToken function [Installable File System Drivers], ifsk.sequerysubjectcontexttoken, ntifs/SeQuerySubjectContextToken, seref_5b274dd0-4f8e-4f4c-b7ff-9de9b3da9213.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	SeQuerySubjectContextToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeQuerySubjectContextToken macro


## -description


The <b>SeQuerySubjectContextToken</b> macro retrieves the access token for a security subject context.


## -syntax


````
PACCESS_TOKEN SeQuerySubjectContextToken(
  _In_ PSECURITY_SUBJECT_CONTEXT SubjectContext
);
````


## -parameters




### -param SubjectContext [in]

Pointer to the subject context to query.


## -remarks



The access token pointer returned by <b>SeQuerySubjectContextToken</b> can be passed to <b>SeQueryInformationToken</b>. 

<b>SeQuerySubjectContextToken</b> does not affect the lock status or access token of the subject context.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\ntifs\nf-ntifs-psdereferenceprimarytoken.md">PsDereferencePrimaryToken</a>



<a href="..\ntifs\nf-ntifs-setokenisadmin.md">SeTokenIsAdmin</a>



<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>



<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-psdereferenceimpersonationtoken.md">PsDereferenceImpersonationToken</a>



<a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



 

 


