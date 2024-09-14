---
UID: NS:windot11.DOT11_OFFLOAD_NETWORK
title: DOT11_OFFLOAD_NETWORK (windot11.h)
description: The DOT11_OFFLOAD_NETWORK structure describes a network list offload.
old-location: netvista\dot11_offload_network.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_OFFLOAD_NETWORK structure"]
ms.keywords: "*PDOT11_OFFLOAD_NETWORK, DOT11_OFFLOAD_NETWORK, DOT11_OFFLOAD_NETWORK structure [Network Drivers Starting with Windows Vista], PDOT11_OFFLOAD_NETWORK, PDOT11_OFFLOAD_NETWORK structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_offload_network, windot11/DOT11_OFFLOAD_NETWORK, windot11/PDOT11_OFFLOAD_NETWORK"
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
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
req.typenames: DOT11_OFFLOAD_NETWORK, *PDOT11_OFFLOAD_NETWORK
f1_keywords:
 - DOT11_OFFLOAD_NETWORK
 - windot11/DOT11_OFFLOAD_NETWORK
 - PDOT11_OFFLOAD_NETWORK
 - windot11/PDOT11_OFFLOAD_NETWORK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - DOT11_OFFLOAD_NETWORK
 - PDOT11_OFFLOAD_NETWORK
---

# DOT11_OFFLOAD_NETWORK structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_OFFLOAD_NETWORK structure describes a network list offload.

## -struct-fields

### -field Ssid

SSID interface.

### -field UnicastCipher

Cipher algorithm for data encryption and decryption.

### -field AuthAlgo

Wireless LAN authentication algorithm.

### -field Dot11ChannelHints

Array of hints listing 802.11 PHY and media types and channels.

## -syntax

```cpp
typedef struct _DOT11_OFFLOAD_NETWORK {
  DOT11_SSID             Ssid;
  DOT11_CIPHER_ALGORITHM UnicastCipher;
  DOT11_AUTH_ALGORITHM   AuthAlgo;
  DOT11_CHANNEL_HINT     Dot11ChannelHints[DOT11_MAX_CHANNEL_HINTS];
} DOT11_OFFLOAD_NETWORK, *PDOT11_OFFLOAD_NETWORK;
```

