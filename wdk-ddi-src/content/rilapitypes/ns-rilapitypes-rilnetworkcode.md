---
UID: NS:rilapitypes.RILNETWORKCODE
title: RILNETWORKCODE
author: windows-driver-content
description: This structure represents a RILNETWORKCODE.
old-location: netvista\rilnetworkcode.htm
old-project: netvista
ms.assetid: b0fa761c-8e28-4067-ae9e-d39e2853fb05
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILNETWORKCODE, rilapitypes/RILNETWORKCODE, RILNETWORKCODE structure [Network Drivers Starting with Windows Vista], RILNETWORKCODE, netvista.rilnetworkcode"
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
-	RILNETWORKCODE
product: Windows
targetos: Windows
req.typenames: "*LPRILNETWORKCODE, RILNETWORKCODE"
req.product: Windows 10 or later.
---

# RILNETWORKCODE structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILNETWORKCODE.


## -syntax


````
struct RILNETWORKCODE {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwExecutor;
  DWORD dwMCC;
  DWORD dwMNC;
  DWORD dwSID;
  DWORD dwNID;
  DWORD dwRI;
};
````


## -struct-fields




### -field cbSize

The size of the structure in bytes.


### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilnetworkcodeparammask.md">RILNETWORKCODEPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwExecutor

This field is unused.


### -field dwMCC

Mobile Country Code, if applicable. For RIL_SYSTEMTYPE_1XRTT and RIL_SYSTEMTYPE_EVDO it is network-dependent whether this value is available; further, the MCC provided by some 3GPP2 networks may not be accurate.


### -field dwMNC

Mobile Network Code. For RIL_SYSTEMTYPE_1XRTT and RIL_SYSTEMTYPE_EVDO it is network-dependent whether this value is available; further, the MCC provided by some 3GPP2 networks may not be accurate.


### -field dwSID

System ID, if applicable. This is available only for RIL_SYSTEMTYPE_1XRTT.


### -field dwNID

Network ID, if applicable. This is available only for RIL_SYSTEMTYPE_1XRTT.


### -field dwRI

Roaming indicator, if applicable. This is available only for RIL_SYSTEMTYPE_1XRTT and RIL_SYSTEMTYPE_EVDO.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILNETWORKCODE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

