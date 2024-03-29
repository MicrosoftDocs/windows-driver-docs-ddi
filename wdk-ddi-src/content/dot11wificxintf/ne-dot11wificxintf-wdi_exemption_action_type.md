---
UID: NE:dot11wificxintf._WDI_EXEMPTION_ACTION_TYPE
tech.root: netvista
title: WDI_EXEMPTION_ACTION_TYPE (dot11wificxintf.h)
ms.date: 09/15/2021
targetos: Windows
description: The WDI_EXEMPTION_ACTION_TYPE enum defines exemption types.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxintf.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxintf.h
api_name:
 - _WDI_EXEMPTION_ACTION_TYPE
 - WDI_EXEMPTION_ACTION_TYPE
f1_keywords:
 - _WDI_EXEMPTION_ACTION_TYPE
 - dot11wificxintf/_WDI_EXEMPTION_ACTION_TYPE
 - WDI_EXEMPTION_ACTION_TYPE
 - dot11wificxintf/WDI_EXEMPTION_ACTION_TYPE
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is now in maintenance mode and will only receive high priority fixes.

The **WDI_EXEMPTION_ACTION_TYPE** enumeration defines exemption types.

## -enum-fields

### -field WDI_EXEMPT_NO_EXEMPTION:0

Packets are not exempt from any cipher operations performed by the port.

### -field WDI_EXEMPT_ALWAYS:1

On send, packets are exempt from cipher operations and are transmitted unencrypted. On receive, the received packet is discarded if the Protected Frame subfield of the Frame Control field in the 802.11 MAC header is set to 1.

### -field WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE:2

On send, packets are exempt from cipher operations if there is no key-mapping key for the packet's destination MAC address. On receive, the received packet is discarded if a key-mapping key for the source MAC address is available and the Protected Frame subfield of the Frame Control field in the 802.11 MAC header is set to **zero**.


## -remarks

The **WDI_EXEMPTION_ACTION_TYPE** enum is a value in the [**WDI_TLV_PRIVACY_EXEMPTION_ENTRY**](/windows-hardware/drivers/netcx/wdi-tlv-privacy-exemption-entry) TLV.

## -see-also

[**WDI_TLV_PRIVACY_EXEMPTION_ENTRY**](/windows-hardware/drivers/netcx/wdi-tlv-privacy-exemption-entry)
