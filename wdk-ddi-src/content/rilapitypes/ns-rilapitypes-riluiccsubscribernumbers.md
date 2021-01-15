---
UID: NS:rilapitypes.RILUICCSUBSCRIBERNUMBERS
title: RILUICCSUBSCRIBERNUMBERS (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccsubscribernumbers_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILUICCSUBSCRIBERNUMBERS structure"]
ms.keywords: "*LPRILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS structure [Network Drivers Starting with Windows Vista], netvista.riluiccsubscribernumbers_2, rilapitypes/RILUICCSUBSCRIBERNUMBERS"
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
req.typenames: RILUICCSUBSCRIBERNUMBERS, *LPRILUICCSUBSCRIBERNUMBERS
req.product: Windows 10 or later.
f1_keywords:
 - RILUICCSUBSCRIBERNUMBERS
 - rilapitypes/RILUICCSUBSCRIBERNUMBERS
 - LPRILUICCSUBSCRIBERNUMBERS
 - rilapitypes/LPRILUICCSUBSCRIBERNUMBERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCSUBSCRIBERNUMBERS
 - LPRILUICCSUBSCRIBERNUMBERS
---

# RILUICCSUBSCRIBERNUMBERS structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field cbSize

### -field dwNumSubscribers

### -field rsiInfo

## -syntax

```cpp
typedef struct _RILUICCSUBSCRIBERNUMBERS {
  DWORD                 cbSize;
  DWORD                 dwNumSubscribers;
  RILSUBSCRIBERINFO [1] rsiInfo;
} RILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS;
```

