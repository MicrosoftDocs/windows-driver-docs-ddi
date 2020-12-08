---
UID: NS:rilapitypes.RILUICCLOCK
title: RILUICCLOCK (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclock_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILUICCLOCK structure"]
ms.keywords: "*LPRILUICCLOCK, RILUICCLOCK, RILUICCLOCK structure [Network Drivers Starting with Windows Vista], netvista.riluicclock_2, rilapitypes/RILUICCLOCK"
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
req.typenames: RILUICCLOCK, *LPRILUICCLOCK
req.product: Windows 10 or later.
f1_keywords:
 - RILUICCLOCK
 - rilapitypes/RILUICCLOCK
 - LPRILUICCLOCK
 - rilapitypes/LPRILUICCLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCLOCK
---

# RILUICCLOCK structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field hUiccApp

### -field dwKeyRef

## -syntax

```cpp
typedef struct _RILUICCLOCK {
  HUICCAPP  hUiccApp;
  DWORD     dwKeyRef;
} RILUICCLOCK, RILUICCLOCK;
```

