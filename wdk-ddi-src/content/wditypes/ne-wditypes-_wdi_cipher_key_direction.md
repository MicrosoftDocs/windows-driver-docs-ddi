---
UID: NE:wditypes._WDI_CIPHER_KEY_DIRECTION
title: _WDI_CIPHER_KEY_DIRECTION
author: windows-driver-content
description: The WDI_CIPHER_KEY_DIRECTION enumeration defines the traffic directions decrypted by a cipher key.
old-location: netvista\wdi_cipher_key_direction.htm
old-project: netvista
ms.assetid: BE054858-F61A-488B-87A3-615A646C27F0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_CIPHER_KEY_DIRECTION, WDI_CIPHER_KEY_DIRECTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_CIPHER_KEY_DIRECTION
req.alt-loc: wditypes.hpp
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
req.typenames: WDI_CIPHER_KEY_DIRECTION
req.product: Windows 10 or later.
---

# _WDI_CIPHER_KEY_DIRECTION enumeration



## -description
The WDI_CIPHER_KEY_DIRECTION enumeration defines the traffic directions decrypted by a cipher key.



## -syntax

````
typedef enum _WDI_CIPHER_KEY_DIRECTION { 
  WDI_CIPHER_KEY_DIRECTION_INBOUND   = 1,
  WDI_CIPHER_KEY_DIRECTION_OUTBOUND  = 2,
  WDI_CIPHER_KEY_DIRECTION_BOTH      = 3
} WDI_CIPHER_KEY_DIRECTION;
````


## -enum-fields

### -field WDI_CIPHER_KEY_DIRECTION_INBOUND

The cipher key decrypts packets received from a peer.


### -field WDI_CIPHER_KEY_DIRECTION_OUTBOUND

The cipher key decrypts packets transmitted to a peer.


### -field WDI_CIPHER_KEY_DIRECTION_BOTH

The cipher key  decrypts packets received from or transmitted to a peer.


## -remarks
