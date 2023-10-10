---
UID: NS:ntifs._SID
title: SID (ntifs.h)
description: The security identifier (SID) structure is a variable-length structure used to uniquely identify users or groups.
old-location: ifsk\sid.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["SID structure"]
ms.keywords: "*PISID, PSID, PSID structure pointer [Installable File System Drivers], SID, SID structure [Installable File System Drivers], _SID, ifsk.sid, ntifs/PSID, ntifs/SID, securitystructures_748be9da-f428-42cd-a1f8-eca090e2b3aa.xml"
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
req.typenames: SID, *PISID
f1_keywords:
 - _SID
 - ntifs/_SID
 - PISID
 - ntifs/PISID
 - SID
 - ntifs/SID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SID
 - PISID
 - SID
---

# SID structure

## -description

The security identifier (SID) structure is a variable-length structure used to uniquely identify users or groups.

Drivers must not modify the SID structure directly. To create and manipulate a security identifier, use the support routines listed in the See Also section.

## -struct-fields

### -field Revision

The revision level assigned to the SID.

### -field SubAuthorityCount

Number of subauthorities in the SID.

### -field IdentifierAuthority

A [**SID_IDENTIFIER_AUTHORITY**](ns-ntifs-_sid_identifier_authority.md) structure that represents the top-level authority of the SID.

### -field SubAuthority[*]

The subauthority of the SID.

### -field SubAuthority[ANYSIZE_ARRAY]

The subauthority of the SID.

## -see-also

[**RtlCopySid**](nf-ntifs-rtlcopysid.md)

[**RtlEqualPrefixSid**](nf-ntifs-rtlequalprefixsid.md)

[**RtlEqualSid**](nf-ntifs-rtlequalsid.md)

[**RtlGetOwnerSecurityDescriptor**](nf-ntifs-rtlgetownersecuritydescriptor.md)

[**RtlInitializeSid**](nf-ntifs-rtlinitializesid.md)

[**RtlLengthSid**](nf-ntifs-rtllengthsid.md)

[**RtlSetOwnerSecurityDescriptor**](nf-ntifs-rtlsetownersecuritydescriptor.md)

[**RtlSubAuthoritySid**](nf-ntifs-rtlsubauthoritysid.md)

[**RtlValidSid**](nf-ntifs-rtlvalidsid.md)

[**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md)

[**SID_IDENTIFIER_AUTHORITY**](ns-ntifs-_sid_identifier_authority.md)
