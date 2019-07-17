---
UID: NS:ntddrilapitypes.RILTDSCDMAMRL
title: RILTDSCDMAMRL (ntddrilapitypes.h)
description: This structure represents RILTDSCDMAMRL, which is a TD_SCDMA network measurement report.
old-location: netvista\riltdscdmamrl.htm
tech.root: netvista
ms.assetid: 26399c62-c17a-40ad-964e-144badc55614
ms.date: 02/16/2018
ms.keywords: "*LPRILTDSCDMAMRL, RILTDSCDMAMRL, RILTDSCDMAMRL structure [Network Drivers Starting with Windows Vista], netvista.riltdscdmamrl, rilapitypes/RILTDSCDMAMRL"
ms.topic: struct
f1_keywords:
 - "ntddrilapitypes/RILTDSCDMAMRL"
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
- RILTDSCDMAMRL
product:
- Windows
targetos: Windows
req.typenames: RILTDSCDMAMRL, *LPRILTDSCDMAMRL
---

# RILTDSCDMAMRL structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILTDSCDMAMRL, which is a TD_SCDMA network measurement report.


## -syntax


```cpp
struct RILTDSCDMAMRL {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwUARFCN;
  DWORD dwCellParameterID;
  DWORD dwRSCP;
  DWORD dwPathLoss;
};
```


## -struct-fields




### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-riltdscdmamrlparammask.md">RILTDSCDMAMRLPARAMMASK</a> that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwMobileCountryCode

(Reserved for future use) Mobile country code (0...999).


### -field dwMobileNetworkCode

(Reserved for future use) Mobile Network Code (0...999).


### -field dwLocationAreaCode

(Reserved for future use) Location Area Code (0...65535).


### -field dwCellID

(Reserved for future use) Cell identity 28 bits (0...268435455).


### -field dwUARFCN

Channel number (0...16383).


### -field dwCellParameterID

Cell parameter ID (0...127).


### -field dwRSCP

Received signal code power of serving cell. Range −128...−25 in units of 1dBm in Q8 L3 filtered.


### -field dwPathLoss

Path loss of serving cell (46...173)


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>



 

 


