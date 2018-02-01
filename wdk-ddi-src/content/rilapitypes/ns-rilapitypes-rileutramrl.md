---
UID: NS:rilapitypes.RILEUTRAMRL
title: RILEUTRAMRL
author: windows-driver-content
description: This structure represents RILEUTRAMRL, which is a EUTRA (LTE) network measurement report.
old-location: netvista\rileutramrl.htm
old-project: netvista
ms.assetid: 2dd695c4-ed3e-4278-b82e-6643aaded890
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILEUTRAMRL, netvista.rileutramrl, RILEUTRAMRL structure [Network Drivers Starting with Windows Vista], *LPRILEUTRAMRL, rilapitypes/RILEUTRAMRL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	RILEUTRAMRL
product: Windows
targetos: Windows
req.typenames: "*LPRILEUTRAMRL, RILEUTRAMRL"
req.product: Windows 10 or later.
---

# RILEUTRAMRL structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILEUTRAMRL, which is a EUTRA (LTE) network measurement report.


## -syntax


````
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
````


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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILEUTRAMRL structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

