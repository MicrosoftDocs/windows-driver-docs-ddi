---
UID: NS:windot11.DOT11_KEY_ALGO_BIP
title: DOT11_KEY_ALGO_BIP (windot11.h)
description: The DOT11_KEY_ALGO_BIP structure defines a cipher key that is used by the Broadcast Integrity Protocol (BIP) algorithm for management frame integrity protection.
old-location: netvista\dot11_key_algo_bip.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_KEY_ALGO_BIP structure"]
ms.keywords: "*PDOT11_KEY_ALGO_BIP, DOT11_KEY_ALGO_BIP, DOT11_KEY_ALGO_BIP structure [Network Drivers Starting with Windows Vista], PDOT11_KEY_ALGO_BIP, PDOT11_KEY_ALGO_BIP structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_key_algo_bip, windot11/DOT11_KEY_ALGO_BIP, windot11/PDOT11_KEY_ALGO_BIP"
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
targetos: Windows
req.typenames: DOT11_KEY_ALGO_BIP, *PDOT11_KEY_ALGO_BIP
f1_keywords:
 - DOT11_KEY_ALGO_BIP
 - windot11/DOT11_KEY_ALGO_BIP
 - PDOT11_KEY_ALGO_BIP
 - windot11/PDOT11_KEY_ALGO_BIP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_KEY_ALGO_BIP
 - PDOT11_KEY_ALGO_BIP
---

# DOT11_KEY_ALGO_BIP structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_KEY_ALGO_BIP structure defines a cipher key that is used by the Broadcast Integrity Protocol (BIP) algorithm for management frame integrity protection.

## -struct-fields

### -field ucIPN

### -field ulBIPKeyLength

The length, in bytes, of the BIP key material in <b>ucBIPKey</b> array.

### -field ucBIPKey

The BIP key material.


### -field ucIPN

The initial IGTK packet number (IPN) used for replay protection.

## -syntax

```cpp
typedef struct _DOT11_KEY_ALGO_BIP {
  UCHAR ucIPN[6];
  ULONG ulBIPKeyLength;
  UCHAR ucBIPKey[1];
} DOT11_KEY_ALGO_BIP, *PDOT11_KEY_ALGO_BIP;
```

