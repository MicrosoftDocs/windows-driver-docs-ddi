---
UID: NS:windot11.DOT11_KEY_ALGO_BIP
title: DOT11_KEY_ALGO_BIP
author: windows-driver-content
description: The DOT11_KEY_ALGO_BIP structure defines a cipher key that is used by the Broadcast Integrity Protocol (BIP) algorithm for management frame integrity protection.
old-location: netvista\dot11_key_algo_bip.htm
tech.root: netvista
ms.assetid: 608AD247-19C8-40E8-B2FF-D49818AE4AD7
ms.date: 2/16/2018
ms.keywords: "*PDOT11_KEY_ALGO_BIP, DOT11_KEY_ALGO_BIP, DOT11_KEY_ALGO_BIP structure [Network Drivers Starting with Windows Vista], PDOT11_KEY_ALGO_BIP, PDOT11_KEY_ALGO_BIP structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_key_algo_bip, windot11/DOT11_KEY_ALGO_BIP, windot11/PDOT11_KEY_ALGO_BIP"
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of the Windows operating   systems.
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
-	windot11.h
api_name:
-	DOT11_KEY_ALGO_BIP
product:
- Windows
targetos: Windows
req.typenames: DOT11_KEY_ALGO_BIP, *PDOT11_KEY_ALGO_BIP
product:
- Windows 10 or later.
---

# DOT11_KEY_ALGO_BIP structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_KEY_ALGO_BIP structure defines a cipher key that is used by the Broadcast Integrity Protocol (BIP) algorithm for management frame integrity protection.


## -syntax


```cpp
typedef struct _DOT11_KEY_ALGO_BIP {
  UCHAR ucIPN[6];
  ULONG ulBIPKeyLength;
  UCHAR ucBIPKey[1];
} DOT11_KEY_ALGO_BIP, *PDOT11_KEY_ALGO_BIP;
```


## -struct-fields




### -field ucIPN




### -field ulBIPKeyLength

The length, in bytes, of the BIP key material in <b>ucBIPKey</b> array.


### -field ucBIPKey






#### - ucBIPKey[1]

The BIP key material.


#### - ucIPN[6]

The initial IGTK packet number (IPN) used for replay protection.

