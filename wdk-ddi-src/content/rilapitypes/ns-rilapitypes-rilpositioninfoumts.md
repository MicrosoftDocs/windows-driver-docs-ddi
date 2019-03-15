---
UID: NS:rilapitypes.RILPOSITIONINFOUMTS
title: RILPOSITIONINFOUMTS (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfoumts_2.htm
tech.root: netvista
ms.assetid: f0603990-d63c-433f-b5ac-c8d0efcc4243
ms.date: 02/26/2018
ms.keywords: "*LPRILPOSITIONINFOUMTS, RILPOSITIONINFOUMTS, RILPOSITIONINFOUMTS structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfoumts_2, rilapitypes/RILPOSITIONINFOUMTS"
ms.topic: struct
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
- RILPOSITIONINFOUMTS
product:
- Windows
targetos: Windows
req.typenames: RILPOSITIONINFOUMTS, *LPRILPOSITIONINFOUMTS
req.product: Windows 10 or later.
---

# RILPOSITIONINFOUMTS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


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

