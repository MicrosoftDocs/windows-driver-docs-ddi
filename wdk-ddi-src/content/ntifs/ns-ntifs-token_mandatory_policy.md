---
UID: NS:ntifs._TOKEN_MANDATORY_POLICY
tech.root: ifsk
title: TOKEN_MANDATORY_POLICY
ms.date: 01/10/23
targetos: Windows
description: Learn more about the TOKEN_MANDATORY_POLICY structure.
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
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.target-type: 
req.typenames: TOKEN_MANDATORY_POLICY, *PTOKEN_MANDATORY_POLICY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_MANDATORY_POLICY
 - PTOKEN_MANDATORY_POLICY
 - TOKEN_MANDATORY_POLICY
f1_keywords:
 - _TOKEN_MANDATORY_POLICY
 - ntifs/_TOKEN_MANDATORY_POLICY
 - PTOKEN_MANDATORY_POLICY
 - ntifs/PTOKEN_MANDATORY_POLICY
 - TOKEN_MANDATORY_POLICY
 - ntifs/TOKEN_MANDATORY_POLICY
dev_langs:
 - c++
helpviewer_keywords:
 - _TOKEN_MANDATORY_POLICY
---

## -description

The **TOKEN_MANDATORY_POLICY** structure specifies the mandatory integrity policy for a token.

## -struct-fields

### -field Policy

The mandatory integrity access policy for the associated token. This can be one of the following values.

| Value | Meaning |
| TOKEN_MANDATORY_POLICY_OFF (0x0) |  No mandatory integrity policy is enforced for the token. |
| TOKEN_MANDATORY_POLICY_NO_WRITE_UP (0x1) | A process associated with the token cannot write to objects that have a greater mandatory integrity level. |
| TOKEN_MANDATORY_POLICY_NEW_PROCESS_MIN (0x2) | A process created with the token has an integrity level that is the lesser of the parent-process integrity level and the executable-file integrity level. |
| TOKEN_MANDATORY_POLICY_VALID_MASK (0x3) | A combination of TOKEN_MANDATORY_POLICY_NO_WRITE_UP and TOKEN_MANDATORY_POLICY_NEW_PROCESS_MIN. |

## -see-also

[**TOKEN_ACCESS_INFORMATION**](ns-ntifs-token_access_information.md)
