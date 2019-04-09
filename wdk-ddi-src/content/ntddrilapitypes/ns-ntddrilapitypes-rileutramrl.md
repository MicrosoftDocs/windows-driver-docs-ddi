---
UID: NS:ntddrilapitypes.RILEUTRAMRL
title: RILEUTRAMRL (ntddrilapitypes.h)
description: This structure represents RILEUTRAMRL, which is a EUTRA (LTE) network measurement report.
old-location: netvista\rileutramrl.htm
tech.root: netvista
ms.assetid: 2dd695c4-ed3e-4278-b82e-6643aaded890
ms.date: 02/16/2018
ms.keywords: "*LPRILEUTRAMRL, RILEUTRAMRL, RILEUTRAMRL structure [Network Drivers Starting with Windows Vista], netvista.rileutramrl, rilapitypes/RILEUTRAMRL"
ms.topic: struct
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
- RILEUTRAMRL
product:
- Windows
targetos: Windows
req.typenames: RILEUTRAMRL, *LPRILEUTRAMRL
---

# RILEUTRAMRL structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILEUTRAMRL, which is a EUTRA (LTE) network measurement report.


## -syntax


```cpp
struct RILEUTRAMRL {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwCellID;
  DWORD dwEARFCN;
  DWORD dwPhysCellID;
  DWORD dwTAC;
  DWORD dwRSRP;
  DWORD dwRSRQ;
};
```


## -struct-fields




### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rileutramrlparammask.md">RILEUTRAMRLPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwMobileCountryCode

Mobile country code (0...999)


### -field dwMobileNetworkCode

Mobile Network Code (0...999)


### -field dwCellID

Cell identity (28 bits).


### -field dwEARFCN

EUTRA absolute radio frequency channel number (0...65535).


### -field dwPhysCellID

Physical cell ID (0...503).


### -field dwTAC

Tracking area code (0...65535).


### -field dwRSRP

Average reference signal received power (–1400 ... –440) in units of 0.1dBm.


### -field dwRSRQ

Average reference signal received quality (–200 ... –30) in units of 0.1dBm.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 


