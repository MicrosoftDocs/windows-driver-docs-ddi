---
UID: NS:ntddrilapitypes.RILUMTSMRL
title: RILUMTSMRL
author: windows-driver-content
description: This structure represents a RILUMTSMRL.
old-location: netvista\rilumtsmrl.htm
old-project: netvista
ms.assetid: 72567e37-f37f-43f6-8a3a-3d184cb8de13
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILUMTSMRL, RILUMTSMRL, RILUMTSMRL structure [Network Drivers Starting with Windows Vista], netvista.rilumtsmrl, rilapitypes/RILUMTSMRL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILUMTSMRL
product:
- Windows
targetos: Windows
req.typenames: RILUMTSMRL, *LPRILUMTSMRL
---

# RILUMTSMRL structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILUMTSMRL.


## -syntax


````
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
````


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


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 


