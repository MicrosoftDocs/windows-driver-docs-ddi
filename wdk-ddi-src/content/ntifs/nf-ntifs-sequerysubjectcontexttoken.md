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
req.lib: ntifs.h
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



<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>



<a href="..\ntifs\nf-ntifs-psdereferenceimpersonationtoken.md">PsDereferenceImpersonationToken</a>



<a href="..\ntifs\nf-ntifs-setokenisadmin.md">SeTokenIsAdmin</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeQuerySubjectContextToken function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

