---
UID: NC:dot11wdi.MINIPORT_WDI_TX_PEER_BACKLOG
title: MINIPORT_WDI_TX_PEER_BACKLOG (dot11wdi.h)
description: The MiniportWdiTxPeerBacklog handler function is issued when a paused peer has a change in backlog state.
old-location: netvista\miniportwditxpeerbacklog.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_TX_PEER_BACKLOG callback function"]
ms.keywords: MINIPORT_WDI_TX_PEER_BACKLOG, MINIPORT_WDI_TX_PEER_BACKLOG callback, MiniportWdiTxPeerBacklog, MiniportWdiTxPeerBacklog callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxPeerBacklog, netvista.miniportwditxpeerbacklog
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
 - MINIPORT_WDI_TX_PEER_BACKLOG
 - dot11wdi/MINIPORT_WDI_TX_PEER_BACKLOG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiTxPeerBacklog
---

# MINIPORT_WDI_TX_PEER_BACKLOG callback function


## -description

The 
  MiniportWdiTxPeerBacklog handler function is issued when a paused peer has a change in backlog state.  This can happen when WDI receives a send request or as a result of an <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_release_frames_ind">NdisWdiTxReleaseFrameIndication</a>.  It is also issued on an <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_pause_ind">NdisWdiTxSendPauseIndication</a> for affected peers to notify the IHV miniport of the backlog states of those peers.

This is a WDI miniport handler inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.

This request is never made when <b>TargetPriorityQueueing</b> is set to true.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_PEER_BACKLOG</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext 

[in]
TAL device handle returned by the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId 

[in]
The port ID.

### -param PeerId 

[in]
The peer ID.

### -param bBacklogged 

[in]
The backlog state.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_release_frames_ind">NdisWdiTxReleaseFrameIndication</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_pause_ind">NdisWdiTxSendPauseIndication</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_txrx_target_capabilities">WDI_TXRX_CAPABILITIES</a>
