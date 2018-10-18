---
UID: NE:rilapitypes.RILPOSITIONINFOGSMPARAMMASK
title: RILPOSITIONINFOGSMPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfogsmparammask_2.htm
tech.root: netvista
ms.assetid: 7c5fc8bc-6d0c-429c-944f-5f26b7582fa7
ms.date: 2/26/2018
ms.keywords: RILPOSITIONINFOGSMPARAMMASK, RILPOSITIONINFOGSMPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_POSITION_GSM_ALL, RIL_PARAM_POSITION_GSM_ARFCN, RIL_PARAM_POSITION_GSM_BSID, RIL_PARAM_POSITION_GSM_CELLID, RIL_PARAM_POSITION_GSM_LAC, RIL_PARAM_POSITION_GSM_MNC, RIL_PARAM_POSITION_GSM_RXLEVEL, RIL_PARAM_POSITION_GSM_TA, netvista.rilpositioninfogsmparammask_2, rilapitypes/RILPOSITIONINFOGSMPARAMMASK, rilapitypes/RIL_PARAM_POSITION_GSM_ALL, rilapitypes/RIL_PARAM_POSITION_GSM_ARFCN, rilapitypes/RIL_PARAM_POSITION_GSM_BSID, rilapitypes/RIL_PARAM_POSITION_GSM_CELLID, rilapitypes/RIL_PARAM_POSITION_GSM_LAC, rilapitypes/RIL_PARAM_POSITION_GSM_MNC, rilapitypes/RIL_PARAM_POSITION_GSM_RXLEVEL, rilapitypes/RIL_PARAM_POSITION_GSM_TA
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILPOSITIONINFOGSMPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILPOSITIONINFOGSMPARAMMASK
req.product: Windows 10 or later.
---

# RILPOSITIONINFOGSMPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef enum _RILPOSITIONINFOGSMPARAMMASK {
  RIL_PARAM_POSITION_GSM_MNC,
  RIL_PARAM_POSITION_GSM_LAC,
  RIL_PARAM_POSITION_GSM_CELLID,
  RIL_PARAM_POSITION_GSM_TA,
  RIL_PARAM_POSITION_GSM_ARFCN,
  RIL_PARAM_POSITION_GSM_BSID,
  RIL_PARAM_POSITION_GSM_RXLEVEL,
  RIL_PARAM_POSITION_GSM_ALL
} RILPOSITIONINFOGSMPARAMMASK;
```


## -enum-fields




### -field RIL_PARAM_POSITION_GSM_MCC


### -field RIL_PARAM_POSITION_GSM_MNC


### -field RIL_PARAM_POSITION_GSM_LAC


### -field RIL_PARAM_POSITION_GSM_CELLID


### -field RIL_PARAM_POSITION_GSM_TA


### -field RIL_PARAM_POSITION_GSM_ARFCN


### -field RIL_PARAM_POSITION_GSM_BSID


### -field RIL_PARAM_POSITION_GSM_RXLEVEL


### -field RIL_PARAM_POSITION_GSM_ALL

