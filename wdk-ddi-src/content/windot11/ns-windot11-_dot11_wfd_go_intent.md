---
UID: NS:windot11._DOT11_WFD_GO_INTENT
title: _DOT11_WFD_GO_INTENT (windot11.h)
description: The DOT11_WFD_GO_INTENT structure represents the Group Intent value used during Group Owner Negotiation
old-location: netvista\_dot11_wfd_go_intent.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_GO_INTENT structure"]
ms.keywords: "*PDOT11_WFD_GO_INTENT, DOT11_WFD_GO_INTENT, DOT11_WFD_GO_INTENT structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_GO_INTENT, PDOT11_WFD_GO_INTENT structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_GO_INTENT, netvista._dot11_wfd_go_intent, windot11/DOT11_WFD_GO_INTENT, windot11/PDOT11_WFD_GO_INTENT"
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
req.typenames: DOT11_WFD_GO_INTENT, *PDOT11_WFD_GO_INTENT
f1_keywords:
 - _DOT11_WFD_GO_INTENT
 - windot11/_DOT11_WFD_GO_INTENT
 - PDOT11_WFD_GO_INTENT
 - windot11/PDOT11_WFD_GO_INTENT
 - DOT11_WFD_GO_INTENT
 - windot11/DOT11_WFD_GO_INTENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WFD_GO_INTENT
 - PDOT11_WFD_GO_INTENT
 - DOT11_WFD_GO_INTENT
---

# _DOT11_WFD_GO_INTENT structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The <b>DOT11_WFD_GO_INTENT</b> structure represents the Group Intent value used during Group Owner Negotiation

## -struct-fields

### -field TieBreaker

If set, indicates that group ownership is granted.

### -field Intent

Group ownership intent level. The value of the local device intent is compared to the remote device intent to negotiate ownership.

## -syntax

```cpp
typedef struct _DOT11_WFD_GO_INTENT {
  UCHAR TieBreaker:1;
  UCHAR Intent:7;
} DOT11_WFD_GO_INTENT, *PDOT11_WFD_GO_INTENT;
```

