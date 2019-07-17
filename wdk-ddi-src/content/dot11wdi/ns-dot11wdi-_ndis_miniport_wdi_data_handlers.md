---
UID: NS:dot11wdi._NDIS_MINIPORT_WDI_DATA_HANDLERS
title: _NDIS_MINIPORT_WDI_DATA_HANDLERS (dot11wdi.h)
description: The NDIS_MINIPORT_WDI_DATA_HANDLERS structure specifies the entry points for the IHV miniport datapath handlers.
old-location: netvista\ndis_miniport_wdi_data_handlers.htm
tech.root: netvista
ms.assetid: DBDB5F08-9988-4D9B-A731-DA65BBA67813
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_WDI_DATA_HANDLERS, NDIS_MINIPORT_WDI_DATA_HANDLERS, NDIS_MINIPORT_WDI_DATA_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_WDI_DATA_HANDLERS, PNDIS_MINIPORT_WDI_DATA_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_WDI_DATA_HANDLERS, dot11wdi/NDIS_MINIPORT_WDI_DATA_HANDLERS, dot11wdi/PNDIS_MINIPORT_WDI_DATA_HANDLERS, netvista.ndis_miniport_wdi_data_handlers"
ms.topic: struct
f1_keywords:
 - "dot11wdi/NDIS_MINIPORT_WDI_DATA_HANDLERS"
req.header: dot11wdi.h
req.include-header: Ndis.h
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
- HeaderDef
api_location:
- dot11wdi.h
api_name:
- NDIS_MINIPORT_WDI_DATA_HANDLERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_WDI_DATA_HANDLERS, *PNDIS_MINIPORT_WDI_DATA_HANDLERS
---

# _NDIS_MINIPORT_WDI_DATA_HANDLERS structure


## -description


The NDIS_MINIPORT_WDI_DATA_HANDLERS structure specifies the entry points for the IHV miniport datapath handlers.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_WDI_DATA_HANDLERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_WDI_DATA_HANDLERS.
     

To indicate the version of the NDIS_MINIPORT_WDI_DATA_HANDLERS structure, set the 
     <b>Revision</b> member to the following value:





#### NDIS_OBJECT_TYPE_MINIPORT_WDI_DATA_HANDLERS_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_WDI_DATA_HANDLERS_REVISION_1.


### -field TxAbortHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tx_abort">MiniportWdiTxAbort</a> handler function.


### -field TxTargetDescInitHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tx_target_desc_init">MiniportWdiTxTargetDescInit</a> handler function.


### -field TxTargetDescDeInitHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tx_target_desc_deinit">MiniportWdiTxTargetDescDeInit</a> handler function.


### -field TxDataSendHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tx_data_send">MiniportWdiTxDataSend</a> handler function.


### -field TxTalSendHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tx_tal_send">MiniportWdiTxTalSend</a> handler function.


### -field TxTalSendCompleteHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tx_tal_send_complete">MiniportWdiTxTalSendComplete</a> handler function.


### -field TxTalQueueInOrderHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order">MiniportWdiTxTalQueueInOrder</a> handler function.


### -field TxPeerBacklogHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tx_peer_backlog">MiniportWdiTxPeerBacklog</a> handler function.


### -field RxStopHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_rx_stop">MiniportWdiRxStop</a> handler function.


### -field RxFlushHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_rx_flush">MiniportWdiRxFlush</a> handler function.


### -field RxRestartHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_rx_restart">MiniportWdiRxRestart</a> handler function.


### -field RxGetMpdusHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_rx_get_mpdus">MiniportWdiRxGetMpdus</a> handler function.


### -field RxReturnFramesHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_rx_return_frames">MiniportWdiRxReturnFrames</a> handler function.


### -field RxResumeHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_rx_resume">MiniportWdiRxResume</a> handler function.


### -field RxThrottleHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_rx_throttle">MiniportWdiRxThrottle</a> handler function.


### -field RxPpduRssiHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_rx_ppdu_rssi">MiniportWdiRxPpduRssi</a> handler function.


### -field TalTxRxStartHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_start">MiniportWdiTalTxRxStart</a> handler function.


### -field TalTxRxStopHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_stop">MiniportWdiTalTxRxStop</a> handler function.


### -field TalTxRxAddPortHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_add_port">MiniportWdiTalTxRxAddPort</a> handler function.


### -field TalTxRxDeletePortHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_delete_port">MiniportWdiTalTxRxDeletePort</a> handler function.


### -field TalTxRxSetPortOpModeHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_set_port_opmode">MiniportWdiTalTxRxSetPortOpMode</a> handler function.


### -field TalTxRxResetPortHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_reset_port">MiniportWdiTalTxRxResetPort</a> handler function.


### -field TalTxRxPeerConfigHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_peer_config">MiniportWdiTalTxRxPeerConfig</a> handler function.


### -field TalTxRxPeerDeleteConfirmHandler

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm">MiniportWdiTalTxRxPeerDeleteConfirm</a> handler function.


### -field TxSuspectFrameAbortHandler

The entry point of the [MiniportWdiTxSuspectFrameAbort](nc-dot11wdi-miniport_wdi_tx_suspect_frame_list_abort.md) handler function.
