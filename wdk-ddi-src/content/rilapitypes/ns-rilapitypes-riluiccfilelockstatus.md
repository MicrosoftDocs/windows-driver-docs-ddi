---
UID: NS:rilapitypes.RILUICCFILELOCKSTATUS
title: RILUICCFILELOCKSTATUS (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccfilelockstatus_2.htm
tech.root: netvista
ms.assetid: a06cba0a-9ab6-4125-a506-5cc1d0c1055c
ms.date: 02/26/2018
ms.keywords: "*LPRILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS structure [Network Drivers Starting with Windows Vista], netvista.riluiccfilelockstatus_2, rilapitypes/RILUICCFILELOCKSTATUS"
ms.topic: struct
f1_keywords:
 - "rilapitypes/RILUICCFILELOCKSTATUS"
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
- RILUICCFILELOCKSTATUS
product:
- Windows
targetos: Windows
req.typenames: RILUICCFILELOCKSTATUS, *LPRILUICCFILELOCKSTATUS
req.product: Windows 10 or later.
---

# RILUICCFILELOCKSTATUS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef struct _RILUICCFILELOCKSTATUS {
  DWORD                                 cbSize;
  DWORD                                 dwParams;
  RILUICCFILELOCKSTATUSACCESSCONDITION  dwAccessCondition;
  BYTE [MAXNUM_PINREF]                  bPinRef;
} RILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS;
```


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwAccessCondition


### -field bPinRef

