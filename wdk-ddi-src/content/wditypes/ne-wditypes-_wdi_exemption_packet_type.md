---
UID: NE:wditypes._WDI_EXEMPTION_PACKET_TYPE
title: _WDI_EXEMPTION_PACKET_TYPE (wditypes.h)
description: The WDI_EXEMPTION_PACKET_TYPE enumeration defines the types of packet exemptions.
old-location: netvista\wdi_exemption_packet_type.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_EXEMPTION_PACKET_TYPE enumeration"]
ms.keywords: WDI_EXEMPTION_PACKET_TYPE, WDI_EXEMPTION_PACKET_TYPE enumeration [Device and Driver Installation], WDI_EXEMPT_PACKET_TYPE_BOTH, WDI_EXEMPT_PACKET_TYPE_MULTICAST, WDI_EXEMPT_PACKET_TYPE_UNICAST, _WDI_EXEMPTION_PACKET_TYPE, netvista.wdi_exemption_packet_type, netvista.wifi_exemption_packet_type, wditypes/WDI_EXEMPTION_PACKET_TYPE, wditypes/WDI_EXEMPT_PACKET_TYPE_BOTH, wditypes/WDI_EXEMPT_PACKET_TYPE_MULTICAST, wditypes/WDI_EXEMPT_PACKET_TYPE_UNICAST
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
targetos: Windows
req.typenames: WDI_EXEMPTION_PACKET_TYPE
f1_keywords:
 - _WDI_EXEMPTION_PACKET_TYPE
 - wditypes/_WDI_EXEMPTION_PACKET_TYPE
 - WDI_EXEMPTION_PACKET_TYPE
 - wditypes/WDI_EXEMPTION_PACKET_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_EXEMPTION_PACKET_TYPE
 - WDI_EXEMPTION_PACKET_TYPE
---

# _WDI_EXEMPTION_PACKET_TYPE enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_EXEMPTION_PACKET_TYPE enumeration defines the types of packet exemptions.

## -enum-fields

### -field WDI_EXEMPT_PACKET_TYPE_UNICAST

Exempt unicast packets only.

### -field WDI_EXEMPT_PACKET_TYPE_MULTICAST

Exempt multicast and broadcast packets only.

### -field WDI_EXEMPT_PACKET_TYPE_BOTH

Exempt all packet types.

