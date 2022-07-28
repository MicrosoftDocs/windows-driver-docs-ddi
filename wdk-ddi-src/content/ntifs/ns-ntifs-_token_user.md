---
UID: NS:ntifs._TOKEN_USER
title: TOKEN_USER (ntifs.h)
description: TOKEN_USER identifies the user associated with an access token.
old-location: ifsk\token_user.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["TOKEN_USER structure"]
ms.keywords: "*PTOKEN_USER, PTOKEN_USER, PTOKEN_USER structure pointer [Installable File System Drivers], TOKEN_USER, TOKEN_USER structure [Installable File System Drivers], _TOKEN_USER, ifsk.token_user, ntifs/PTOKEN_USER, ntifs/TOKEN_USER, securitystructures_0e952505-1e51-463e-ba92-c6995e6f107a.xml"
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.typenames: TOKEN_USER, *PTOKEN_USER
f1_keywords:
 - _TOKEN_USER
 - ntifs/_TOKEN_USER
 - PTOKEN_USER
 - ntifs/PTOKEN_USER
 - TOKEN_USER
 - ntifs/TOKEN_USER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_USER
 - PTOKEN_USER
 - TOKEN_USER
---

# TOKEN_USER structure

## -description

The **TOKEN_USER** structure identifies the user associated with an access token.

## -struct-fields

### -field User

Specifies an [**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md) structure representing the user associated with the access token.

## -remarks

Unlike TOKEN_GROUPS structures, TOKEN_USER structures cannot be passed to **SeFilterToken**. Nevertheless, it is possible to designate a user SID as a deny-only SID by specifying the user SID as one of the group SIDs in the TOKEN_GROUPS structure passed to **SeFilterToken**.

## -see-also

[**SID**](ns-ntifs-_sid.md)

[**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md)

[**SeFilterToken**](nf-ntifs-sefiltertoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**TOKEN_GROUPS**](ns-ntifs-_token_groups.md)

[**TOKEN_INFORMATION_CLASS**](ne-ntifs-_token_information_class.md)

[**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md)

[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)
