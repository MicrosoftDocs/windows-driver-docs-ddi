---
UID: NE:rilapitypes.RILNETWORKCODEPARAMMASK
title: RILNETWORKCODEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnetworkcodeparammask_2.htm
tech.root: netvista
ms.assetid: 944a4974-cb1d-4c0c-bca6-2741f16d2b3e
ms.date: 02/26/2018
ms.keywords: RILNETWORKCODEPARAMMASK, RILNETWORKCODEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_NETWORKCODE_ALL, RIL_PARAM_NETWORKCODE_MCC, RIL_PARAM_NETWORKCODE_MNC, RIL_PARAM_NETWORKCODE_NID, RIL_PARAM_NETWORKCODE_RI, RIL_PARAM_NETWORKCODE_SID, netvista.rilnetworkcodeparammask_2, rilapitypes/RILNETWORKCODEPARAMMASK, rilapitypes/RIL_PARAM_NETWORKCODE_ALL, rilapitypes/RIL_PARAM_NETWORKCODE_MCC, rilapitypes/RIL_PARAM_NETWORKCODE_MNC, rilapitypes/RIL_PARAM_NETWORKCODE_NID, rilapitypes/RIL_PARAM_NETWORKCODE_RI, rilapitypes/RIL_PARAM_NETWORKCODE_SID
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
-	RILNETWORKCODEPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILNETWORKCODEPARAMMASK
req.product: Windows 10 or later.
---

# RILNETWORKCODEPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef enum _RILNETWORKCODEPARAMMASK {
  RIL_PARAM_NETWORKCODE_MCC,
  RIL_PARAM_NETWORKCODE_MNC,
  RIL_PARAM_NETWORKCODE_SID,
  RIL_PARAM_NETWORKCODE_NID,
  RIL_PARAM_NETWORKCODE_RI,
  RIL_PARAM_NETWORKCODE_ALL
} RILNETWORKCODEPARAMMASK;
```


## -enum-fields




### -field RIL_PARAM_NETWORKCODE_EXECUTOR


### -field RIL_PARAM_NETWORKCODE_MCC


### -field RIL_PARAM_NETWORKCODE_MNC


### -field RIL_PARAM_NETWORKCODE_SID


### -field RIL_PARAM_NETWORKCODE_NID


### -field RIL_PARAM_NETWORKCODE_RI


### -field RIL_PARAM_NETWORKCODE_ALL

