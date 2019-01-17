---
UID: NS:rilapitypes.RILEUTRAMRL
title: RILEUTRAMRL
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rileutramrl_2.htm
tech.root: netvista
ms.assetid: 77a57c67-90ff-489c-a791-56ac0afbec59
ms.date: 02/26/2018
ms.keywords: "*LPRILEUTRAMRL, RILEUTRAMRL, RILEUTRAMRL structure [Network Drivers Starting with Windows Vista], netvista.rileutramrl_2, rilapitypes/RILEUTRAMRL"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILEUTRAMRL
product:
- Windows
targetos: Windows
req.typenames: RILEUTRAMRL, *LPRILEUTRAMRL
req.product: Windows 10 or later.
---

# RILEUTRAMRL structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef struct _RILEUTRAMRL {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwCellID;
  DWORD  dwEARFCN;
  DWORD  dwPhysCellID;
  DWORD  dwTAC;
  LONG   dwRSRP;
  LONG   dwRSRQ;
} RILEUTRAMRL, RILEUTRAMRL;
```


## -struct-fields




### -field dwParams


### -field dwMobileCountryCode


### -field dwMobileNetworkCode


### -field dwCellID


### -field dwEARFCN


### -field dwPhysCellID


### -field dwTAC


### -field dwRSRP


### -field dwRSRQ

