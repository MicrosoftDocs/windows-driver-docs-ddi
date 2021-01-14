---
UID: NS:rilapitypes.RILUICCLOCKSTATE
title: RILUICCLOCKSTATE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclockstate_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILUICCLOCKSTATE structure"]
ms.keywords: "*LPRILUICCLOCKSTATE, RILUICCLOCKSTATE, RILUICCLOCKSTATE structure [Network Drivers Starting with Windows Vista], netvista.riluicclockstate_2, rilapitypes/RILUICCLOCKSTATE"
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: RILUICCLOCKSTATE, *LPRILUICCLOCKSTATE
req.product: Windows 10 or later.
f1_keywords:
 - RILUICCLOCKSTATE
 - rilapitypes/RILUICCLOCKSTATE
 - LPRILUICCLOCKSTATE
 - rilapitypes/LPRILUICCLOCKSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCLOCKSTATE
 - LPRILUICCLOCKSTATE
---

# RILUICCLOCKSTATE structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field cbSize

### -field dwParams

### -field rilUiccLock

### -field dwLockState

### -field dwVerifyAttemptsLeft

### -field dwUnblockAttemptsLeft

## -syntax

```cpp
typedef struct _RILUICCLOCKSTATE {
  DWORD        cbSize;
  DWORD        dwParams;
  RILUICCLOCK  rilUiccLock;
  DWORD        dwLockState;
  DWORD        dwVerifyAttemptsLeft;
  DWORD        dwUnblockAttemptsLeft;
} RILUICCLOCKSTATE, RILUICCLOCKSTATE;
```

