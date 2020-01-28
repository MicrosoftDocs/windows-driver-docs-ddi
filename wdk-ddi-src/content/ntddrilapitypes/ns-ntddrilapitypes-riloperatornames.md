---
UID: NS:ntddrilapitypes.RILOPERATORNAMES
title: RILOPERATORNAMES (ntddrilapitypes.h)
description: This structure represents the RILOPERATORNAMES.
old-location: netvista\riloperatornames.htm
tech.root: netvista
ms.assetid: 2813c28c-e964-44ee-9995-15aa563c43d0
ms.date: 02/16/2018
ms.keywords: "*LPRILOPERATORNAMES, RILOPERATORNAMES, RILOPERATORNAMES structure [Network Drivers Starting with Windows Vista], netvista.riloperatornames, rilapitypes/RILOPERATORNAMES"
f1_keywords:
 - "ntddrilapitypes/RILOPERATORNAMES"
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
- RILOPERATORNAMES
product:
- Windows
targetos: Windows
req.typenames: RILOPERATORNAMES, *LPRILOPERATORNAMES
---

# RILOPERATORNAMES structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents the RILOPERATORNAMES.


## -syntax


```cpp
struct RILOPERATORNAMES {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwSystemType;
  WCHAR wszLongName[MAXLENGTH_OPERATOR_LONG];
  WCHAR wszShortName[MAXLENGTH_OPERATOR_SHORT];
  WCHAR wszNumName[MAXLENGTH_OPERATOR_NUMERIC];
  WCHAR wszCountryCode[MAXLENGTH_OPERATOR_COUNTRY_CODE];
};
```


## -struct-fields




### -field cbSize

The size of the structure in bytes.


### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-riloperatornamesparammask.md">RILOPERATORNAMESPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwSystemType

Must specify one and only one system type.


### -field wszLongName


### -field wszShortName


### -field wszNumName


### -field wszCountryCode

Mobile country code


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>



 

 


