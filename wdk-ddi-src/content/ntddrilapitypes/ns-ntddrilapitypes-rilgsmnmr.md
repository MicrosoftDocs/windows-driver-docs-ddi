---
UID: NS:ntddrilapitypes.RILGSMNMR
title: RILGSMNMR
author: windows-driver-content
description: This structure represents RILGSMNMR, which is a GSM network measurement report.
old-location: netvista\rilgsmnmr.htm
tech.root: netvista
ms.assetid: 397d882d-c82a-4686-b9ca-58a2fade5256
ms.date: 02/16/2018
ms.keywords: "*LPRILGSMNMR, RILGSMNMR, RILGSMNMR structure [Network Drivers Starting with Windows Vista], netvista.rilgsmnmr, rilapitypes/RILGSMNMR"
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
-	RILGSMNMR
product:
- Windows
targetos: Windows
req.typenames: RILGSMNMR, *LPRILGSMNMR
---

# RILGSMNMR structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILGSMNMR, which is a GSM network measurement report.


## -syntax


```cpp
struct RILGSMNMR {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwARFCN;
  DWORD dwBaseStationID;
  DWORD dwRxLevel;
};
```


## -struct-fields




### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilgsmmnmrparammask.md">RILGSMMNMRPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwMobileCountryCode

Mobile country code (0...999)


### -field dwMobileNetworkCode

Mobile network code (0...999).


### -field dwLocationAreaCode

Location area code (0…65535)


### -field dwCellID

GSM Cell ID (0...65535)


### -field dwARFCN

Absolute radio frequency channel number of serving cell (0...1023)


### -field dwBaseStationID

Base station ID of serving cell (0..63)


### -field dwRxLevel

Received signal strength of serving cell (0...63) where:

(x=0, RSS &lt; -110dBm

x=63, RSS &gt; -49dBm

0 &lt;x &lt;63, -110+x &lt; RSS &lt; -109+x)


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 


