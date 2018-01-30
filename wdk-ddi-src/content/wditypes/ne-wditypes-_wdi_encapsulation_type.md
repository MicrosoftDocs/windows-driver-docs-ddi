---
UID: NE:wditypes._WDI_ENCAPSULATION_TYPE
title: "_WDI_ENCAPSULATION_TYPE"
author: windows-driver-content
description: The WDI_ENCAPSULATION_TYPE enumeration defines the Wi-Fi encapsulation types.
old-location: netvista\wdi_encapsulation_type.htm
old-project: netvista
ms.assetid: 6EDCC69B-F156-416B-9824-5E26F9834D14
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wditypes/WDI_ENCAPSULATION_802_1H, WDI_ENCAPSULATION_RFC_1042, netvista.wdi_encapsulation_type, wditypes/WDI_ENCAPSULATION_TYPE, wditypes/WDI_ENCAPSULATION_RFC_1042, WDI_ENCAPSULATION_802_1H, _WDI_ENCAPSULATION_TYPE, netvista.wifi_encapsulation_type, WDI_ENCAPSULATION_TYPE, WDI_ENCAPSULATION_TYPE enumeration [Device and Driver Installation]
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
-	wditypes.hpp
apiname:
-	WDI_ENCAPSULATION_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_ENCAPSULATION_TYPE
req.product: Windows 10 or later.
---

# _WDI_ENCAPSULATION_TYPE enumeration


## -description


The WDI_ENCAPSULATION_TYPE enumeration defines the Wi-Fi encapsulation types.


## -syntax


````
typedef enum _WDI_ENCAPSULATION_TYPE { 
  WDI_ENCAPSULATION_RFC_1042  = 1,
  WDI_ENCAPSULATION_802_1H    = 2
} WDI_ENCAPSULATION_TYPE;
````


## -enum-fields




### -field WDI_ENCAPSULATION_RFC_1042

The encapsulation that is defined in IETF RFC 1042.


### -field WDI_ENCAPSULATION_802_1H

The encapsulation that is defined in the IEEE 802.1h-1997 standard.

