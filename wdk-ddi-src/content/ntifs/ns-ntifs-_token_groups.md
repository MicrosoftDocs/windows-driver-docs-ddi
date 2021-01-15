---
UID: NS:ntifs._TOKEN_GROUPS
title: _TOKEN_GROUPS (ntifs.h)
description: TOKEN_GROUPS contains information about the group security identifiers (SID) in an access token.
old-location: ifsk\token_groups.htm
tech.root: ifsk
ms.date: 04/16/2018
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

# _TOKEN_GROUPS structure


## -description

TOKEN_GROUPS contains information about the group security identifiers (SID) in an access token.

## -struct-fields

### -field GroupCount

Specifies the number of groups in the access token.

### -field Groups.size_is

### -field Groups.size_is.GroupCount

### -field Groups

Specifies an array of <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid_and_attributes">SID_AND_ATTRIBUTES</a> structures containing a set of SIDs and corresponding attributes.

## -remarks

You can use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sefiltertoken">SeFilterToken</a> to designate one or more group SIDs as deny-only SIDs. Note that it is also possible to designate a user SID as a deny-only SID by specifying the user SID as one of the group SIDs in the <b>TOKEN_GROUPS</b> structure passed to <b>SeFilterToken</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid_and_attributes">SID_AND_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sefiltertoken">SeFilterToken</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="/previous-versions/ff567055(v=vs.85)">ZwQueryInformationToken</a>



<a href="/previous-versions/ff567102(v=vs.85)">ZwSetInformationToken</a>

