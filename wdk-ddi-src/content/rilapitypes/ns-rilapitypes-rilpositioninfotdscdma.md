---
UID: NS:rilapitypes.RILPOSITIONINFOTDSCDMA
title: RILPOSITIONINFOTDSCDMA (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfotdscdma_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILPOSITIONINFOTDSCDMA structure"]
ms.keywords: "*LPRILPOSITIONINFOTDSCDMA, RILPOSITIONINFOTDSCDMA, RILPOSITIONINFOTDSCDMA structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfotdscdma_2, rilapitypes/RILPOSITIONINFOTDSCDMA"
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
req.typenames: RILPOSITIONINFOTDSCDMA, *LPRILPOSITIONINFOTDSCDMA
req.product: Windows 10 or later.
f1_keywords:
 - RILPOSITIONINFOTDSCDMA
 - rilapitypes/RILPOSITIONINFOTDSCDMA
 - LPRILPOSITIONINFOTDSCDMA
 - rilapitypes/LPRILPOSITIONINFOTDSCDMA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFOTDSCDMA
 - LPRILPOSITIONINFOTDSCDMA
---

# RILPOSITIONINFOTDSCDMA structure (rilapitypes.h)


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

### -field dwTimingAdvance

### -field dwRSCP

### -field dwPathLoss

## -syntax

```cpp
typedef struct _RILPOSITIONINFOTDSCDMA {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwLocationAreaCode;
  DWORD  dwCellID;
  DWORD  dwUARFCN;
  DWORD  dwCellParameterID;
  DWORD  dwTimingAdvance;
  DWORD  dwRSCP;
  DWORD  dwPathLoss;
} RILPOSITIONINFOTDSCDMA, RILPOSITIONINFOTDSCDMA;
```

