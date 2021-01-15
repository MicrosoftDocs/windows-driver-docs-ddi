---
UID: NS:rilapitypes.RILPOSITIONINFOUMTS
title: RILPOSITIONINFOUMTS (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfoumts_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILPOSITIONINFOUMTS structure"]
ms.keywords: "*LPRILPOSITIONINFOUMTS, RILPOSITIONINFOUMTS, RILPOSITIONINFOUMTS structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfoumts_2, rilapitypes/RILPOSITIONINFOUMTS"
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
req.typenames: RILPOSITIONINFOUMTS, *LPRILPOSITIONINFOUMTS
req.product: Windows 10 or later.
f1_keywords:
 - RILPOSITIONINFOUMTS
 - rilapitypes/RILPOSITIONINFOUMTS
 - LPRILPOSITIONINFOUMTS
 - rilapitypes/LPRILPOSITIONINFOUMTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFOUMTS
 - LPRILPOSITIONINFOUMTS
---

# RILPOSITIONINFOUMTS structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field dwParams

### -field dwMobileCountryCode

### -field dwMobileNetworkCode

### -field dwLocationAreaCode

### -field dwCellID

### -field dwFrequencyInfoUL

### -field dwFrequencyInfoDL

### -field dwFrequencyInfoNT

### -field dwUARFCN

### -field dwPrimaryScramblingCode

### -field dwRSCP

### -field dwECNO

### -field dwPathLoss

## -syntax

```cpp
typedef struct _RILPOSITIONINFOUMTS {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwLocationAreaCode;
  DWORD  dwCellID;
  DWORD  dwFrequencyInfoUL;
  DWORD  dwFrequencyInfoDL;
  DWORD  dwFrequencyInfoNT;
  DWORD  dwUARFCN;
  DWORD  dwPrimaryScramblingCode;
  LONG   dwRSCP;
  LONG   dwECNO;
  DWORD  dwPathLoss;
} RILPOSITIONINFOUMTS, RILPOSITIONINFOUMTS;
```

