---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_PEER_CONFIG
title: MINIPORT_WDI_TAL_TXRX_PEER_CONFIG (dot11wdi.h)
description: The MiniportWdiTalTxRxPeerConfig handler function specifies the port ID, peer ID, and peer capabilities (for example, QoS capabilities). It is invoked after the peer has associated, which involves creation of the peer object in the TAL.
old-location: netvista\miniportwditaltxrxpeerconfig.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_TAL_TXRX_PEER_CONFIG callback function"]
ms.keywords: MINIPORT_WDI_TAL_TXRX_PEER_CONFIG, MINIPORT_WDI_TAL_TXRX_PEER_CONFIG callback, MiniportWdiTalTxRxPeerConfig, MiniportWdiTalTxRxPeerConfig callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxPeerConfig, netvista.miniportwditaltxrxpeerconfig
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
req.typenames: 
f1_keywords:
 - MINIPORT_WDI_TAL_TXRX_PEER_CONFIG
 - dot11wdi/MINIPORT_WDI_TAL_TXRX_PEER_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiTalTxRxPeerConfig
---

# MINIPORT_WDI_TAL_TXRX_PEER_CONFIG callback function


## -description

The 
  MiniportWdiTalTxRxPeerConfig handler function specifies the port ID, peer ID,  and peer capabilities  (for example, QoS capabilities). It is invoked after the peer has associated, which involves creation of the peer object in the TAL.

This is a WDI miniport handler inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_PEER_CONFIG</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext 

[in]
TAL device handle returned by the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId 

[in]
Port ID associated with the peer.

### -param PeerId 

[in]
Peer ID for the peer.

### -param pPeerCfg 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_txrx_peer_cfg">WDI_TXRX_PEER_CFG</a> structure that contains negotiated QoS settings.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="/windows-hardware/drivers/network/wdi-general-datapath-interfaces">WDI general datapath interfaces</a>



<a href="/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_txrx_peer_cfg">WDI_TXRX_PEER_CFG</a>
