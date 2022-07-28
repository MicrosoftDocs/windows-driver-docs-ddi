---
UID: NS:ntifs._SE_TOKEN_USER
title: SE_TOKEN_USER (ntifs.h)
description: The SE_TOKEN_USER structure holds the maximum-sized valid user SID that can be returned by SeQueryInformationToken, GetTokenInformation, or ZwQueryInformationToken with the TokenUser information class. This structure is suitable for stack allocation.
old-location: ifsk\se_token_user.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["SE_TOKEN_USER structure"]
ms.keywords: PSE_TOKEN_USER, PSE_TOKEN_USER structure pointer [Installable File System Drivers], SE_TOKEN_USER, SE_TOKEN_USER structure [Installable File System Drivers], _SE_TOKEN_USER, ifsk.se_token_user, ntifs/PSE_TOKEN_USER, ntifs/SE_TOKEN_USER
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
targetos: Windows
req.typenames: SE_TOKEN_USER, PSE_TOKEN_USER
f1_keywords:
 - _SE_TOKEN_USER
 - ntifs/_SE_TOKEN_USER
 - SE_TOKEN_USER
 - ntifs/SE_TOKEN_USER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SE_TOKEN_USER
 - SE_TOKEN_USER
---

# SE_TOKEN_USER structure

## -description

The **SE_TOKEN_USER** structure holds the maximum-sized valid user SID that can be returned by [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md), [**GetTokenInformation**](/windows/win32/api/securitybaseapi/nf-securitybaseapi-gettokeninformation), or [**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md) with the **TokenUser** information class. This structure is suitable for stack allocation.

## -struct-fields

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.TokenUser

Specifies a **TOKEN_USER** structure representing the user associated with an access token.

### -field DUMMYUNIONNAME.User

Specifies an **SID_AND_ATTRIBUTES** structure representing the user associated with the access token.

### -field DUMMYUNIONNAME2

### -field DUMMYUNIONNAME2.Sid

Specifies a **Security Identifier (SID)** structure used to uniquely identify users or groups

### -field DUMMYUNIONNAME2.Buffer

Specifies an array of SECURITY_MAX_SID_SIZE for allocating enough memory for the largest possible SID size.

## -see-also

[**SID**](ns-ntifs-_sid.md)

[**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md)

[**TOKEN_USER**](ns-ntifs-_token_user.md)
