---
UID: NE:dot11wdi._WDI_EXEMPTION_ACTION_TYPE
title: _WDI_EXEMPTION_ACTION_TYPE (dot11wdi.h)
description: The WDI_EXEMPTION_ACTION_TYPE enumeration defines the exemption types.
old-location: netvista\wdi_exemption_action_type.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_EXEMPTION_ACTION_TYPE enumeration"]
ms.keywords: WDI_EXEMPTION_ACTION_TYPE, WDI_EXEMPTION_ACTION_TYPE enumeration [Network Drivers Starting with Windows Vista], WDI_EXEMPT_ALWAYS, WDI_EXEMPT_NO_EXEMPTION, WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE, _WDI_EXEMPTION_ACTION_TYPE, dot11wdi/WDI_EXEMPTION_ACTION_TYPE, dot11wdi/WDI_EXEMPT_ALWAYS, dot11wdi/WDI_EXEMPT_NO_EXEMPTION, dot11wdi/WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE, netvista.wdi_exemption_action_type, netvista.wifi_exemption_action_type
req.header: dot11wdi.h
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
targetos: Windows
req.typenames: WDI_EXEMPTION_ACTION_TYPE
f1_keywords:
 - _WDI_EXEMPTION_ACTION_TYPE
 - dot11wdi/_WDI_EXEMPTION_ACTION_TYPE
 - WDI_EXEMPTION_ACTION_TYPE
 - dot11wdi/WDI_EXEMPTION_ACTION_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_EXEMPTION_ACTION_TYPE
 - WDI_EXEMPTION_ACTION_TYPE
---

# _WDI_EXEMPTION_ACTION_TYPE enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_EXEMPTION_ACTION_TYPE enumeration defines the exemption types.

## -enum-fields

### -field WDI_EXEMPT_NO_EXEMPTION

Packets are not exempt from any cipher operations performed by the port.

### -field WDI_EXEMPT_ALWAYS

On send, packets are exempt from cipher operations and are transmitted unencrypted. On receive, the received packet is discarded if the Protected Frame subfield of the Frame Control field in the 802.11 MAC header is set to 1.

### -field WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE

On send, packets are exempt from cipher operations if there is no key-mapping key for the packet's destination MAC address. On receive, the received packet is discarded if a key-mapping key for the source MAC address is available and the Protected Frame subfield of the Frame Control field in the 802.11 MAC header is set to 0.

