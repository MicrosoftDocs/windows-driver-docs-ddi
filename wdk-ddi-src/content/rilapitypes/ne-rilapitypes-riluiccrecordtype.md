---
UID: NE:rilapitypes.RILUICCRECORDTYPE
title: RILUICCRECORDTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccrecordtype_2.htm
tech.root: netvista
ms.assetid: 2eb26355-25e9-4edf-9695-08b172593712
ms.date: 02/26/2018
ms.keywords: RILUICCRECORDTYPE, RILUICCRECORDTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_UICCRECORDTYPE_BERTLV, RIL_UICCRECORDTYPE_CYCLIC, RIL_UICCRECORDTYPE_DEDICATED, RIL_UICCRECORDTYPE_LINEAR, RIL_UICCRECORDTYPE_MASTER, RIL_UICCRECORDTYPE_MAX, RIL_UICCRECORDTYPE_TRANSPARENT, netvista.riluiccrecordtype_2, rilapitypes/RILUICCRECORDTYPE, rilapitypes/RIL_UICCRECORDTYPE_BERTLV, rilapitypes/RIL_UICCRECORDTYPE_CYCLIC, rilapitypes/RIL_UICCRECORDTYPE_DEDICATED, rilapitypes/RIL_UICCRECORDTYPE_LINEAR, rilapitypes/RIL_UICCRECORDTYPE_MASTER, rilapitypes/RIL_UICCRECORDTYPE_MAX, rilapitypes/RIL_UICCRECORDTYPE_TRANSPARENT
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
-	RILUICCRECORDTYPE
product:
- Windows
targetos: Windows
req.typenames: RILUICCRECORDTYPE
req.product: Windows 10 or later.
---

# RILUICCRECORDTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef enum _RILUICCRECORDTYPE {
  RIL_UICCRECORDTYPE_TRANSPARENT,
  RIL_UICCRECORDTYPE_CYCLIC,
  RIL_UICCRECORDTYPE_LINEAR,
  RIL_UICCRECORDTYPE_BERTLV,
  RIL_UICCRECORDTYPE_MASTER,
  RIL_UICCRECORDTYPE_DEDICATED,
  RIL_UICCRECORDTYPE_MAX
} RILUICCRECORDTYPE;
```


## -enum-fields




### -field RIL_UICCRECORDTYPE_UNKNOWN


### -field RIL_UICCRECORDTYPE_TRANSPARENT


### -field RIL_UICCRECORDTYPE_CYCLIC


### -field RIL_UICCRECORDTYPE_LINEAR


### -field RIL_UICCRECORDTYPE_BERTLV


### -field RIL_UICCRECORDTYPE_MASTER


### -field RIL_UICCRECORDTYPE_DEDICATED


### -field RIL_UICCRECORDTYPE_MAX

