---
UID: NS:ntifs._TOKEN_CONTROL
title: _TOKEN_CONTROL (ntifs.h)
description: The TOKEN_CONTROL structure contains information that identifies an access token.
old-location: ifsk\token_control.htm
tech.root: ifsk
ms.assetid: 3e0d41f4-4918-4768-a341-25d27f0a8af0
ms.date: 04/16/2018
keywords: ["TOKEN_CONTROL structure"]
ms.keywords: "*PTOKEN_CONTROL, PTOKEN_CONTROL, PTOKEN_CONTROL structure pointer [Installable File System Drivers], TOKEN_CONTROL, TOKEN_CONTROL structure [Installable File System Drivers], _TOKEN_CONTROL, ifsk.token_control, ntifs/PTOKEN_CONTROL, ntifs/TOKEN_CONTROL, securitystructures_26958d39-4a12-4979-b0cc-7a880e3d2384.xml"
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
req.typenames: TOKEN_CONTROL, *PTOKEN_CONTROL
f1_keywords:
 - _TOKEN_CONTROL
 - ntifs/_TOKEN_CONTROL
 - PTOKEN_CONTROL
 - ntifs/PTOKEN_CONTROL
 - TOKEN_CONTROL
 - ntifs/TOKEN_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - TOKEN_CONTROL
---

# _TOKEN_CONTROL structure


## -description

The TOKEN_CONTROL structure contains information that identifies an access token.

## -struct-fields

### -field TokenId

Specifies a locally unique identifier (LUID) identifying this instance of the token object.

### -field AuthenticationId

Specifies an LUID assigned to the session this token represents. There can be many tokens representing a single logon session.

### -field ModifiedId

Specifies an LUID that changes each time the token is modified. An application can use this value as a test of whether a security context has changed since it was last used.

### -field TokenSource

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_source">TOKEN_SOURCE</a> structure identifying the source that issued the token. This information is used in audit logging.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_luid_and_attributes">LUID_AND_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_default_dacl">TOKEN_DEFAULT_DACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_owner">TOKEN_OWNER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_primary_group">TOKEN_PRIMARY_GROUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_privileges">TOKEN_PRIVILEGES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_source">TOKEN_SOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_statistics">TOKEN_STATISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_type">TOKEN_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_user">TOKEN_USER</a>

