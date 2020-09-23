---
UID: NS:ntddrilapitypes.RILNETWORKCODE
title: RILNETWORKCODE (ntddrilapitypes.h)
description: This structure represents a RILNETWORKCODE.
old-location: netvista\rilnetworkcode.htm
tech.root: netvista
ms.assetid: b0fa761c-8e28-4067-ae9e-d39e2853fb05
ms.date: 02/16/2018
keywords: ["RILNETWORKCODE structure"]
ms.keywords: "*LPRILNETWORKCODE, RILNETWORKCODE, RILNETWORKCODE structure [Network Drivers Starting with Windows Vista], netvista.rilnetworkcode, rilapitypes/RILNETWORKCODE"
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
req.typenames: RILNETWORKCODE, *LPRILNETWORKCODE
f1_keywords:
 - RILNETWORKCODE
 - ntddrilapitypes/RILNETWORKCODE
 - LPRILNETWORKCODE
 - ntddrilapitypes/LPRILNETWORKCODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILNETWORKCODE
---

# RILNETWORKCODE structure (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILNETWORKCODE.

## -struct-fields

### -field cbSize

The size of the structure in bytes.

### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilnetworkcodeparammask.md">RILNETWORKCODEPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

### -field dwExecutor

This field is unused.

### -field dwMCC

Mobile Country Code, if applicable. For RIL_SYSTEMTYPE_1XRTT and RIL_SYSTEMTYPE_EVDO it is network-dependent whether this value is available; further, the MCC provided by some 3GPP2 networks may not be accurate.

### -field dwMNC

Mobile Network Code. For RIL_SYSTEMTYPE_1XRTT and RIL_SYSTEMTYPE_EVDO it is network-dependent whether this value is available; further, the MCC provided by some 3GPP2 networks may not be accurate.

### -field dwSID

System ID, if applicable. This is available only for RIL_SYSTEMTYPE_1XRTT.

### -field dwNID

Network ID, if applicable. This is available only for RIL_SYSTEMTYPE_1XRTT.

### -field dwRI

Roaming indicator, if applicable. This is available only for RIL_SYSTEMTYPE_1XRTT and RIL_SYSTEMTYPE_EVDO.

## -syntax

```cpp
struct RILNETWORKCODE {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwExecutor;
  DWORD dwMCC;
  DWORD dwMNC;
  DWORD dwSID;
  DWORD dwNID;
  DWORD dwRI;
};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>