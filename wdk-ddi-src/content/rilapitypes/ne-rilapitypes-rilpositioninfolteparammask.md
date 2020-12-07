---
UID: NE:rilapitypes.RILPOSITIONINFOLTEPARAMMASK
title: RILPOSITIONINFOLTEPARAMMASK (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfolteparammask_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILPOSITIONINFOLTEPARAMMASK enumeration"]
ms.keywords: RILPOSITIONINFOLTEPARAMMASK, RILPOSITIONINFOLTEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_POSITION_LTE_ALL, RIL_PARAM_POSITION_LTE_CELLID, RIL_PARAM_POSITION_LTE_EARFCN, RIL_PARAM_POSITION_LTE_MNC, RIL_PARAM_POSITION_LTE_PHYSCELLID, RIL_PARAM_POSITION_LTE_RSRP, RIL_PARAM_POSITION_LTE_RSRQ, RIL_PARAM_POSITION_LTE_TA, RIL_PARAM_POSITION_LTE_TAC, netvista.rilpositioninfolteparammask_2, rilapitypes/RILPOSITIONINFOLTEPARAMMASK, rilapitypes/RIL_PARAM_POSITION_LTE_ALL, rilapitypes/RIL_PARAM_POSITION_LTE_CELLID, rilapitypes/RIL_PARAM_POSITION_LTE_EARFCN, rilapitypes/RIL_PARAM_POSITION_LTE_MNC, rilapitypes/RIL_PARAM_POSITION_LTE_PHYSCELLID, rilapitypes/RIL_PARAM_POSITION_LTE_RSRP, rilapitypes/RIL_PARAM_POSITION_LTE_RSRQ, rilapitypes/RIL_PARAM_POSITION_LTE_TA, rilapitypes/RIL_PARAM_POSITION_LTE_TAC
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
targetos: Windows
req.typenames: RILPOSITIONINFOLTEPARAMMASK
req.product: Windows 10 or later.
f1_keywords:
 - RILPOSITIONINFOLTEPARAMMASK
 - rilapitypes/RILPOSITIONINFOLTEPARAMMASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFOLTEPARAMMASK
---

# RILPOSITIONINFOLTEPARAMMASK enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_PARAM_POSITION_LTE_MCC

### -field RIL_PARAM_POSITION_LTE_MNC

### -field RIL_PARAM_POSITION_LTE_CELLID

### -field RIL_PARAM_POSITION_LTE_EARFCN

### -field RIL_PARAM_POSITION_LTE_PHYSCELLID

### -field RIL_PARAM_POSITION_LTE_TAC

### -field RIL_PARAM_POSITION_LTE_RSRP

### -field RIL_PARAM_POSITION_LTE_RSRQ

### -field RIL_PARAM_POSITION_LTE_TA

### -field RIL_PARAM_POSITION_LTE_ALL

## -syntax

```cpp
typedef enum _RILPOSITIONINFOLTEPARAMMASK {
  RIL_PARAM_POSITION_LTE_MNC,
  RIL_PARAM_POSITION_LTE_CELLID,
  RIL_PARAM_POSITION_LTE_EARFCN,
  RIL_PARAM_POSITION_LTE_PHYSCELLID,
  RIL_PARAM_POSITION_LTE_TAC,
  RIL_PARAM_POSITION_LTE_RSRP,
  RIL_PARAM_POSITION_LTE_RSRQ,
  RIL_PARAM_POSITION_LTE_TA,
  RIL_PARAM_POSITION_LTE_ALL
} RILPOSITIONINFOLTEPARAMMASK;
```

