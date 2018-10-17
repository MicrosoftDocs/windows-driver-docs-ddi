---
UID: NE:rilapitypes.RILADDRESSNUMPLAN
title: RILADDRESSNUMPLAN
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdressnumplan_2.htm
tech.root: netvista
ms.assetid: 14c0f786-4616-49f1-aa9c-0e5c8d4f0197
ms.date: 2/26/2018
ms.keywords: RILADDRESSNUMPLAN, RILADDRESSNUMPLAN enumeration [Network Drivers Starting with Windows Vista], RIL_NUMPLAN_DATA, RIL_NUMPLAN_ERMES, RIL_NUMPLAN_MAX, RIL_NUMPLAN_NATIONAL, RIL_NUMPLAN_PRIVATE, RIL_NUMPLAN_TELEPHONE, RIL_NUMPLAN_TELEX, netvista.riladdressnumplan_2, rilapitypes/RILADDRESSNUMPLAN, rilapitypes/RIL_NUMPLAN_DATA, rilapitypes/RIL_NUMPLAN_ERMES, rilapitypes/RIL_NUMPLAN_MAX, rilapitypes/RIL_NUMPLAN_NATIONAL, rilapitypes/RIL_NUMPLAN_PRIVATE, rilapitypes/RIL_NUMPLAN_TELEPHONE, rilapitypes/RIL_NUMPLAN_TELEX
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
-	RILADDRESSNUMPLAN
product:
- Windows
targetos: Windows
req.typenames: RILADDRESSNUMPLAN
req.product: Windows 10 or later.
---

# RILADDRESSNUMPLAN enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```
typedef enum _RILADDRESSNUMPLAN {
  RIL_NUMPLAN_TELEPHONE,
  RIL_NUMPLAN_DATA,
  RIL_NUMPLAN_TELEX,
  RIL_NUMPLAN_NATIONAL,
  RIL_NUMPLAN_PRIVATE,
  RIL_NUMPLAN_ERMES,
  RIL_NUMPLAN_MAX
} RILADDRESSNUMPLAN;
```


## -enum-fields




### -field RIL_NUMPLAN_UNKNOWN


### -field RIL_NUMPLAN_TELEPHONE


### -field RIL_NUMPLAN_DATA


### -field RIL_NUMPLAN_TELEX


### -field RIL_NUMPLAN_NATIONAL


### -field RIL_NUMPLAN_PRIVATE


### -field RIL_NUMPLAN_ERMES


### -field RIL_NUMPLAN_MAX

