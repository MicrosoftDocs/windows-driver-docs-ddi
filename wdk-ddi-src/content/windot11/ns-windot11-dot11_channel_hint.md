---
UID: NS:windot11.DOT11_CHANNEL_HINT
title: DOT11_CHANNEL_HINT
author: windows-driver-content
description: The DOT11_CHANNEL_HINT structure describes suggested channel numbers for an NLO operation.
old-location: netvista\dot11_channel_hint.htm
tech.root: netvista
ms.assetid: B3E395C3-C642-4A5E-9005-88323A80F90E
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_CHANNEL_HINT, DOT11_CHANNEL_HINT, DOT11_CHANNEL_HINT structure [Network Drivers Starting with Windows Vista], PDOT11_CHANNEL_HINT, PDOT11_CHANNEL_HINT structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_channel_hint, windot11/DOT11_CHANNEL_HINT, windot11/PDOT11_CHANNEL_HINT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Windot11.h
api_name:
-	DOT11_CHANNEL_HINT
product:
- Windows
targetos: Windows
req.typenames: DOT11_CHANNEL_HINT, *PDOT11_CHANNEL_HINT
product:
- Windows 10 or later.
---

# DOT11_CHANNEL_HINT structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CHANNEL_HINT structure describes suggested channel numbers for an NLO operation.


## -syntax


```
typedef struct _DOT11_CHANNEL_HINT {
  DOT11_PHY_TYPE Dot11PhyType;
  ULONG          uChannelNumber;
} DOT11_CHANNEL_HINT, *PDOT11_CHANNEL_HINT;
```


## -struct-fields




### -field Dot11PhyType

The 802.11 PHY and media type.


### -field uChannelNumber

Channel number.

