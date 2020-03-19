---
UID: NS:rilapitypes.RILUICCLOCKSTATE
title: RILUICCLOCKSTATE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclockstate_2.htm
tech.root: netvista
ms.assetid: 18b933e6-cff3-49de-94ec-731a168c9d23
ms.date: 02/26/2018
keywords: ["RILUICCLOCKSTATE structure"]
ms.keywords: "*LPRILUICCLOCKSTATE, RILUICCLOCKSTATE, RILUICCLOCKSTATE structure [Network Drivers Starting with Windows Vista], netvista.riluicclockstate_2, rilapitypes/RILUICCLOCKSTATE"
f1_keywords:
 - "rilapitypes/RILUICCLOCKSTATE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILUICCLOCKSTATE
product:
- Windows
targetos: Windows
req.typenames: RILUICCLOCKSTATE, *LPRILUICCLOCKSTATE
req.product: Windows 10 or later.
---

# RILUICCLOCKSTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


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


## -struct-fields




### -field cbSize


### -field dwParams


### -field rilUiccLock


### -field dwLockState


### -field dwVerifyAttemptsLeft


### -field dwUnblockAttemptsLeft

