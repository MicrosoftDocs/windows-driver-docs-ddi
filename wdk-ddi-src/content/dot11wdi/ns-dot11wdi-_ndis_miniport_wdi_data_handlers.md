---
UID: NS:dot11wdi._NDIS_MINIPORT_WDI_DATA_HANDLERS
title: "_NDIS_MINIPORT_WDI_DATA_HANDLERS"
author: windows-driver-content
description: The NDIS_MINIPORT_WDI_DATA_HANDLERS structure specifies the entry points for the IHV miniport datapath handlers.
old-location: netvista\ndis_miniport_wdi_data_handlers.htm
old-project: netvista
ms.assetid: DBDB5F08-9988-4D9B-A731-DA65BBA67813
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_MINIPORT_WDI_DATA_HANDLERS, NDIS_MINIPORT_WDI_DATA_HANDLERS, NDIS_MINIPORT_WDI_DATA_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_WDI_DATA_HANDLERS, PNDIS_MINIPORT_WDI_DATA_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_WDI_DATA_HANDLERS, dot11wdi/NDIS_MINIPORT_WDI_DATA_HANDLERS, dot11wdi/PNDIS_MINIPORT_WDI_DATA_HANDLERS, netvista.ndis_miniport_wdi_data_handlers"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dot11wdi.h
api_name:
-	NDIS_MINIPORT_WDI_DATA_HANDLERS
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_WDI_DATA_HANDLERS, *PNDIS_MINIPORT_WDI_DATA_HANDLERS
---

# _NDIS_MINIPORT_WDI_DATA_HANDLERS structure


## -description


The NDIS_MINIPORT_WDI_DATA_HANDLERS structure specifies the entry points for the IHV miniport datapath handlers.


## -syntax


````
typedef struct _NDIS_MINIPORT_WDI_DATA_HANDLERS {
  NDIS_OBJECT_HEADER                                Header;
  MINIPORT_WDI_TX_ABORT_HANDLER                     TxAbortHandler;
  MINIPORT_WDI_TX_TARGET_DESC_INIT_HANDLER          TxTargetDescInitHandler;
  MINIPORT_WDI_TX_TARGET_DESC_DEINIT_HANDLER        TxTargetDescDeInitHandler;
  MINIPORT_WDI_TX_DATA_SEND_HANDLER                 TxDataSendHandler;
  MINIPORT_WDI_TX_TAL_SEND_HANDLER                  TxTalSendHandler;
  MINIPORT_WDI_TX_TAL_SEND_COMPLETE_HANDLER         TxTalSendCompleteHandler;
  MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER_HANDLER        TxTalQueueInOrderHandler;
  MINIPORT_WDI_TX_PEER_BACKLOG_HANDLER              TxPeerBacklogHandler;
  MINIPORT_WDI_RX_STOP_HANDLER                      RxStopHandler;
  MINIPORT_WDI_RX_FLUSH_HANDLER                     RxFlushHandler;
  MINIPORT_WDI_RX_RESTART_HANDLER                   RxRestartHandler;
  MINIPORT_WDI_RX_GET_MPDUS_HANDLER                 RxGetMpdusHandler;
  MINIPORT_WDI_RX_RETURN_FRAMES_HANDLER             RxReturnFramesHandler;
  MINIPORT_WDI_RX_RESUME_HANDLER                    RxResumeHandler;
  MINIPORT_WDI_RX_THROTTLE_HANDLER                  RxThrottleHandler;
  MINIPORT_WDI_RX_PPDU_RSSI_HANDLER                 RxPpduRssiHandler;
  MINIPORT_WDI_TAL_TXRX_START_HANDLER               TalTxRxStartHandler;
  MINIPORT_WDI_TAL_TXRX_STOP_HANDLER                TalTxRxStopHandler;
  MINIPORT_WDI_TAL_TXRX_ADD_PORT_HANDLER            TalTxRxAddPortHandler;
  MINIPORT_WDI_TAL_TXRX_DELETE_PORT_HANDLER         TalTxRxDeletePortHandler;
  MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE_HANDLER     TalTxRxSetPortOpModeHandler;
  MINIPORT_WDI_TAL_TXRX_RESET_PORT_HANDLER          TalTxRxResetPortHandler;
  MINIPORT_WDI_TAL_TXRX_PEER_CONFIG_HANDLER         TalTxRxPeerConfigHandler;
  MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM_HANDLER TalTxRxPeerDeleteConfirmHandler;
} NDIS_MINIPORT_WDI_DATA_HANDLERS, *PNDIS_MINIPORT_WDI_DATA_HANDLERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_WDI_DATA_HANDLERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_WDI_DATA_HANDLERS.
     

To indicate the version of the NDIS_MINIPORT_WDI_DATA_HANDLERS structure, set the 
     <b>Revision</b> member to the following value:





#### NDIS_OBJECT_TYPE_MINIPORT_WDI_DATA_HANDLERS_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_WDI_DATA_HANDLERS_REVISION_1.


### -field TxAbortHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_abort.md">MiniportWdiTxAbort</a> handler function.


### -field TxTargetDescInitHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_target_desc_init.md">MiniportWdiTxTargetDescInit</a> handler function.


### -field TxTargetDescDeInitHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_target_desc_deinit.md">MiniportWdiTxTargetDescDeInit</a> handler function.


### -field TxDataSendHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_data_send.md">MiniportWdiTxDataSend</a> handler function.


### -field TxTalSendHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_send.md">MiniportWdiTxTalSend</a> handler function.


### -field TxTalSendCompleteHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_send_complete.md">MiniportWdiTxTalSendComplete</a> handler function.


### -field TxTalQueueInOrderHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md">MiniportWdiTxTalQueueInOrder</a> handler function.


### -field TxPeerBacklogHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_peer_backlog.md">MiniportWdiTxPeerBacklog</a> handler function.


### -field RxStopHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_stop.md">MiniportWdiRxStop</a> handler function.


### -field RxFlushHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_flush.md">MiniportWdiRxFlush</a> handler function.


### -field RxRestartHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_restart.md">MiniportWdiRxRestart</a> handler function.


### -field RxGetMpdusHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_get_mpdus.md">MiniportWdiRxGetMpdus</a> handler function.


### -field RxReturnFramesHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_return_frames.md">MiniportWdiRxReturnFrames</a> handler function.


### -field RxResumeHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_resume.md">MiniportWdiRxResume</a> handler function.


### -field RxThrottleHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_throttle.md">MiniportWdiRxThrottle</a> handler function.


### -field RxPpduRssiHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_ppdu_rssi.md">MiniportWdiRxPpduRssi</a> handler function.


### -field TalTxRxStartHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_start.md">MiniportWdiTalTxRxStart</a> handler function.


### -field TalTxRxStopHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_stop.md">MiniportWdiTalTxRxStop</a> handler function.


### -field TalTxRxAddPortHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_add_port.md">MiniportWdiTalTxRxAddPort</a> handler function.


### -field TalTxRxDeletePortHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_delete_port.md">MiniportWdiTalTxRxDeletePort</a> handler function.


### -field TalTxRxSetPortOpModeHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_set_port_opmode.md">MiniportWdiTalTxRxSetPortOpMode</a> handler function.


### -field TalTxRxResetPortHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_reset_port.md">MiniportWdiTalTxRxResetPort</a> handler function.


### -field TalTxRxPeerConfigHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_config.md">MiniportWdiTalTxRxPeerConfig</a> handler function.


### -field TalTxRxPeerDeleteConfirmHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm.md">MiniportWdiTalTxRxPeerDeleteConfirm</a> handler function.


### -field TxSuspectFrameAbortHandler

 



