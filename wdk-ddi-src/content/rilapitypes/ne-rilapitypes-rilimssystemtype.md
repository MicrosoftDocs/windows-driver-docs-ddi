---
UID: NE:rilapitypes.RILIMSSYSTEMTYPE
title: RILIMSSYSTEMTYPE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssystemtype_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILIMSSYSTEMTYPE enumeration"]
ms.keywords: RILIMSSYSTEMTYPE, RILIMSSYSTEMTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_IMSSYSTEMTYPE_LTE, RIL_IMSSYSTEMTYPE_MAX, RIL_IMSSYSTEMTYPE_WIFI, netvista.rilimssystemtype_2, rilapitypes/RILIMSSYSTEMTYPE, rilapitypes/RIL_IMSSYSTEMTYPE_LTE, rilapitypes/RIL_IMSSYSTEMTYPE_MAX, rilapitypes/RIL_IMSSYSTEMTYPE_WIFI
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
req.typenames: RILIMSSYSTEMTYPE
req.product: Windows 10 or later.
f1_keywords:
 - RILIMSSYSTEMTYPE
 - rilapitypes/RILIMSSYSTEMTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILIMSSYSTEMTYPE
---

# RILIMSSYSTEMTYPE enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_IMSSYSTEMTYPE_UNKNOWN

### -field RIL_IMSSYSTEMTYPE_WIFI

### -field RIL_IMSSYSTEMTYPE_LTE

### -field RIL_IMSSYSTEMTYPE_MAX

## -syntax

```cpp
typedef enum _RILIMSSYSTEMTYPE {
  RIL_IMSSYSTEMTYPE_WIFI,
  RIL_IMSSYSTEMTYPE_LTE,
  RIL_IMSSYSTEMTYPE_MAX
} RILIMSSYSTEMTYPE;
```

