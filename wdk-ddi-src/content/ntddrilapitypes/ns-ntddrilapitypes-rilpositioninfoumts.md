---
UID: NS:ntddrilapitypes.RILPOSITIONINFOUMTS
title: RILPOSITIONINFOUMTS
author: windows-driver-content
description: This structure represents a RILPOSITIONINFOUMTS.
old-location: netvista\rilpositioninfoumts.htm
old-project: netvista
ms.assetid: c17760c4-6f75-41e8-84a5-f13e26735af5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILPOSITIONINFOUMTS, ,, F, I, L, M, N, O, P, R, RILPOSITIONINFOUMTS, RILPOSITIONINFOUMTS structure [Network Drivers Starting with Windows Vista], S, T, U, netvista.rilpositioninfoumts, rilapitypes/RILPOSITIONINFOUMTS"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILPOSITIONINFOUMTS
product: Windows
targetos: Windows
req.typenames: RILPOSITIONINFOUMTS, *LPRILPOSITIONINFOUMTS
---

# RILPOSITIONINFOUMTS structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILPOSITIONINFOUMTS.


## -syntax


````
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
````


## -struct-fields




### -field dwParams

A bitwise combination of <a href="..\ntddrilapitypes\ne-ntddrilapitypes-rilpositioninfoumtsparammask.md">RILPOSITIONINFOUMTSPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


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


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILPOSITIONINFOUMTS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

