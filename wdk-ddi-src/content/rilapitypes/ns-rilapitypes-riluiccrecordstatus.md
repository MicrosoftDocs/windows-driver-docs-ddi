---
UID: NS:rilapitypes.RILUICCRECORDSTATUS
title: RILUICCRECORDSTATUS (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccrecordstatus_2.htm
tech.root: netvista
ms.assetid: 5f6ff5b1-cd13-4bf6-b4ef-e9b6f4fd54e0
ms.date: 02/26/2018
keywords: ["RILUICCRECORDSTATUS structure"]
ms.keywords: "*LPRILUICCRECORDSTATUS, RILUICCRECORDSTATUS, RILUICCRECORDSTATUS structure [Network Drivers Starting with Windows Vista], netvista.riluiccrecordstatus_2, rilapitypes/RILUICCRECORDSTATUS"
f1_keywords:
 - "rilapitypes/RILUICCRECORDSTATUS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILUICCRECORDSTATUS
product:
- Windows
targetos: Windows
req.typenames: RILUICCRECORDSTATUS, *LPRILUICCRECORDSTATUS
req.product: Windows 10 or later.
---

# RILUICCRECORDSTATUS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef struct _RILUICCRECORDSTATUS {
  DWORD                                        cbSize;
  DWORD                                        dwParams;
  RILUICCRECORDTYPE                            dwRecordType;
  DWORD                                        dwItemCount;
  DWORD                                        dwSize;
  RILUICCFILELOCKSTATUS [MAXNUM_EFACCESSTYPES] fileLockStatus;
} RILUICCRECORDSTATUS, RILUICCRECORDSTATUS;
```


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwRecordType


### -field dwItemCount


### -field dwSize


### -field fileLockStatus

