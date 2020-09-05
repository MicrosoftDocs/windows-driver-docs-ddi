---
UID: NS:ntddrilapitypes.RILPOSITIONINFOTDSCDMA
title: RILPOSITIONINFOTDSCDMA (ntddrilapitypes.h)
description: This structure represents the RILPOSITIONINFOTDSCDMA.
old-location: netvista\rilpositioninfotdscdma.htm
tech.root: netvista
ms.assetid: 0b7b2592-8a67-4eb0-8e87-354fd5f215c5
ms.date: 02/16/2018
keywords: ["RILPOSITIONINFOTDSCDMA structure"]
ms.keywords: "*LPRILPOSITIONINFOTDSCDMA, RILPOSITIONINFOTDSCDMA, RILPOSITIONINFOTDSCDMA structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfotdscdma, rilapitypes/RILPOSITIONINFOTDSCDMA"
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
targetos: Windows
req.typenames: RILPOSITIONINFOTDSCDMA, *LPRILPOSITIONINFOTDSCDMA
f1_keywords:
 - RILPOSITIONINFOTDSCDMA
 - ntddrilapitypes/RILPOSITIONINFOTDSCDMA
 - LPRILPOSITIONINFOTDSCDMA
 - ntddrilapitypes/LPRILPOSITIONINFOTDSCDMA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFOTDSCDMA
---

# RILPOSITIONINFOTDSCDMA structure (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents the RILPOSITIONINFOTDSCDMA.

## -struct-fields

### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilpositioninfotdscdmaparammask.md">RILPOSITIONINFOTDSCDMAPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set

### -field dwMobileCountryCode

Mobile country code (0...999).

### -field dwMobileNetworkCode

Mobile Network Code (0...999).

### -field dwLocationAreaCode

Location Area Code (0...65535).

### -field dwCellID

Cell ID (0...268435455)).

### -field dwUARFCN

Channel number for serving cell (0...16383).

### -field dwCellParameterID

Cell parameter ID (0...127).

### -field dwTimingAdvance

Timing Advance (0...1023), same value for all timeslots.

### -field dwRSCP

Received signal code power of serving cell. Range (−128...−25) in units of 1dBm in Q8 L3 filtered.

### -field dwPathLoss

Path loss of serving cell (46...158).

## -syntax

```cpp
struct RILPOSITIONINFOTDSCDMA {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwUARFCN;
  DWORD dwCellParameterID;
  DWORD dwTimingAdvance;
  LONG  dwRSCP;
  DWORD dwPathLoss;
};
```

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>

