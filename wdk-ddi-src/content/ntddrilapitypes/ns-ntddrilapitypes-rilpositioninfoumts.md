---
UID: NS:ntddrilapitypes.RILPOSITIONINFOUMTS
title: RILPOSITIONINFOUMTS (ntddrilapitypes.h)
description: This structure represents a RILPOSITIONINFOUMTS.
old-location: netvista\rilpositioninfoumts.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["RILPOSITIONINFOUMTS structure"]
ms.keywords: "*LPRILPOSITIONINFOUMTS, RILPOSITIONINFOUMTS, RILPOSITIONINFOUMTS structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfoumts, rilapitypes/RILPOSITIONINFOUMTS"
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
req.typenames: RILPOSITIONINFOUMTS, *LPRILPOSITIONINFOUMTS
f1_keywords:
 - RILPOSITIONINFOUMTS
 - ntddrilapitypes/RILPOSITIONINFOUMTS
 - LPRILPOSITIONINFOUMTS
 - ntddrilapitypes/LPRILPOSITIONINFOUMTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFOUMTS
---

# RILPOSITIONINFOUMTS structure (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILPOSITIONINFOUMTS.

## -struct-fields

### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilpositioninfoumtsparammask.md">RILPOSITIONINFOUMTSPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

### -field dwMobileCountryCode

Mobile country code (0...999).

### -field dwMobileNetworkCode

Mobile Network Code (0...999).

### -field dwLocationAreaCode

Location Area Code (0...65535).

### -field dwCellID

Cell ID (0...268435455)).

### -field dwFrequencyInfoUL

Channel number for serving cell (0...16383).

### -field dwFrequencyInfoDL

Frequency Info Downlink (0...16383)

### -field dwFrequencyInfoNT

Frequency Info for TDD (0...16383)

### -field dwUARFCN

UTRA Absolute Radio Frequency Channel Number for serving cell (0...16383)

### -field dwPrimaryScramblingCode

Primary scrambling code of serving cell (0...511)

### -field dwRSCP

Received signal code power of serving cell. Range (-1200 ... -250) in units of .1dBm, i.e., -250 represents -25dBm.

### -field dwECNO

Signal to noise ratio of serving cell; the ratio of the received energy per PN chip for the CPICH to the total received power spectral density at the antenna. Range (-500…0) in units of 0.1dBm.

### -field dwPathLoss

Path loss of serving cell (46...173)

## -syntax

```cpp
struct RILPOSITIONINFOUMTS {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwFrequencyInfoUL;
  DWORD dwFrequencyInfoDL;
  DWORD dwFrequencyInfoNT;
  DWORD dwUARFCN;
  DWORD dwPrimaryScramblingCode;
  DWORD dwRSCP;
  DWORD dwECNO;
  DWORD dwPathLoss;
};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>
