---
UID: NE:rilapitypes.RILDEVICEINFORMATION
title: RILDEVICEINFORMATION (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeviceinformation_2.htm
tech.root: netvista
ms.assetid: a67a637e-92ac-4a42-bfef-8a42ce26b9b3
ms.date: 02/26/2018
keywords: ["RILDEVICEINFORMATION enumeration"]
ms.keywords: RILDEVICEINFORMATION, RILDEVICEINFORMATION enumeration [Network Drivers Starting with Windows Vista], RIL_DEVICEINFO_ARG_LARGEST, RIL_DEVICEINFO_ARG_SMALLEST, RIL_DEVICEINFO_MAX, RIL_DEVICEINFO_MIN, RIL_DEVICEINFO_MODEL, RIL_DEVICEINFO_REVISION, RIL_DEVICEINFO_SERIALNUMBER_CDMA, RIL_DEVICEINFO_SERIALNUMBER_GW, netvista.rildeviceinformation_2, rilapitypes/RILDEVICEINFORMATION, rilapitypes/RIL_DEVICEINFO_ARG_LARGEST, rilapitypes/RIL_DEVICEINFO_ARG_SMALLEST, rilapitypes/RIL_DEVICEINFO_MAX, rilapitypes/RIL_DEVICEINFO_MIN, rilapitypes/RIL_DEVICEINFO_MODEL, rilapitypes/RIL_DEVICEINFO_REVISION, rilapitypes/RIL_DEVICEINFO_SERIALNUMBER_CDMA, rilapitypes/RIL_DEVICEINFO_SERIALNUMBER_GW
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
req.typenames: RILDEVICEINFORMATION
req.product: Windows 10 or later.
f1_keywords:
 - RILDEVICEINFORMATION
 - rilapitypes/RILDEVICEINFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILDEVICEINFORMATION
---

# RILDEVICEINFORMATION enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_DEVICEINFO_MANUFACTURER

### -field RIL_DEVICEINFO_MODEL

### -field RIL_DEVICEINFO_REVISION

### -field RIL_DEVICEINFO_SERIALNUMBER_GW

### -field RIL_DEVICEINFO_SERIALNUMBER_CDMA

### -field RIL_DEVICEINFO_ARG_SMALLEST

### -field RIL_DEVICEINFO_ARG_LARGEST

### -field RIL_DEVICEINFO_MIN

### -field RIL_DEVICEINFO_MAX

## -syntax

```cpp
typedef enum _RILDEVICEINFORMATION {
  RIL_DEVICEINFO_MODEL,
  RIL_DEVICEINFO_REVISION,
  RIL_DEVICEINFO_SERIALNUMBER_GW,
  RIL_DEVICEINFO_SERIALNUMBER_CDMA,
  RIL_DEVICEINFO_ARG_SMALLEST,
  RIL_DEVICEINFO_ARG_LARGEST,
  RIL_DEVICEINFO_MIN,
  RIL_DEVICEINFO_MAX
} RILDEVICEINFORMATION;
```

