---
UID: NS:ntifs._TOKEN_ACCESS_INFORMATION
tech.root: ifsk
title: TOKEN_ACCESS_INFORMATION
ms.date: 01/10/2023
targetos: Windows
description: Learn more about the TOKEN_ACCESS_INFORMATION structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.typenames: TOKEN_ACCESS_INFORMATION, *PTOKEN_ACCESS_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_ACCESS_INFORMATION
 - PTOKEN_ACCESS_INFORMATION
 - TOKEN_ACCESS_INFORMATION
f1_keywords:
 - _TOKEN_ACCESS_INFORMATION
 - ntifs/_TOKEN_ACCESS_INFORMATION
 - PTOKEN_ACCESS_INFORMATION
 - ntifs/PTOKEN_ACCESS_INFORMATION
 - TOKEN_ACCESS_INFORMATION
 - ntifs/TOKEN_ACCESS_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _TOKEN_ACCESS_INFORMATION
---

## -description

The **TOKEN_ACCESS_INFORMATION** structure specifies all the information in a token that is necessary to perform an access check.

## -struct-fields

### -field SidHash

Pointer to a [**SID_AND_ATTRIBUTES_HASH**](ns-ntifs-sid_and_attributes_hash.md) structure that specifies a hash of the token's security identifier (SID).

### -field RestrictedSidHash

Pointer to a [**SID_AND_ATTRIBUTES_HASH**](ns-ntifs-sid_and_attributes_hash.md) structure that specifies a hash of the token's restricted SID.

### -field Privileges

Pointer to a [**TOKEN_PRIVILEGES**](ns-ntifs-_token_privileges.md) structure that specifies information about the token's privileges.

### -field AuthenticationId

A [**LUID**](/windows/win32/api/ntdef/ns-ntdef-luid) structure that specifies the token's identity.

### -field TokenType

A [**TOKEN_TYPE**](ne-ntifs-_token_type.md) enumeration value that specifies the token's type.

### -field ImpersonationLevel

A [**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md) enumeration value that specifies the token's impersonation level.

### -field MandatoryPolicy

A [**TOKEN_MANDATORY_POLICY**](ns-ntifs-token_mandatory_policy.md) structure that specifies the token's mandatory integrity policy.

### -field Flags

Reserved. Must be set to zero.

### -field AppContainerNumber

The app container number for the token or zero if this is not an app container token.

### -field PackageSid

The app container [**SID**](ns-ntifs-_sid.md) or NULL if this is not an app container token.

### -field CapabilitiesHash

Pointer to a [**SID_AND_ATTRIBUTES_HASH**](ns-ntifs-sid_and_attributes_hash.md) structure that specifies a hash of the token's capability SIDs.

### -field TrustLevelSid

Pointer to a [**SID**](ns-ntifs-_sid.md) value that specifies the protected process trust level of the token.

### -field SecurityAttributes

Reserved. Must be set to NULL.

## -remarks

## -see-also

[**SeAccessCheckFromState**](nf-ntifs-seaccesscheckfromstate.md)
