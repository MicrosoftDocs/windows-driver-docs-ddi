---
UID: NS:rilapitypes.RILOPERATORNAMES
title: RILOPERATORNAMES (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riloperatornames_2.htm
tech.root: netvista
ms.assetid: 5a066e35-1e8c-431e-897f-9d864991b15f
ms.date: 02/26/2018
ms.keywords: "*LPRILOPERATORNAMES, RILOPERATORNAMES, RILOPERATORNAMES structure [Network Drivers Starting with Windows Vista], netvista.riloperatornames_2, rilapitypes/RILOPERATORNAMES"
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
-	RILOPERATORNAMES
product:
- Windows
targetos: Windows
req.typenames: RILOPERATORNAMES, *LPRILOPERATORNAMES
req.product: Windows 10 or later.
---

# RILOPERATORNAMES structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef struct _RILOPERATORNAMES {
  DWORD                                   cbSize;
  DWORD                                   dwParams;
  DWORD                                   dwSystemType;
  WCHAR [MAXLENGTH_OPERATOR_LONG]         wszLongName;
  WCHAR [MAXLENGTH_OPERATOR_SHORT]        wszShortName;
  WCHAR [MAXLENGTH_OPERATOR_NUMERIC]      wszNumName;
  WCHAR [MAXLENGTH_OPERATOR_COUNTRY_CODE] wszCountryCode;
} RILOPERATORNAMES, RILOPERATORNAMES;
```


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwSystemType


### -field wszLongName


### -field wszShortName


### -field wszNumName


### -field wszCountryCode

