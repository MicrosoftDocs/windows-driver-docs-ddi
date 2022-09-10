---
UID: NS:ntifs._TOKEN_DEFAULT_DACL
title: TOKEN_DEFAULT_DACL (ntifs.h)
description: The TOKEN_DEFAULT_DACL structure specifies a discretionary access-control list (DACL).
old-location: ifsk\token_default_dacl.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["TOKEN_DEFAULT_DACL structure"]
ms.keywords: "*PTOKEN_DEFAULT_DACL, PTOKEN_DEFAULT_DACL, PTOKEN_DEFAULT_DACL structure pointer [Installable File System Drivers], TOKEN_DEFAULT_DACL, TOKEN_DEFAULT_DACL structure [Installable File System Drivers], _TOKEN_DEFAULT_DACL, ifsk.token_default_dacl, ntifs/PTOKEN_DEFAULT_DACL, ntifs/TOKEN_DEFAULT_DACL, securitystructures_a79d9155-eff5-457f-8036-c3d718b36c4e.xml"
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
req.typenames: TOKEN_DEFAULT_DACL, *PTOKEN_DEFAULT_DACL
f1_keywords:
 - _TOKEN_DEFAULT_DACL
 - ntifs/_TOKEN_DEFAULT_DACL
 - PTOKEN_DEFAULT_DACL
 - ntifs/PTOKEN_DEFAULT_DACL
 - TOKEN_DEFAULT_DACL
 - ntifs/TOKEN_DEFAULT_DACL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_DEFAULT_DACL
 - PTOKEN_DEFAULT_DACL
 - TOKEN_DEFAULT_DACL
---

# TOKEN_DEFAULT_DACL structure

## -description

The TOKEN_DEFAULT_DACL structure specifies a discretionary access-control list (DACL).

## -struct-fields

### -field DefaultDacl

Pointer to an access control list (ACL) structure assigned by default to any objects created by the user represented by the access token.

## -remarks

The **SeQueryInformationToken** support routine retrieves the default DACL for an access token, in the form of a TOKEN_DEFAULT_DACL structure.

## -see-also

[**ACL**](../wdm/ns-wdm-_acl.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md)

[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)
