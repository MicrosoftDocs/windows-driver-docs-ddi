---
UID: NE:rilapitypes.RILIMSSYSTEMTYPE
title: RILIMSSYSTEMTYPE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssystemtype_2.htm
tech.root: netvista
ms.assetid: 94c37721-372f-448f-8cd9-d4c64dd285cb
ms.date: 02/26/2018
ms.keywords: RILIMSSYSTEMTYPE, RILIMSSYSTEMTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_IMSSYSTEMTYPE_LTE, RIL_IMSSYSTEMTYPE_MAX, RIL_IMSSYSTEMTYPE_WIFI, netvista.rilimssystemtype_2, rilapitypes/RILIMSSYSTEMTYPE, rilapitypes/RIL_IMSSYSTEMTYPE_LTE, rilapitypes/RIL_IMSSYSTEMTYPE_MAX, rilapitypes/RIL_IMSSYSTEMTYPE_WIFI
ms.topic: enum
f1_keywords:
 - "rilapitypes/RILIMSSYSTEMTYPE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILIMSSYSTEMTYPE
product:
- Windows
targetos: Windows
req.typenames: RILIMSSYSTEMTYPE
req.product: Windows 10 or later.
---

# RILIMSSYSTEMTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef enum _RILIMSSYSTEMTYPE {
  RIL_IMSSYSTEMTYPE_WIFI,
  RIL_IMSSYSTEMTYPE_LTE,
  RIL_IMSSYSTEMTYPE_MAX
} RILIMSSYSTEMTYPE;
```


## -enum-fields




### -field RIL_IMSSYSTEMTYPE_UNKNOWN


### -field RIL_IMSSYSTEMTYPE_WIFI


### -field RIL_IMSSYSTEMTYPE_LTE


### -field RIL_IMSSYSTEMTYPE_MAX

