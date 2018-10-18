---
UID: NS:rilapitypes.RILUICCSUBSCRIBERNUMBERS
title: RILUICCSUBSCRIBERNUMBERS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccsubscribernumbers_2.htm
tech.root: netvista
ms.assetid: e1a097b5-ce13-4070-a6f6-4b461ac086de
ms.date: 2/26/2018
ms.keywords: "*LPRILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS structure [Network Drivers Starting with Windows Vista], netvista.riluiccsubscribernumbers_2, rilapitypes/RILUICCSUBSCRIBERNUMBERS"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILUICCSUBSCRIBERNUMBERS
product:
- Windows
targetos: Windows
req.typenames: RILUICCSUBSCRIBERNUMBERS, *LPRILUICCSUBSCRIBERNUMBERS
req.product: Windows 10 or later.
---

# RILUICCSUBSCRIBERNUMBERS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef struct _RILUICCSUBSCRIBERNUMBERS {
  DWORD                 cbSize;
  DWORD                 dwNumSubscribers;
  RILSUBSCRIBERINFO [1] rsiInfo;
} RILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS;
```


## -struct-fields




### -field cbSize


### -field dwNumSubscribers


### -field rsiInfo

