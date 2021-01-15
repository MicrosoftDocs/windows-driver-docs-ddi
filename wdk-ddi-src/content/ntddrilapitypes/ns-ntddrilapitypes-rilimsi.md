---
UID: NS:ntddrilapitypes.RILIMSI
title: RILIMSI (ntddrilapitypes.h)
description: This structure represents a RILIMSI.
old-location: netvista\rilimsi.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["RILIMSI structure"]
ms.keywords: "*LPRILIMSI, RILIMSI, RILIMSI structure [Network Drivers Starting with Windows Vista], netvista.rilimsi, rilapitypes/RILIMSI"
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
req.typenames: RILIMSI, *LPRILIMSI
f1_keywords:
 - RILIMSI
 - ntddrilapitypes/RILIMSI
 - LPRILIMSI
 - ntddrilapitypes/LPRILIMSI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILIMSI
 - LPRILIMSI
---

# RILIMSI structure (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILIMSI.

<code>const int MAXLENGTH_IMSI = 16</code>

## -struct-fields

### -field cbSize

The size of the structure in bytes.

### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilimsiparammask.md">RILIMSIPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

### -field wszImsi

The IMSI as a null-terminated Unicode string.

### -field dwMcc

The mobile country code from the IMSI.

### -field dwMnc

The mobile network code from the IMSI.

## -syntax

```cpp
struct RILIMSI {
  DWORD cbSize;
  DWORD dwParams;
  WCHAR wszImsi[MAXLENGTH_IMSI];
  DWORD dwMcc;
  DWORD dwMnc;
};
```

## -remarks

The RIL driver is responsible for determining whether the MNC comprises two or three digits and extracting it accordingly. (For 3GPP, the number of digits in the MNC is specified by the fourth byte of EFAD as specified in 3GPP TS 31.102 section 4.2.18.)

For 3GPP2, the IMSI_T is returned if it is programmed; otherwise, the IMSI_M is returned. For the IMSI_T, dwMcc contains the MCC_Tp and dwMnc contains IMSI_T_11_12p. For the IMSI_M, dwMcc contains the MCC_Mp and dwMnc is not defined (that is, the RIL_PARAM_IMSI_MNC bit in dwParams is 0).

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>

