---
UID: NS:rilapitypes.RILADDRESS
title: RILADDRESS (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdress_2.htm
tech.root: netvista
ms.assetid: 45888814-28c4-4cbc-ace8-7b4aa682b91b
ms.date: 02/26/2018
keywords: ["RILADDRESS structure"]
ms.keywords: "*LPRILADDRESS, RILADDRESS, RILADDRESS structure [Network Drivers Starting with Windows Vista], netvista.riladdress_2, rilapitypes/RILADDRESS"
f1_keywords:
 - "rilapitypes/RILADDRESS"
 - "RILADDRESS"
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
- RILADDRESS
targetos: Windows
req.typenames: RILADDRESS, *LPRILADDRESS
req.product: Windows 10 or later.
---

# RILADDRESS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef struct _RILADDRESS {
  DWORD                     cbSize;
  DWORD                     dwParams;
  RILADDRESSTYPE            dwType;
  RILADDRESSNUMPLAN         dwNumPlan;
  WCHAR [MAXLENGTH_ADDRESS] wszAddress;
} RILADDRESS, RILADDRESS;
```


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwType


### -field dwNumPlan


### -field wszAddress

