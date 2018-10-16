---
UID: NE:rilapitypes.RILOPERATORNAMESPARAMMASK
title: RILOPERATORNAMESPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riloperatornamesparammask_2.htm
tech.root: netvista
ms.assetid: d91e6e66-ff0f-4e36-ba1b-bd7f502739d9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILOPERATORNAMESPARAMMASK, RILOPERATORNAMESPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_ON_ALL, RIL_PARAM_ON_COUNTRY_CODE, RIL_PARAM_ON_NUMNAME, RIL_PARAM_ON_SHORTNAME, RIL_PARAM_ON_SYSTEMTYPE, netvista.riloperatornamesparammask_2, rilapitypes/RILOPERATORNAMESPARAMMASK, rilapitypes/RIL_PARAM_ON_ALL, rilapitypes/RIL_PARAM_ON_COUNTRY_CODE, rilapitypes/RIL_PARAM_ON_NUMNAME, rilapitypes/RIL_PARAM_ON_SHORTNAME, rilapitypes/RIL_PARAM_ON_SYSTEMTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	RILOPERATORNAMESPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILOPERATORNAMESPARAMMASK
req.product: Windows 10 or later.
---

# RILOPERATORNAMESPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef enum _RILOPERATORNAMESPARAMMASK {
  RIL_PARAM_ON_SHORTNAME,
  RIL_PARAM_ON_NUMNAME,
  RIL_PARAM_ON_COUNTRY_CODE,
  RIL_PARAM_ON_SYSTEMTYPE,
  RIL_PARAM_ON_ALL
} RILOPERATORNAMESPARAMMASK;
```


## -enum-fields




### -field RIL_PARAM_ON_LONGNAME


### -field RIL_PARAM_ON_SHORTNAME


### -field RIL_PARAM_ON_NUMNAME


### -field RIL_PARAM_ON_COUNTRY_CODE


### -field RIL_PARAM_ON_SYSTEMTYPE


### -field RIL_PARAM_ON_ALL

