---
UID: NS:rilapitypes.RILUMTSMRL
title: RILUMTSMRL
author: windows-driver-content
description: This structure represents a RILUMTSMRL.
old-location: netvista\rilumtsmrl.htm
old-project: netvista
ms.assetid: 72567e37-f37f-43f6-8a3a-3d184cb8de13
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILUMTSMRL, ,, I, L, M, P, R, RILUMTSMRL, RILUMTSMRL structure [Network Drivers Starting with Windows Vista], S, T, U, netvista.rilumtsmrl, rilapitypes/RILUMTSMRL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILUMTSMRL
product: Windows
targetos: Windows
req.typenames: RILUMTSMRL, *LPRILUMTSMRL
req.product: Windows 10 or later.
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

 A bitwise combination of <a href="..\ntddrilapitypes\ne-ntddrilapitypes-rilumtsmrlparammask.md">RILUMTSMRLPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUMTSMRL structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

