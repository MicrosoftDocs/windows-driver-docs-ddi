---
UID: NE:rilapitypes.RILUICCLOCKSTATELOCKSTATE
title: RILUICCLOCKSTATELOCKSTATE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclockstatelockstate_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILUICCLOCKSTATELOCKSTATE enumeration"]
ms.keywords: RILUICCLOCKSTATELOCKSTATE, RILUICCLOCKSTATELOCKSTATE enumeration [Network Drivers Starting with Windows Vista], RIL_UICCLOCKSTATE_ALL, RIL_UICCLOCKSTATE_BLOCKED, RIL_UICCLOCKSTATE_ENABLED, RIL_UICCLOCKSTATE_VERIFIED, netvista.riluicclockstatelockstate_2, rilapitypes/RILUICCLOCKSTATELOCKSTATE, rilapitypes/RIL_UICCLOCKSTATE_ALL, rilapitypes/RIL_UICCLOCKSTATE_BLOCKED, rilapitypes/RIL_UICCLOCKSTATE_ENABLED, rilapitypes/RIL_UICCLOCKSTATE_VERIFIED
req.header: rilapitypes.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
targetos: Windows
req.typenames: RILUICCLOCKSTATELOCKSTATE
req.product: Windows 10 or later.
f1_keywords:
 - RILUICCLOCKSTATELOCKSTATE
 - rilapitypes/RILUICCLOCKSTATELOCKSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCLOCKSTATELOCKSTATE
---

# RILUICCLOCKSTATELOCKSTATE enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_UICCLOCKSTATE_NONE

### -field RIL_UICCLOCKSTATE_VERIFIED

### -field RIL_UICCLOCKSTATE_ENABLED

### -field RIL_UICCLOCKSTATE_BLOCKED

### -field RIL_UICCLOCKSTATE_ALL

## -syntax

```cpp
typedef enum _RILUICCLOCKSTATELOCKSTATE {
  RIL_UICCLOCKSTATE_VERIFIED,
  RIL_UICCLOCKSTATE_ENABLED,
  RIL_UICCLOCKSTATE_BLOCKED,
  RIL_UICCLOCKSTATE_ALL
} RILUICCLOCKSTATELOCKSTATE;
```

