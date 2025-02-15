---
UID: NS:ntifs._SEC_APP_SESSION_STATE
tech.root: ifsk
title: SEC_APP_SESSION_STATE
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the SEC_APP_SESSION_STATE structure.
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
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: SEC_APP_SESSION_STATE, *PSEC_APP_SESSION_STATE
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
 - _SEC_APP_SESSION_STATE
 - PSEC_APP_SESSION_STATE
 - SEC_APP_SESSION_STATE
f1_keywords:
 - _SEC_APP_SESSION_STATE
 - ntifs/_SEC_APP_SESSION_STATE
 - PSEC_APP_SESSION_STATE
 - ntifs/PSEC_APP_SESSION_STATE
 - SEC_APP_SESSION_STATE
 - ntifs/SEC_APP_SESSION_STATE
dev_langs:
 - c++
helpviewer_keywords:
 - _SEC_APP_SESSION_STATE
---

## -description

The **SEC_APP_SESSION_STATE** structure is used to store and manage application-specific session state information. This structure is typically associated with session tickets to maintain state across secure sessions.

## -struct-fields

### -field AppSessionStateSize

Size, in bytes, of the application state data contained in the **AppSessionState** array. The maximum size allowed is 2048 bytes.

### -field AppSessionState[ANYSIZE_ARRAY]

An array of bytes representing the application-specific state data to be associated with the session ticket. This array is flexible in size, allowing it to accommodate varying amounts of state information.
