---
UID: NS:rilapitypes.RILIMSI
title: RILIMSI (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsi_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILIMSI structure"]
ms.keywords: "*LPRILIMSI, RILIMSI, RILIMSI structure [Network Drivers Starting with Windows Vista], netvista.rilimsi_2, rilapitypes/RILIMSI"
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
targetos: Windows
req.typenames: RILIMSI, *LPRILIMSI
req.product: Windows 10 or later.
f1_keywords:
 - RILIMSI
 - rilapitypes/RILIMSI
 - LPRILIMSI
 - rilapitypes/LPRILIMSI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILIMSI
 - LPRILIMSI
---

# RILIMSI structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field cbSize

### -field dwParams

### -field wszImsi

### -field dwMcc

### -field dwMnc

## -syntax

```cpp
typedef struct _RILIMSI {
  DWORD                  cbSize;
  DWORD                  dwParams;
  WCHAR [MAXLENGTH_IMSI] wszImsi;
  DWORD                  dwMcc;
  DWORD                  dwMnc;
} RILIMSI, RILIMSI;
```

