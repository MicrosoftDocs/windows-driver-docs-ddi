---
UID: NS:ntddrilapitypes.RILUMTSMRL
title: RILUMTSMRL (ntddrilapitypes.h)
description: This structure represents a RILUMTSMRL.
old-location: netvista\rilumtsmrl.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["RILUMTSMRL structure"]
ms.keywords: "*LPRILUMTSMRL, RILUMTSMRL, RILUMTSMRL structure [Network Drivers Starting with Windows Vista], netvista.rilumtsmrl, rilapitypes/RILUMTSMRL"
req.header: ntddrilapitypes.h
req.include-header: Ntddrilapitypes.h
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
req.typenames: RILUMTSMRL, *LPRILUMTSMRL
f1_keywords:
 - RILUMTSMRL
 - ntddrilapitypes/RILUMTSMRL
 - LPRILUMTSMRL
 - ntddrilapitypes/LPRILUMTSMRL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUMTSMRL
---

# RILUMTSMRL structure (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILUMTSMRL.

## -struct-fields

### -field dwParams

 A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilumtsmrlparammask.md">RILUMTSMRLPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

### -field dwMobileCountryCode

Country code (0...999)

### -field dwMobileNetworkCode

Mobile network code (0...999)

### -field dwLocationAreaCode

Location area code (0...65535)

### -field dwCellID

UMTS cell ID (0...268435455)

### -field dwUARFCN

UTRA absolute radio frequency channel number (0...16383)

### -field dwPrimaryScramblingCode

Primary Scrambling Code (0...511)

### -field dwRSCP

Received signal code power of serving cell. Range (-1200 ... -250) in units of 0.1dBm, i.e., -250 represents -25dBm.

### -field dwECNO

Signal to noise ratio of serving cell; the ratio of the received energy per PN chip for the CPICH to the total received power spectral density at the antenna. Range (-500...0) in units of 0.1dBm.

### -field dwPathLoss

Path loss.

## -syntax

```cpp
struct RILUMTSMRL {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwUARFCN;
  DWORD dwPrimaryScramblingCode;
  LONG  dwRSCP;
  LONG  dwECNO;
  DWORD dwPathLoss;
};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>
