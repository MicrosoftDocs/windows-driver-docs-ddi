---
UID: NE:wditypes._WDI_P2P_CHANNEL_INDICATE_REASON
title: _WDI_P2P_CHANNEL_INDICATE_REASON (wditypes.h)
description: The WDI_P2P_CHANNEL_INDICATE_REASON enumeration defines Wi-Fi Direct channel indication reason values.
old-location: netvista\wdi_p2p_channel_indicate_reason.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_P2P_CHANNEL_INDICATE_REASON enumeration"]
ms.keywords: WDI_P2P_CHANNEL_INDICATE_REASON, WDI_P2P_CHANNEL_INDICATE_REASON enumeration [Network Drivers Starting with Windows Vista], WDI_P2P_CHANNEL_INDICATE_REASON_ECSA_GO_INITIATED, WDI_P2P_CHANNEL_INDICATE_REASON_ECSA_REQUESTED, WDI_P2P_CHANNEL_INDICATE_REASON_NEW_CONNECTION, _WDI_P2P_CHANNEL_INDICATE_REASON, netvista.wdi_p2p_channel_indicate_reason, wditypes/WDI_P2P_CHANNEL_INDICATE_REASON, wditypes/WDI_P2P_CHANNEL_INDICATE_REASON_ECSA_GO_INITIATED, wditypes/WDI_P2P_CHANNEL_INDICATE_REASON_ECSA_REQUESTED, wditypes/WDI_P2P_CHANNEL_INDICATE_REASON_NEW_CONNECTION
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
req.typenames: WDI_P2P_CHANNEL_INDICATE_REASON
f1_keywords:
 - _WDI_P2P_CHANNEL_INDICATE_REASON
 - wditypes/_WDI_P2P_CHANNEL_INDICATE_REASON
 - WDI_P2P_CHANNEL_INDICATE_REASON
 - wditypes/WDI_P2P_CHANNEL_INDICATE_REASON
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_P2P_CHANNEL_INDICATE_REASON
 - WDI_P2P_CHANNEL_INDICATE_REASON
---

# _WDI_P2P_CHANNEL_INDICATE_REASON enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_P2P_CHANNEL_INDICATE_REASON enumeration defines Wi-Fi Direct channel indication reason values.

## -enum-fields

### -field WDI_P2P_CHANNEL_INDICATE_REASON_UNKNOWN

### -field WDI_P2P_CHANNEL_INDICATE_REASON_NEW_CONNECTION

New connection set up.

### -field WDI_P2P_CHANNEL_INDICATE_REASON_ECSA_REQUESTED

eCSA request from the peer.

### -field WDI_P2P_CHANNEL_INDICATE_REASON_ECSA_GO_INITIATED

eCSA initiated by GO.

### -field WDI_P2P_CHANNEL_INDICATE_REASON_MAX

