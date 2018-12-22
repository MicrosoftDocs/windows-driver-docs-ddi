---
UID: NE:rilapitypes.RILSYSTEMTYPE
title: RILSYSTEMTYPE
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemtype_2.htm
tech.root: netvista
ms.assetid: 5342333e-6119-4800-896e-4c388706d97e
ms.date: 02/26/2018
ms.keywords: RILSYSTEMTYPE, RILSYSTEMTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_SYSTEMTYPE_1XRTT, RIL_SYSTEMTYPE_3GPP, RIL_SYSTEMTYPE_ALL, RIL_SYSTEMTYPE_CDMA, RIL_SYSTEMTYPE_EVDO, RIL_SYSTEMTYPE_GSM, RIL_SYSTEMTYPE_GSMTDS, RIL_SYSTEMTYPE_GSMUMTS, RIL_SYSTEMTYPE_GSMUMTSTDS, RIL_SYSTEMTYPE_LTE, RIL_SYSTEMTYPE_TDSCDMA, RIL_SYSTEMTYPE_UMTS, netvista.rilsystemtype_2, rilapitypes/RILSYSTEMTYPE, rilapitypes/RIL_SYSTEMTYPE_1XRTT, rilapitypes/RIL_SYSTEMTYPE_3GPP, rilapitypes/RIL_SYSTEMTYPE_ALL, rilapitypes/RIL_SYSTEMTYPE_CDMA, rilapitypes/RIL_SYSTEMTYPE_EVDO, rilapitypes/RIL_SYSTEMTYPE_GSM, rilapitypes/RIL_SYSTEMTYPE_GSMTDS, rilapitypes/RIL_SYSTEMTYPE_GSMUMTS, rilapitypes/RIL_SYSTEMTYPE_GSMUMTSTDS, rilapitypes/RIL_SYSTEMTYPE_LTE, rilapitypes/RIL_SYSTEMTYPE_TDSCDMA, rilapitypes/RIL_SYSTEMTYPE_UMTS
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
-	RILSYSTEMTYPE
product:
- Windows
targetos: Windows
req.typenames: RILSYSTEMTYPE
req.product: Windows 10 or later.
---

# RILSYSTEMTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef enum _RILSYSTEMTYPE {
  RIL_SYSTEMTYPE_1XRTT,
  RIL_SYSTEMTYPE_EVDO,
  RIL_SYSTEMTYPE_GSM,
  RIL_SYSTEMTYPE_UMTS,
  RIL_SYSTEMTYPE_LTE,
  RIL_SYSTEMTYPE_TDSCDMA,
  RIL_SYSTEMTYPE_CDMA,
  RIL_SYSTEMTYPE_GSMUMTS,
  RIL_SYSTEMTYPE_GSMTDS,
  RIL_SYSTEMTYPE_GSMUMTSTDS,
  RIL_SYSTEMTYPE_3GPP,
  RIL_SYSTEMTYPE_ALL
} RILSYSTEMTYPE;
```


## -enum-fields




### -field RIL_SYSTEMTYPE_NONE


### -field RIL_SYSTEMTYPE_1XRTT


### -field RIL_SYSTEMTYPE_EVDO


### -field RIL_SYSTEMTYPE_GSM


### -field RIL_SYSTEMTYPE_UMTS


### -field RIL_SYSTEMTYPE_LTE


### -field RIL_SYSTEMTYPE_TDSCDMA


### -field RIL_SYSTEMTYPE_CDMA


### -field RIL_SYSTEMTYPE_GSMUMTS


### -field RIL_SYSTEMTYPE_GSMTDS


### -field RIL_SYSTEMTYPE_GSMUMTSTDS


### -field RIL_SYSTEMTYPE_3GPP


### -field RIL_SYSTEMTYPE_ALL

