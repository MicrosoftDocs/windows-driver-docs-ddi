---
UID: NE:rilapitypes.RILADDRESSNUMPLAN
title: RILADDRESSNUMPLAN (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdressnumplan_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILADDRESSNUMPLAN enumeration"]
ms.keywords: RILADDRESSNUMPLAN, RILADDRESSNUMPLAN enumeration [Network Drivers Starting with Windows Vista], RIL_NUMPLAN_DATA, RIL_NUMPLAN_ERMES, RIL_NUMPLAN_MAX, RIL_NUMPLAN_NATIONAL, RIL_NUMPLAN_PRIVATE, RIL_NUMPLAN_TELEPHONE, RIL_NUMPLAN_TELEX, netvista.riladdressnumplan_2, rilapitypes/RILADDRESSNUMPLAN, rilapitypes/RIL_NUMPLAN_DATA, rilapitypes/RIL_NUMPLAN_ERMES, rilapitypes/RIL_NUMPLAN_MAX, rilapitypes/RIL_NUMPLAN_NATIONAL, rilapitypes/RIL_NUMPLAN_PRIVATE, rilapitypes/RIL_NUMPLAN_TELEPHONE, rilapitypes/RIL_NUMPLAN_TELEX
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
req.typenames: RILADDRESSNUMPLAN
req.product: Windows 10 or later.
f1_keywords:
 - RILADDRESSNUMPLAN
 - rilapitypes/RILADDRESSNUMPLAN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILADDRESSNUMPLAN
---

# RILADDRESSNUMPLAN enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_NUMPLAN_UNKNOWN

### -field RIL_NUMPLAN_TELEPHONE

### -field RIL_NUMPLAN_DATA

### -field RIL_NUMPLAN_TELEX

### -field RIL_NUMPLAN_NATIONAL

### -field RIL_NUMPLAN_PRIVATE

### -field RIL_NUMPLAN_ERMES

### -field RIL_NUMPLAN_MAX

## -syntax

```cpp
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

