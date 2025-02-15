---
UID: NS:ntifs._TOKEN_LOGGING_INFORMATION
tech.root: ifsk
title: TOKEN_LOGGING_INFORMATION
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the TOKEN_LOGGING_INFORMATION structure.
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
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: TOKEN_LOGGING_INFORMATION, *PTOKEN_LOGGING_INFORMATION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_LOGGING_INFORMATION
 - PTOKEN_LOGGING_INFORMATION
 - TOKEN_LOGGING_INFORMATION
f1_keywords:
 - _TOKEN_LOGGING_INFORMATION
 - ntifs/_TOKEN_LOGGING_INFORMATION
 - PTOKEN_LOGGING_INFORMATION
 - ntifs/PTOKEN_LOGGING_INFORMATION
 - TOKEN_LOGGING_INFORMATION
 - ntifs/TOKEN_LOGGING_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _TOKEN_LOGGING_INFORMATION
---

## -description

The **TOKEN_LOGGING_INFORMATION** provides detailed information about a security token.

## -struct-fields

### -field TokenType

A [**TOKEN_TYPE**](/windows/win32/api/winnt/ne-winnt-token_type) value that indicates the type of the token.

### -field TokenElevation

A [**TOKEN_ELEVATION**](/windows/win32/api/winnt/ns-winnt-token_elevation) value that indicates the elevation level of the token.

### -field TokenElevationType

A [**TOKEN_ELEVATION_TYPE**](/windows/win32/api/winnt/ne-winnt-token_elevation_type) value that indicates the elevation type of the token.

### -field ImpersonationLevel

A [**SECURITY_IMPERSONATION_LEVEL**](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) value that indicates the impersonation level of the token.

### -field IntegrityLevel

Indicates the integrity level of the token.

### -field User

A [**SID_AND_ATTRIBUTES**](/windows/win32/api/winnt/ns-winnt-sid_and_attributes) structure that contains the user SID and its attributes.

### -field TrustLevelSid

Pointer to a [**SID**](/windows/win32/api/winnt/ns-winnt-sid) structure representing the trust level of the token.

### -field SessionId

The session ID associated with the token.

### -field AppContainerNumber

The number of the app container associated with the token.

### -field AuthenticationId

A **LUID** that represents the authentication ID of the token.

### -field GroupCount

Number of groups associated with the token.

### -field GroupsLength

Length in bytes of the **Groups** array.

### -field Groups

Pointer to an array of [**SID_AND_ATTRIBUTES**](/windows/win32/api/winnt/ns-winnt-sid_and_attributes) structures that represent the groups associated with the token.
