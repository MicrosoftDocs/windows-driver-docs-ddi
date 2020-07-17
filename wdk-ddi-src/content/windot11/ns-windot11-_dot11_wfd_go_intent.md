---
UID: NS:windot11._DOT11_WFD_GO_INTENT
title: _DOT11_WFD_GO_INTENT (windot11.h)
description: The DOT11_WFD_GO_INTENT structure represents the Group Intent value used during Group Owner Negotiation
old-location: netvista\_dot11_wfd_go_intent.htm
tech.root: netvista
ms.assetid: 8E4F88EF-04A9-4313-AE6A-2467DA08044A
ms.date: 02/16/2018
keywords: ["_DOT11_WFD_GO_INTENT structure"]
ms.keywords: "*PDOT11_WFD_GO_INTENT, DOT11_WFD_GO_INTENT, DOT11_WFD_GO_INTENT structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_GO_INTENT, PDOT11_WFD_GO_INTENT structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_GO_INTENT, netvista._dot11_wfd_go_intent, windot11/DOT11_WFD_GO_INTENT, windot11/PDOT11_WFD_GO_INTENT"
f1_keywords:
 - "windot11/DOT11_WFD_GO_INTENT"
 - "DOT11_WFD_GO_INTENT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Windot11.h
api_name:
- DOT11_WFD_GO_INTENT
targetos: Windows
req.typenames: DOT11_WFD_GO_INTENT, *PDOT11_WFD_GO_INTENT
product:
- Windows 10 or later.
---

# _DOT11_WFD_GO_INTENT structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_GO_INTENT</b> structure represents the Group Intent value used during Group Owner Negotiation


## -syntax


```cpp
typedef struct _DOT11_WFD_GO_INTENT {
  UCHAR TieBreaker:1;
  UCHAR Intent:7;
} DOT11_WFD_GO_INTENT, *PDOT11_WFD_GO_INTENT;
```


## -struct-fields




### -field TieBreaker




### -field Intent






#### - Intent:7

Group ownership intent level. The value of the local device intent is compared to the remote device intent to negociate ownership.


#### - TieBreaker:1

If set, indicates that group ownership is granted.

