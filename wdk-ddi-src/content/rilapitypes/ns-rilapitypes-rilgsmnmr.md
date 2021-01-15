---
UID: NS:rilapitypes.RILGSMNMR
title: RILGSMNMR (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgsmnmr_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILGSMNMR structure"]
ms.keywords: "*LPRILGSMNMR, RILGSMNMR, RILGSMNMR structure [Network Drivers Starting with Windows Vista], netvista.rilgsmnmr_2, rilapitypes/RILGSMNMR"
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
req.typenames: RILGSMNMR, *LPRILGSMNMR
req.product: Windows 10 or later.
f1_keywords:
 - RILGSMNMR
 - rilapitypes/RILGSMNMR
 - LPRILGSMNMR
 - rilapitypes/LPRILGSMNMR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILGSMNMR
 - LPRILGSMNMR
---

# RILGSMNMR structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field dwParams

### -field dwMobileCountryCode

### -field dwMobileNetworkCode

### -field dwLocationAreaCode

### -field dwCellID

### -field dwARFCN

### -field dwBaseStationID

### -field dwRxLevel

## -syntax

```cpp
typedef struct _RILGSMNMR {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwLocationAreaCode;
  DWORD  dwCellID;
  DWORD  dwARFCN;
  DWORD  dwBaseStationID;
  DWORD  dwRxLevel;
} RILGSMNMR, RILGSMNMR;
```

