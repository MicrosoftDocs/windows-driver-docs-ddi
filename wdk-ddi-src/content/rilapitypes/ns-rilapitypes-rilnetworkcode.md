---
UID: NS:rilapitypes.RILNETWORKCODE
title: RILNETWORKCODE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnetworkcode_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILNETWORKCODE structure"]
ms.keywords: "*LPRILNETWORKCODE, RILNETWORKCODE, RILNETWORKCODE structure [Network Drivers Starting with Windows Vista], netvista.rilnetworkcode_2, rilapitypes/RILNETWORKCODE"
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
req.typenames: RILNETWORKCODE, *LPRILNETWORKCODE
req.product: Windows 10 or later.
f1_keywords:
 - RILNETWORKCODE
 - rilapitypes/RILNETWORKCODE
 - LPRILNETWORKCODE
 - rilapitypes/LPRILNETWORKCODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILNETWORKCODE
---

# RILNETWORKCODE structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field cbSize

### -field dwParams

### -field dwExecutor

### -field dwMCC

### -field dwMNC

### -field dwSID

### -field dwNID

### -field dwRI

## -syntax

```cpp
typedef struct _RILNETWORKCODE {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwExecutor;
  DWORD  dwMCC;
  DWORD  dwMNC;
  DWORD  dwSID;
  DWORD  dwNID;
  DWORD  dwRI;
} RILNETWORKCODE, RILNETWORKCODE;
```

