---
UID: NS:dot11wdi._WDI_TXRX_PEER_CFG
title: "_WDI_TXRX_PEER_CFG"
author: windows-driver-content
description: The WDI_TXRX_PEER_CFG structure defines peer configuration.
old-location: netvista\wdi_txrx_peer_cfg.htm
old-project: netvista
ms.assetid: 5d2a97a3-3214-4f23-bf9d-d0ed292a46f0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PWDI_TXRX_PEER_CFG, *PWDI_TXRX_PEER_CFG, PWDI_TXRX_PEER_CFG structure pointer [Network Drivers Starting with Windows Vista], dot11wdi/PWDI_TXRX_PEER_CFG, netvista.wifi_txrx_peer_cfg, WDI_TXRX_PEER_CFG, _WDI_TXRX_PEER_CFG, netvista.wdi_txrx_peer_cfg, WDI_TXRX_PEER_CFG structure [Network Drivers Starting with Windows Vista], dot11wdi/WDI_TXRX_PEER_CFG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dot11wdi.h
apiname:
-	WDI_TXRX_PEER_CFG
product: Windows
targetos: Windows
req.typenames: "*PWDI_TXRX_PEER_CFG, WDI_TXRX_PEER_CFG"
---

# _WDI_TXRX_PEER_CFG structure


## -description


The WDI_TXRX_PEER_CFG structure defines peer configuration.


## -syntax


````
typedef struct _WDI_TXRX_PEER_CFG {
  WDI_TXRX_PEER_QOS_CAPS PeerQoSConfig;
} WDI_TXRX_PEER_CFG, *PWDI_TXRX_PEER_CFG;
````


## -struct-fields




### -field PeerQoSConfig

The peer's QoS capability as defined in <a href="..\dot11wdi\ne-dot11wdi-_wdi_txrx_peer_qos_caps.md">WDI_TXRX_PEER_QOS_CAPS</a>.

