---
UID: NS:ntifs._TOKEN_GROUPS
title: TOKEN_GROUPS (ntifs.h)
description: TOKEN_GROUPS contains information about the group security identifiers (SID) in an access token.
old-location: ifsk\token_groups.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["TOKEN_GROUPS structure"]
ms.keywords: "*PTOKEN_GROUPS, PTOKEN_GROUPS, PTOKEN_GROUPS structure pointer [Installable File System Drivers], TOKEN_GROUPS, TOKEN_GROUPS structure [Installable File System Drivers], _TOKEN_GROUPS, ifsk.token_groups, ntifs/PTOKEN_GROUPS, ntifs/TOKEN_GROUPS, securitystructures_97d0491f-87b4-4e76-8252-fad37cc94c1c.xml"
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
req.typenames: TOKEN_GROUPS, *PTOKEN_GROUPS
f1_keywords:
 - _TOKEN_GROUPS
 - ntifs/_TOKEN_GROUPS
 - PTOKEN_GROUPS
 - ntifs/PTOKEN_GROUPS
 - TOKEN_GROUPS
 - ntifs/TOKEN_GROUPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_GROUPS
 - PTOKEN_GROUPS
 - TOKEN_GROUPS
---

# TOKEN_GROUPS structure

## -description

TOKEN_GROUPS contains information about the group security identifiers (SID) in an access token.

## -struct-fields

### -field GroupCount

Specifies the number of groups in the access token.

### -field Groups

Specifies an array of [**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md) structures containing a set of SIDs and corresponding attributes.

## -remarks

You can use [**SeFilterToken**](nf-ntifs-sefiltertoken.md) to designate one or more group SIDs as deny-only SIDs. Note that it is also possible to designate a user SID as a deny-only SID by specifying the user SID as one of the group SIDs in the **TOKEN_GROUPS** structure passed to **SeFilterToken**.

## -see-also

[**SID**](ns-ntifs-_sid.md)

[**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md)

[**SeFilterToken**](nf-ntifs-sefiltertoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md)

[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)
