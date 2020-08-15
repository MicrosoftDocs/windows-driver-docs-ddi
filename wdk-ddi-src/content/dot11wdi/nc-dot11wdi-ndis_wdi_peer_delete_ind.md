---
UID: NC:dot11wdi.NDIS_WDI_PEER_DELETE_IND
title: NDIS_WDI_PEER_DELETE_IND (dot11wdi.h)
description: The NdisWdiPeerDeleteIndication callback function initiates the removal of the association of between a peer ID and a peer MAC address.
old-location: netvista\ndiswdipeerdeleteindication.htm
tech.root: netvista
ms.assetid: A13F2A98-BADA-43B8-A24B-0749C5558C35
ms.date: 05/02/2018
keywords: ["NDIS_WDI_PEER_DELETE_IND callback function"]
ms.keywords: NDIS_WDI_PEER_DELETE_IND, NDIS_WDI_PEER_DELETE_IND callback, NdisWdiPeerDeleteIndication, NdisWdiPeerDeleteIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiPeerDeleteIndication, netvista.ndiswdipeerdeleteindication
f1_keywords:
 - "dot11wdi/NdisWdiPeerDeleteIndication"
 - "NdisWdiPeerDeleteIndication"
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
- NdisWdiPeerDeleteIndication
targetos: Windows
req.typenames: 
---

# NDIS_WDI_PEER_DELETE_IND callback function


## -description


The 
  NdisWdiPeerDeleteIndication callback function initiates the removal of the association of between a peer ID and a peer MAC address. Once this indication is processed, the peer ID can no longer be used  in subsequent Rx indications and the IHV may not inject any Tx frames for this peer.

This is a callback inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle 
[in]
The NdisMiniportDataPathHandle passed to IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


### -param PortId 
[in]
The port ID.


### -param PeerId 
[in]
The peer ID.


### -param pWifiStatus 
[out]
Indicates whether the peer deletion completed synchronously (if status is set to <b>NDIS_STATUS_SUCCESS</b>), or whether WDI will issue a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm">MiniportWdiTalTxRxPeerDeleteConfirm</a> when peer deletion completes.


## -remarks



In PeerQueueing mode, the TxMgr issues a TxAbort for the peer.  If the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tx_abort">MiniportWdiTxAbort</a> completes synchronously and there are no outstanding TX frames for that peer, WDI_STATUS is set to NDIS_STATUS_SUCCESS and the peer deletion is complete (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm">MiniportWdiTalTxRxPeerDeleteConfirm</a> for  the description of a peer delete completion).  Otherwise, WDI issues a <i>MiniportWdiTalTxRxPeerDeleteConfirm</i> when the TxAbort is completed and there are no outstanding frames for this peer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm">MiniportWdiTalTxRxPeerDeleteConfirm</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tx_abort">MiniportWdiTxAbort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-general-datapath-interfaces">WDI general datapath interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>
 

 

