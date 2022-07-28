---
UID: NS:ntifs._TOKEN_STATISTICS
title: TOKEN_STATISTICS (ntifs.h)
description: TOKEN_STATISTICS contains information about an access token. A driver can retrieve this information by calling SeQueryInformationToken or ZwQueryInformationToken.
old-location: ifsk\token_statistics.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["TOKEN_STATISTICS structure"]
ms.keywords: "*PTOKEN_STATISTICS, PTOKEN_STATISTICS, PTOKEN_STATISTICS structure pointer [Installable File System Drivers], TOKEN_STATISTICS, TOKEN_STATISTICS structure [Installable File System Drivers], _TOKEN_STATISTICS, ifsk.token_statistics, ntifs/PTOKEN_STATISTICS, ntifs/TOKEN_STATISTICS, securitystructures_5934a44f-c54e-44fe-a1c8-50b656b2b1f5.xml"
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
req.typenames: TOKEN_STATISTICS, *PTOKEN_STATISTICS
f1_keywords:
 - _TOKEN_STATISTICS
 - ntifs/_TOKEN_STATISTICS
 - PTOKEN_STATISTICS
 - ntifs/PTOKEN_STATISTICS
 - TOKEN_STATISTICS
 - ntifs/TOKEN_STATISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_STATISTICS
 - PTOKEN_STATISTICS
 - TOKEN_STATISTICS
---

# TOKEN_STATISTICS structure

## -description

The **TOKEN_STATISTICS** structure contains information about an access token. A driver can retrieve this information by calling [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md) or [**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken).

## -struct-fields

### -field TokenId

Specifies a locally unique identifier ([**LUID**](../igpupvdev/ns-igpupvdev-_luid.md)) that identifies this instance of the token object.

### -field AuthenticationId

Specifies an LUID assigned to the session this token represents. There can be many tokens representing a single logon session.

### -field ExpirationTime

Specifies the time at which this token expires. Expiration times for access tokens are not currently supported.

### -field TokenType

Specifies a [**TOKEN_TYPE**](ne-ntifs-_token_type.md) enumerated type indicating whether the token is a primary or impersonation token.

### -field ImpersonationLevel

Specifies a [**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md) enumerated type indicating the impersonation level of the token. This member is valid only if the **TokenType** is TokenImpersonation.

### -field DynamicCharged

Specifies the amount, in bytes, of memory allocated for storing a default access-control list (DACL) and primary group identifier.

### -field DynamicAvailable

Specifies the portion of the memory allocated for storing a DACL and primary group identifier that is not already in use. This value is returned as a count of free bytes.

### -field GroupCount

Specifies the number of supplemental group security identifiers ([**SID**](ns-ntifs-_sid.md)) included in the token.

### -field PrivilegeCount

Specifies the number of privileges included in the token.

### -field ModifiedId

Specifies an LUID that changes each time the token is modified. An application can use this value as a test of whether a security context has changed since it was last used.

## -see-also

[**ACL**](../wdm/ns-wdm-_acl.md)

[**LUID**](../igpupvdev/ns-igpupvdev-_luid.md)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)

[**SID**](ns-ntifs-_sid.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**TOKEN_INFORMATION_CLASS**](ne-ntifs-_token_information_class.md)

[**TOKEN_TYPE**](ne-ntifs-_token_type.md)

[**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken)

[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)
