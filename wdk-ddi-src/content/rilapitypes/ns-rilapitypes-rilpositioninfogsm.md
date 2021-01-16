---
UID: NS:rilapitypes.RILPOSITIONINFOGSM
title: RILPOSITIONINFOGSM (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfogsm_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILPOSITIONINFOGSM structure"]
ms.keywords: "*LPRILPOSITIONINFOGSM, RILPOSITIONINFOGSM, RILPOSITIONINFOGSM structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfogsm_2, rilapitypes/RILPOSITIONINFOGSM"
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
req.typenames: RILPOSITIONINFOGSM, *LPRILPOSITIONINFOGSM
req.product: Windows 10 or later.
f1_keywords:
 - RILPOSITIONINFOGSM
 - rilapitypes/RILPOSITIONINFOGSM
 - LPRILPOSITIONINFOGSM
 - rilapitypes/LPRILPOSITIONINFOGSM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFOGSM
 - LPRILPOSITIONINFOGSM
---

# RILPOSITIONINFOGSM structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field dwParams

### -field dwMobileCountryCode

### -field dwMobileNetworkCode

### -field dwLocationAreaCode

### -field dwCellID

### -field dwTimingAdvance

### -field dwARFCN

### -field dwBaseStationID

### -field dwRxLevel

## -syntax

```cpp
typedef struct _RILPOSITIONINFOGSM {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwLocationAreaCode;
  DWORD  dwCellID;
  DWORD  dwTimingAdvance;
  DWORD  dwARFCN;
  DWORD  dwBaseStationID;
  DWORD  dwRxLevel;
} RILPOSITIONINFOGSM, RILPOSITIONINFOGSM;
```

