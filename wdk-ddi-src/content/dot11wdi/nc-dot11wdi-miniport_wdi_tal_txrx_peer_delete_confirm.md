---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM
title: MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM (dot11wdi.h)
description: The MiniportWdiTalTxRxPeerDeleteConfirm handler function is invoked after the completion of a PeerDeleteIndication call which did not return success.
old-location: netvista\miniportwditaltxrxpeerdeleteconfirm.htm
tech.root: netvista
ms.assetid: 993C600F-E2FA-46D7-AE66-77048B481660
ms.date: 05/02/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM, MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM callback, MiniportWdiTalTxRxPeerDeleteConfirm, MiniportWdiTalTxRxPeerDeleteConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxPeerDeleteConfirm, netvista.miniportwditaltxrxpeerdeleteconfirm
f1_keywords:
 - "dot11wdi/MiniportWdiTalTxRxPeerDeleteConfirm"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dot11wdi.h
api_name:
- MiniportWdiTalTxRxPeerDeleteConfirm
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM callback function


## -description


The 
  MiniportWdiTalTxRxPeerDeleteConfirm handler function is invoked after the completion of a  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_peer_delete_ind">PeerDeleteIndication</a> call which did not return success.  This is called after a successful <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tx_abort">MiniportWdiTxAbort</a> (or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_abort_confirm">TxAbortConfirm</a>) and after all outstanding TX frames for the peer are completed.  After this call, the mapping between the peer Id and MAC address is no longer valid and the peer Id and MAC address may be used for future <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_peer_create_ind">PeerCreateIndication</a> calls.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

Port ID associated with the peer.


### -param PeerId [in]

Peer ID for the peer.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tx_abort">MiniportWdiTxAbort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_peer_create_ind">PeerCreateIndication</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_peer_delete_ind">PeerDeleteIndication</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_abort_confirm">TxAbortConfirm</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-general-datapath-interfaces">WDI general datapath interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>
 

 

