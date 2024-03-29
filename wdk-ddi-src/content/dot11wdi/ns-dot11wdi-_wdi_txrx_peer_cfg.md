---
UID: NS:dot11wdi._WDI_TXRX_PEER_CFG
title: _WDI_TXRX_PEER_CFG (dot11wdi.h)
description: The WDI_TXRX_PEER_CFG structure defines peer configuration.
old-location: netvista\wdi_txrx_peer_cfg.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_TXRX_PEER_CFG structure"]
ms.keywords: "*PWDI_TXRX_PEER_CFG, PWDI_TXRX_PEER_CFG, PWDI_TXRX_PEER_CFG structure pointer [Network Drivers Starting with Windows Vista], WDI_TXRX_PEER_CFG, WDI_TXRX_PEER_CFG structure [Network Drivers Starting with Windows Vista], _WDI_TXRX_PEER_CFG, dot11wdi/PWDI_TXRX_PEER_CFG, dot11wdi/WDI_TXRX_PEER_CFG, netvista.wdi_txrx_peer_cfg, netvista.wifi_txrx_peer_cfg"
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
req.typenames: WDI_TXRX_PEER_CFG, *PWDI_TXRX_PEER_CFG
f1_keywords:
 - _WDI_TXRX_PEER_CFG
 - dot11wdi/_WDI_TXRX_PEER_CFG
 - PWDI_TXRX_PEER_CFG
 - dot11wdi/PWDI_TXRX_PEER_CFG
 - WDI_TXRX_PEER_CFG
 - dot11wdi/WDI_TXRX_PEER_CFG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_TXRX_PEER_CFG
 - PWDI_TXRX_PEER_CFG
 - WDI_TXRX_PEER_CFG
---

# _WDI_TXRX_PEER_CFG structure


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_TXRX_PEER_CFG structure defines peer configuration.

## -struct-fields

### -field PeerQoSConfig

The peer's QoS capability as defined in <a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_txrx_peer_qos_caps">WDI_TXRX_PEER_QOS_CAPS</a>.

