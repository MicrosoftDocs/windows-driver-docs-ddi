---
UID: NC:dot11wdi.NDIS_WDI_PEER_DELETE_IND
title: NDIS_WDI_PEER_DELETE_IND
author: windows-driver-content
description: The NdisWdiPeerDeleteIndication callback function initiates the removal of the association of between a peer ID and a peer MAC address.
old-location: netvista\ndiswdipeerdeleteindication.htm
old-project: netvista
ms.assetid: A13F2A98-BADA-43B8-A24B-0749C5558C35
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndiswdipeerdeleteindication, NdisWdiPeerDeleteIndication callback function [Network Drivers Starting with Windows Vista], NdisWdiPeerDeleteIndication, NDIS_WDI_PEER_DELETE_IND, NDIS_WDI_PEER_DELETE_IND, dot11wdi/NdisWdiPeerDeleteIndication
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	NdisWdiPeerDeleteIndication
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_PEER_DELETE_IND callback


## -description


The 
  NdisWdiPeerDeleteIndication callback function initiates the removal of the association of between a peer ID and a peer MAC address. Once this indication is processed, the peer ID can no longer be used  in subsequent Rx indications and the IHV may not inject any Tx frames for this peer.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_PEER_DELETE_IND NdisWdiPeerDeleteIndication;

VOID NdisWdiPeerDeleteIndication(
  _In_  NDIS_HANDLE NdisMiniportDataPathHandle,
  _In_  WDI_PORT_ID PortId,
  _In_  WDI_PEER_ID PeerId,
  _Out_ NDIS_STATUS *pWifiStatus
)
{ ... }
````


## -parameters




#### - NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


#### - PortId [in]

The port ID.


#### - PeerId [in]

The peer ID.


#### - *pWifiStatus [out]

Indicates whether the peer deletion completed synchronously (if status is set to <b>NDIS_STATUS_SUCCESS</b>), or whether WDI will issue a <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm.md">MiniportWdiTalTxRxPeerDeleteConfirm</a> when peer deletion completes.


#### - pWifiStatus [out]

Indicates whether the peer deletion completed synchronously (if status is set to <b>NDIS_STATUS_SUCCESS</b>), or whether WDI will issue a <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm.md">MiniportWdiTalTxRxPeerDeleteConfirm</a> when peer deletion completes.


## -returns


This callback function does not return a value.



## -remarks


In PeerQueueing mode, the TxMgr issues a TxAbort for the peer.  If the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_abort.md">MiniportWdiTxAbort</a> completes synchronously and there are no outstanding TX frames for that peer, WDI_STATUS is set to NDIS_STATUS_SUCCESS and the peer deletion is complete (see <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm.md">MiniportWdiTalTxRxPeerDeleteConfirm</a> for  the description of a peer delete completion).  Otherwise, WDI issues a <i>MiniportWdiTalTxRxPeerDeleteConfirm</i> when the TxAbort is completed and there are no outstanding frames for this peer.



## -see-also

<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_abort.md">MiniportWdiTxAbort</a>

<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>

<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm.md">MiniportWdiTalTxRxPeerDeleteConfirm</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_PEER_DELETE_IND callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

