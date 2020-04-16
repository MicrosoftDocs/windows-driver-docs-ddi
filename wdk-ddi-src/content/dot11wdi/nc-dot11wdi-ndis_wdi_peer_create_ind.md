---
UID: NC:dot11wdi.NDIS_WDI_PEER_CREATE_IND
title: NDIS_WDI_PEER_CREATE_IND (dot11wdi.h)
description: The NdisWdiPeerCreateIndication callback function specifies a peer ID to associate with a peer MAC address.
old-location: netvista\ndiswdipeercreateindication.htm
tech.root: netvista
ms.assetid: 58B60160-FE04-4EDE-900F-244D0F76E50D
ms.date: 05/02/2018
keywords: ["NDIS_WDI_PEER_CREATE_IND callback function"]
ms.keywords: NDIS_WDI_PEER_CREATE_IND, NDIS_WDI_PEER_CREATE_IND callback, NdisWdiPeerCreateIndication, NdisWdiPeerCreateIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiPeerCreateIndication, netvista.ndiswdipeercreateindication
f1_keywords:
 - "dot11wdi/NdisWdiPeerCreateIndication"
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
- NdisWdiPeerCreateIndication
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_PEER_CREATE_IND callback function


## -description


The NdisWdiPeerCreateIndication callback function specifies a peer ID to associate with a peer MAC address.

This is a callback inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID.


### -param PeerId [in]

The peer ID. This is used to identify the  peer in subsequent commands and indications.


### -param PeerAddr [in]

The peer MAC address.


## -remarks



This must be received and processed prior to exchanging frames with the peer.

A port operating in AP or Wi-Fi Direct GO mode may simultaneously have more than one peer (clients).  When a port is operating in AP or Wi-Fi Direct GO mode, the IHV miniport creates a 'peer' for group addressed traffic (by passing a broadcast MAC address).  All multicast and broadcast traffic for this port is associated with this peer. In port queuing mode, the creation of the group peer by the IHV miniport is not required as Tx frame classification does not occur in this mode.

A port operating in any mode may create a group peer.

To facilitate TDLS implementation in the IHV component, a port operating in STA or Wi-Fi Direct client mode may simultaneously have more than one peer.  If  a TX frame's destination MAC address matches is associated with a non-AP/GO peer ID, the TxMgr queues the frame with a TID queue associated with that non-AP/GO peer (if WDI is operating in PeerTID queuing mode).

In peer queuing mode, a peer is created with all TIDs paused with <b>WDI_TX_PAUSE_REASON_PEER_CREATE</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-general-datapath-interfaces">WDI general datapath interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_mac_address">WDI_MAC_ADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>
 

 

