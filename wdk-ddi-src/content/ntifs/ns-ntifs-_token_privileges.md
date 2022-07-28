---
UID: NS:ntifs._TOKEN_PRIVILEGES
title: TOKEN_PRIVILEGES (ntifs.h)
description: TOKEN_PRIVILEGES contains information about a set of privileges for an access token.
old-location: ifsk\token_privileges.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["TOKEN_PRIVILEGES structure"]
ms.keywords: "*PTOKEN_PRIVILEGES, PTOKEN_PRIVILEGES, PTOKEN_PRIVILEGES structure pointer [Installable File System Drivers], TOKEN_PRIVILEGES, TOKEN_PRIVILEGES structure [Installable File System Drivers], _TOKEN_PRIVILEGES, ifsk.token_privileges, ntifs/PTOKEN_PRIVILEGES, ntifs/TOKEN_PRIVILEGES, securitystructures_3da1d9ba-6fa7-4b16-bdd7-416890b57f7e.xml"
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
req.typenames: TOKEN_PRIVILEGES, *PTOKEN_PRIVILEGES
f1_keywords:
 - _TOKEN_PRIVILEGES
 - ntifs/_TOKEN_PRIVILEGES
 - PTOKEN_PRIVILEGES
 - ntifs/PTOKEN_PRIVILEGES
 - TOKEN_PRIVILEGES
 - ntifs/TOKEN_PRIVILEGES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_PRIVILEGES
 - PTOKEN_PRIVILEGES
 - TOKEN_PRIVILEGES
---

# TOKEN_PRIVILEGES structure

## -description

The **TOKEN_PRIVILEGES** structure contains information about a set of privileges for an access token.

## -struct-fields

### -field PrivilegeCount

Specifies the number of entries in the **Privileges** array.

### -field Privileges

Specifies an array of [**LUID_AND_ATTRIBUTES**](../wdm/ns-wdm-_luid_and_attributes.md) structures. Each structure contains the LUID and attributes of a privilege.

## -see-also

[**LUID**](../igpupvdev/ns-igpupvdev-_luid.md)

[**LUID_AND_ATTRIBUTES**](../wdm/ns-wdm-_luid_and_attributes.md)

[**SID**](ns-ntifs-_sid.md)

[**SeFilterToken**](nf-ntifs-sefiltertoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**TOKEN_INFORMATION_CLASS**](ne-ntifs-_token_information_class.md)

[**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md)

[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)
