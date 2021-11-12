---
UID: NE:dot11wdi._WDI_TXRX_PEER_QOS_CAPS
title: _WDI_TXRX_PEER_QOS_CAPS (dot11wdi.h)
description: The WDI_TXRX_PEER_QOS_CAPS enumeration defines the Quality of Service (QoS) capabilities.
old-location: netvista\wdi_txrx_peer_qos_caps.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_TXRX_PEER_QOS_CAPS enumeration"]
ms.keywords: WDI_TXRX_PEER_QOS_CAPS, WDI_TXRX_PEER_QOS_CAPS enumeration [Network Drivers Starting with Windows Vista], WDI_TXRX_PeerCfgQosCapable, WDI_TXRX_PeerCfgQosNone, WDI_TXRX_PeerCfgQosUapsdTids, _WDI_TXRX_PEER_QOS_CAPS, dot11wdi/WDI_TXRX_PEER_QOS_CAPS, dot11wdi/WDI_TXRX_PeerCfgQosCapable, dot11wdi/WDI_TXRX_PeerCfgQosNone, dot11wdi/WDI_TXRX_PeerCfgQosUapsdTids, netvista.wdi_txrx_peer_qos_caps, netvista.wifi_txrx_peer_qos_caps
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
req.typenames: WDI_TXRX_PEER_QOS_CAPS
f1_keywords:
 - _WDI_TXRX_PEER_QOS_CAPS
 - dot11wdi/_WDI_TXRX_PEER_QOS_CAPS
 - WDI_TXRX_PEER_QOS_CAPS
 - dot11wdi/WDI_TXRX_PEER_QOS_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_TXRX_PEER_QOS_CAPS
 - WDI_TXRX_PEER_QOS_CAPS
---

# _WDI_TXRX_PEER_QOS_CAPS enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_TXRX_PEER_QOS_CAPS enumeration defines the Quality of Service (QoS) capabilities.

## -enum-fields

### -field WDI_TXRX_PeerCfgQosNone

Specifies that QoS was not negotiated for this peer during association.

### -field WDI_TXRX_PeerCfgQosCapable

Specifies that QoS was negotiated for this peer during association.

### -field WDI_TXRX_PeerCfgUapsdTids

### -field WDI_TXRX_PeerCfgQosUapsdTids

Reserved.

