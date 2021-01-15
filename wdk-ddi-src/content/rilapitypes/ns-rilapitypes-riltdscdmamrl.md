---
UID: NS:rilapitypes.RILTDSCDMAMRL
title: RILTDSCDMAMRL (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltdscdmamrl_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILTDSCDMAMRL structure"]
ms.keywords: "*LPRILTDSCDMAMRL, RILTDSCDMAMRL, RILTDSCDMAMRL structure [Network Drivers Starting with Windows Vista], netvista.riltdscdmamrl_2, rilapitypes/RILTDSCDMAMRL"
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
req.typenames: RILTDSCDMAMRL, *LPRILTDSCDMAMRL
req.product: Windows 10 or later.
f1_keywords:
 - RILTDSCDMAMRL
 - rilapitypes/RILTDSCDMAMRL
 - LPRILTDSCDMAMRL
 - rilapitypes/LPRILTDSCDMAMRL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILTDSCDMAMRL
 - LPRILTDSCDMAMRL
---

# RILTDSCDMAMRL structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field dwParams

### -field dwMobileCountryCode

### -field dwMobileNetworkCode

### -field dwLocationAreaCode

### -field dwCellID

### -field dwUARFCN

### -field dwCellParameterID

### -field dwRSCP

### -field dwPathLoss

## -syntax

```cpp
typedef struct _RILTDSCDMAMRL {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwLocationAreaCode;
  DWORD  dwCellID;
  DWORD  dwUARFCN;
  DWORD  dwCellParameterID;
  DWORD  dwRSCP;
  DWORD  dwPathLoss;
} RILTDSCDMAMRL, RILTDSCDMAMRL;
```

