---
UID: NS:ntddrilapitypes.RILPOSITIONINFOLTE
title: RILPOSITIONINFOLTE
author: windows-driver-content
description: This structure represents the RILPOSITIONINFOLTE.
old-location: netvista\rilpositioninfolte.htm
tech.root: netvista
ms.assetid: 40f4dfca-7ee6-48d2-b0a4-8a563587b2ab
ms.date: 02/16/2018
ms.keywords: "*LPRILPOSITIONINFOLTE, RILPOSITIONINFOLTE, RILPOSITIONINFOLTE structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfolte, rilapitypes/RILPOSITIONINFOLTE"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILPOSITIONINFOLTE
product:
- Windows
targetos: Windows
req.typenames: RILPOSITIONINFOLTE, *LPRILPOSITIONINFOLTE
---

# RILPOSITIONINFOLTE structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents the RILPOSITIONINFOLTE.


## -syntax


```cpp
struct RILPOSITIONINFOLTE {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwCellID;
  DWORD dwEARFCN;
  DWORD dwPhysCellID;
  DWORD dwTAC;
  DWORD dwRSRP;
  DWORD dwRSRQ;
  DWORD dwTimingAdvance;
};
```


## -struct-fields




### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilpositioninfolteparammask.md">RILPOSITIONINFOLTEPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwMobileCountryCode

Mobile country code (0...999)


### -field dwMobileNetworkCode

Mobile Network Code (0...999)


### -field dwCellID

Cell identity (28 bits)


### -field dwEARFCN

Radio Frequency Channel Number of serving cell (0...65535)


### -field dwPhysCellID

Physical CellID (0...503)


### -field dwTAC

Tracking area code (0...65535)


### -field dwRSRP

Average Reference Signal Received Power. Range (-1400 ... -440) in units of 0.1dBm.


### -field dwRSRQ

Average Reference Signal Received Quality. Range (-200 ... -30) in units of 0.1dBm.


### -field dwTimingAdvance

Timing Advance (0...255) in bit periods, where a bit period is 48/13µs


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 


