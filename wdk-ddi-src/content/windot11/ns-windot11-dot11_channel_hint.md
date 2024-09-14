---
UID: NS:windot11.DOT11_CHANNEL_HINT
title: DOT11_CHANNEL_HINT (windot11.h)
description: The DOT11_CHANNEL_HINT structure describes suggested channel numbers for an NLO operation.
old-location: netvista\dot11_channel_hint.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_CHANNEL_HINT structure"]
ms.keywords: "*PDOT11_CHANNEL_HINT, DOT11_CHANNEL_HINT, DOT11_CHANNEL_HINT structure [Network Drivers Starting with Windows Vista], PDOT11_CHANNEL_HINT, PDOT11_CHANNEL_HINT structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_channel_hint, windot11/DOT11_CHANNEL_HINT, windot11/PDOT11_CHANNEL_HINT"
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
req.typenames: DOT11_CHANNEL_HINT, *PDOT11_CHANNEL_HINT
f1_keywords:
 - DOT11_CHANNEL_HINT
 - windot11/DOT11_CHANNEL_HINT
 - PDOT11_CHANNEL_HINT
 - windot11/PDOT11_CHANNEL_HINT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - DOT11_CHANNEL_HINT
 - PDOT11_CHANNEL_HINT
---

# DOT11_CHANNEL_HINT structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_CHANNEL_HINT structure describes suggested channel numbers for an NLO operation.

## -struct-fields

### -field Dot11PhyType

The 802.11 PHY and media type.

### -field uChannelNumber

Channel number.

## -syntax

```cpp
typedef struct _DOT11_CHANNEL_HINT {
  DOT11_PHY_TYPE Dot11PhyType;
  ULONG          uChannelNumber;
} DOT11_CHANNEL_HINT, *PDOT11_CHANNEL_HINT;
```

