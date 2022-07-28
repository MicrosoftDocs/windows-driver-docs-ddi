---
UID: NS:ntifs._TOKEN_GROUPS_AND_PRIVILEGES
title: TOKEN_GROUPS_AND_PRIVILEGES (ntifs.h)
description: TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token.
old-location: ifsk\token_groups_and_privileges.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["TOKEN_GROUPS_AND_PRIVILEGES structure"]
ms.keywords: "*PTOKEN_GROUPS_AND_PRIVILEGES, PTOKEN_GROUPS_AND_PRIVILEGES, PTOKEN_GROUPS_AND_PRIVILEGES structure pointer [Installable File System Drivers], TOKEN_GROUPS_AND_PRIVILEGES, TOKEN_GROUPS_AND_PRIVILEGES structure [Installable File System Drivers], _TOKEN_GROUPS_AND_PRIVILEGES, ifsk.token_groups_and_privileges, ntifs/PTOKEN_GROUPS_AND_PRIVILEGES, ntifs/TOKEN_GROUPS_AND_PRIVILEGES, securitystructures_4cab5ceb-66b1-4445-a9b0-a428fc628ab5.xml"
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
req.typenames: TOKEN_GROUPS_AND_PRIVILEGES, *PTOKEN_GROUPS_AND_PRIVILEGES
f1_keywords:
 - _TOKEN_GROUPS_AND_PRIVILEGES
 - ntifs/_TOKEN_GROUPS_AND_PRIVILEGES
 - PTOKEN_GROUPS_AND_PRIVILEGES
 - ntifs/PTOKEN_GROUPS_AND_PRIVILEGES
 - TOKEN_GROUPS_AND_PRIVILEGES
 - ntifs/TOKEN_GROUPS_AND_PRIVILEGES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_GROUPS_AND_PRIVILEGES
 - PTOKEN_GROUPS_AND_PRIVILEGES
 - TOKEN_GROUPS_AND_PRIVILEGES
---

# TOKEN_GROUPS_AND_PRIVILEGES structure

## -description

TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token.

## -struct-fields

### -field SidCount

Specifies the number of SIDs in the access token.

### -field SidLength

Specifies the length, in bytes, required to hold all of the user SIDs and the account SID for the group.

### -field Sids

A pointer to SID_AND_ATTRIBUTES structures that contain a set of SIDs and corresponding attributes.

### -field RestrictedSidCount

Specifies the number of the restricted SIDs included in the access token.

### -field RestrictedSidLength

Specifies the length, in bytes, required to hold all of the restricted SIDs.

### -field RestrictedSids

A pointer to [**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md) structures that contain a set of restricted SIDs and corresponding attributes.

### -field PrivilegeCount

Specifies the number of privileges included in the access token.

### -field PrivilegeLength

Specifies the length, in bytes, needed to hold all of the privileges.

### -field Privileges

A pointer to [**LUID_AND_ATTRIBUTES**](../wdm/ns-wdm-_luid_and_attributes.md) structures that contain a set of privileges.

### -field AuthenticationId

The locally unique identifier (LUID) of the authenticator of the token.

## -see-also

[**ACL**](../wdm/ns-wdm-_acl.md)

[**LUID_AND_ATTRIBUTES**](../wdm/ns-wdm-_luid_and_attributes.md)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)

[**SID**](ns-ntifs-_sid.md)

[**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md)

[**SeFilterToken**](nf-ntifs-sefiltertoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**SeTokenIsRestricted**](nf-ntifs-setokenisrestricted.md)

[**TOKEN_DEFAULT_DACL**](ns-ntifs-_token_default_dacl.md)

[**TOKEN_INFORMATION_CLASS**](ne-ntifs-_token_information_class.md)

[**TOKEN_OWNER**](ns-ntifs-_token_owner.md)

[**TOKEN_PRIMARY_GROUP**](ns-ntifs-_token_primary_group.md)

[**TOKEN_PRIVILEGES**](ns-ntifs-_token_privileges.md)

[**TOKEN_SOURCE**](ns-ntifs-_token_source.md)

[**TOKEN_STATISTICS**](ns-ntifs-_token_statistics.md)

[**TOKEN_TYPE**](ne-ntifs-_token_type.md)

[**TOKEN_USER**](ns-ntifs-_token_user.md)

[**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md)

[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)
