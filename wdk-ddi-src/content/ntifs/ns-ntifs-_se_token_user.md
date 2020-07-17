---
UID: NS:ntifs._SE_TOKEN_USER
title: _SE_TOKEN_USER (ntifs.h)
description: The SE_TOKEN_USER structure holds the maximum-sized valid user SID that can be returned by SeQueryInformationToken, GetTokenInformation, or ZwQueryInformationToken with the TokenUser information class. This structure is suitable for stack allocation.
old-location: ifsk\se_token_user.htm
tech.root: ifsk
ms.assetid: 3B870461-0C5D-46DF-A850-EB796AE5A4CB
ms.date: 04/16/2018
keywords: ["_SE_TOKEN_USER structure"]
ms.keywords: PSE_TOKEN_USER, PSE_TOKEN_USER structure pointer [Installable File System Drivers], SE_TOKEN_USER, SE_TOKEN_USER structure [Installable File System Drivers], _SE_TOKEN_USER, ifsk.se_token_user, ntifs/PSE_TOKEN_USER, ntifs/SE_TOKEN_USER
f1_keywords:
 - "ntifs/SE_TOKEN_USER"
 - "SE_TOKEN_USER"
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- SE_TOKEN_USER
product:
- Windows
targetos: Windows
req.typenames: SE_TOKEN_USER, PSE_TOKEN_USER
---

# _SE_TOKEN_USER structure


## -description


The <b>SE_TOKEN_USER</b> structure holds the maximum-sized valid user SID that can be returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>, <a href="https://docs.microsoft.com/windows/desktop/api/securitybaseapi/nf-securitybaseapi-gettokeninformation">GetTokenInformation</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a> with the TokenUser information class. This structure is suitable for stack allocation.


## -struct-fields




### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.TokenUser

Specifies a <b>TOKEN_USER</b> structure representing the user associated with an access token.


### -field DUMMYUNIONNAME.User

Specifies an <b>SID_AND_ATTRIBUTES</b> structure representing the user associated with the access token.


### -field DUMMYUNIONNAME2

 


### -field DUMMYUNIONNAME2.Sid

Specifies a <b>Security Identifier (SID)</b> structure used to uniquely identify users or groups


### -field DUMMYUNIONNAME2.Buffer

Specifies an array of SECURITY_MAX_SID_SIZE for allocating enough memory for the largest possible SID size.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid_and_attributes">SID_AND_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_user">TOKEN_USER</a>
 

 

