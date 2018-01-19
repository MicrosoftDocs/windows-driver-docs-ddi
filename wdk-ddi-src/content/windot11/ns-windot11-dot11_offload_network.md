---
UID: NS:windot11.DOT11_OFFLOAD_NETWORK
title: DOT11_OFFLOAD_NETWORK
author: windows-driver-content
description: The DOT11_OFFLOAD_NETWORK structure describes a network list offload.
old-location: netvista\dot11_offload_network.htm
old-project: netvista
ms.assetid: 75DC558F-801B-42ED-9282-127E86E78923
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_OFFLOAD_NETWORK, DOT11_OFFLOAD_NETWORK, *PDOT11_OFFLOAD_NETWORK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_OFFLOAD_NETWORK
req.alt-loc: Windot11.h
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
req.typenames: DOT11_OFFLOAD_NETWORK, *PDOT11_OFFLOAD_NETWORK
req.product: Windows 10 or later.
---

# DOT11_OFFLOAD_NETWORK structure



## -description

## -syntax

````
typedef struct _DOT11_OFFLOAD_NETWORK {
  DOT11_SSID             Ssid;
  DOT11_CIPHER_ALGORITHM UnicastCipher;
  DOT11_AUTH_ALGORITHM   AuthAlgo;
  DOT11_CHANNEL_HINT     Dot11ChannelHints[DOT11_MAX_CHANNEL_HINTS];
} DOT11_OFFLOAD_NETWORK, *PDOT11_OFFLOAD_NETWORK;
````


## -struct-fields

### -field Ssid

SSID interface.


### -field UnicastCipher

Cipher algorithm for data encryption and decryption.


### -field AuthAlgo

Wireless LAN authentication algorithm.


### -field Dot11ChannelHints[DOT11_MAX_CHANNEL_HINTS]

Array of hints listing 802.11 PHY and media types and channels.


## -remarks
