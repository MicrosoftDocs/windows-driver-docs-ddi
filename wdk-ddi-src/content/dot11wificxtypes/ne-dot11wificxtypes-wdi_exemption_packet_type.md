---
UID: NE:dot11wificxtypes._WDI_EXEMPTION_PACKET_TYPE
tech.root: netvista
title: WDI_EXEMPTION_PACKET_TYPE (dot11wificxtypes.h)
ms.date: 07/22/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_EXEMPTION_PACKET_TYPE enum defines the types of packet exemptions.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
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
 - dot11wificxtypes.h
api_name:
 - _WDI_EXEMPTION_PACKET_TYPE
 - WDI_EXEMPTION_PACKET_TYPE
f1_keywords:
 - _WDI_EXEMPTION_PACKET_TYPE
 - dot11wificxtypes/_WDI_EXEMPTION_PACKET_TYPE
 - WDI_EXEMPTION_PACKET_TYPE
 - dot11wificxtypes/WDI_EXEMPTION_PACKET_TYPE
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The **WDI_EXEMPTION_PACKET_TYPE** enumeration defines the types of packet exemptions.

## -enum-fields

### -field WDI_EXEMPT_PACKET_TYPE_UNICAST:1

Exempt unicast packets only.

### -field WDI_EXEMPT_PACKET_TYPE_MULTICAST:2

Exempt multicast and broadcast packets only.

### -field WDI_EXEMPT_PACKET_TYPE_BOTH:3

Exempt all packet types.

## -remarks

The **WDI_EXEMPTION_PACKET_TYPE** enum is a value in the [**WDI_TLV_PRIVACY_EXEMPTION_ENTRY**](/windows-hardware/drivers/netcx/wdi-tlv-privacy-exemption-entry) TLV.

## -see-also

[**WDI_TLV_PRIVACY_EXEMPTION_ENTRY**](/windows-hardware/drivers/netcx/wdi-tlv-privacy-exemption-entry)
