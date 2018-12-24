---
UID: NE:rilapitypes.RILIMSIPARAMMASK
title: RILIMSIPARAMMASK
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsiparammask_2.htm
tech.root: netvista
ms.assetid: 69516b0b-d563-4a88-b083-a1a5a4e0ef16
ms.date: 02/26/2018
ms.keywords: RILIMSIPARAMMASK, RILIMSIPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_IMSI_ALL, RIL_PARAM_IMSI_MCC, RIL_PARAM_IMSI_MNC, netvista.rilimsiparammask_2, rilapitypes/RILIMSIPARAMMASK, rilapitypes/RIL_PARAM_IMSI_ALL, rilapitypes/RIL_PARAM_IMSI_MCC, rilapitypes/RIL_PARAM_IMSI_MNC
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
-	RILIMSIPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILIMSIPARAMMASK
req.product: Windows 10 or later.
---

# RILIMSIPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef enum _RILIMSIPARAMMASK {
  RIL_PARAM_IMSI_MCC,
  RIL_PARAM_IMSI_MNC,
  RIL_PARAM_IMSI_ALL
} RILIMSIPARAMMASK;
```


## -enum-fields




### -field RIL_PARAM_IMSI_IMSI


### -field RIL_PARAM_IMSI_MCC


### -field RIL_PARAM_IMSI_MNC


### -field RIL_PARAM_IMSI_ALL

