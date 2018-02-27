---
UID: NA:dot11wdi
ms.assetid: b9b9a3d0-411a-3f22-b90a-dd065eaf4aa0
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Dot11Wdi.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Dot11Wdi.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NdisMDeregisterWdiMiniportDriver function](nf-dot11wdi-ndismderegisterwdiminiportdriver.md) | A miniport driver calls the NdisMDeregisterWdiMiniportDriver function to release resources that it allocated with a previous call to the NdisMRegisterWdiMiniportDriver function. |
| [NdisMRegisterWdiMiniportDriver function](nf-dot11wdi-ndismregisterwdiminiportdriver.md) | A miniport driver calls the NdisMRegisterWdiMiniportDriver function to register MiniportWdiXxx entry points with NDIS as the first step in initialization. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE callback](nc-dot11wdi-miniport_wdi_adapter_hang_diagnose.md) | The MiniportWdiAdapterHangDiagnose handler function is used to collect hardware control register states and optionally full firmware state. |
| [MINIPORT_WDI_ALLOCATE_ADAPTER callback](nc-dot11wdi-miniport_wdi_allocate_adapter.md) | The MiniportWdiAllocateAdapter handler function allocates a WDI miniport adapter. |
| [MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION callback](nc-dot11wdi-miniport_wdi_cancel_idle_notification.md) | NDIS calls the MiniportWdiCancelIdleNotification handler function to notify the WDI miniport driver that NDIS has detected activity on the suspended network adapter. |
| [MINIPORT_WDI_CLOSE_ADAPTER callback](nc-dot11wdi-miniport_wdi_close_adapter.md) | The MiniportWdiCloseAdapter handler function is used by the Microsoft component to initiate the Close Task operation on the IHV driver. |
| [MINIPORT_WDI_FREE_ADAPTER callback](nc-dot11wdi-miniport_wdi_free_adapter.md) | The MiniportWdiFreeAdapter handler function requests that the IHV driver deletes its software state. |
| [MINIPORT_WDI_IDLE_NOTIFICATION callback](nc-dot11wdi-miniport_wdi_idle_notification.md) | NDIS calls the MiniportWdiIdleNotification handler function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state. |
| [MINIPORT_WDI_OPEN_ADAPTER callback](nc-dot11wdi-miniport_wdi_open_adapter.md) | The MiniportWdiOpenAdapter handler function is used by the Microsoft component to initiate the Open Task operation on the IHV driver. |
| [MINIPORT_WDI_POST_ADAPTER_PAUSE callback](nc-dot11wdi-miniport_wdi_post_adapter_pause.md) | The MiniportWdiPostAdapterPause handler function is called by the Microsoft component after it finishes the data path clean up as part of the NDIS MiniportPause requirements. |
| [MINIPORT_WDI_POST_ADAPTER_RESTART callback](nc-dot11wdi-miniport_wdi_post_adapter_restart.md) | The MiniportWdiPostAdapterRestart handler function is called by the Microsoft component after it finishes restarting the data path as part of the NDIS MiniportRestart requirements. |
| [MINIPORT_WDI_RX_FLUSH callback](nc-dot11wdi-miniport_wdi_rx_flush.md) | The MiniportWdiRxFlush handler function is issued after the MiniportWdiRxStop operation is completed. Upon receiving the flush request, the target/RxEngine must discard all unindicated frames on the port/adapter before indicating RxFlushConfirm. |
| [MINIPORT_WDI_RX_GET_MPDUS callback](nc-dot11wdi-miniport_wdi_rx_get_mpdus.md) | The MiniportWdiRxGetMpdus handler function returns a NET_BUFFER_LIST chain. Each NET_BUFFER_LIST represents one MPDU. |
| [MINIPORT_WDI_RX_PPDU_RSSI callback](nc-dot11wdi-miniport_wdi_rx_ppdu_rssi.md) | The MiniportWdiRxPpduRssi handler function returns the absolute value of RSSI (in dB) for the PPDU. The RxMgr may request the RSSI only once per data indication using the PNET_BUFFER_LIST obtained from MiniportWdiRxGetMpdus. |
| [MINIPORT_WDI_RX_RESTART callback](nc-dot11wdi-miniport_wdi_rx_restart.md) | The MiniportWdiRxRestart handler function configures the RxEngine to restart indicating data traffic. This is issued following a MiniportWdiRxStop. |
| [MINIPORT_WDI_RX_RESUME callback](nc-dot11wdi-miniport_wdi_rx_resume.md) | The MiniportWdiRxResume handler function is issued by the RxMgr after it returns a pause status to a data indication. |
| [MINIPORT_WDI_RX_RETURN_FRAMES callback](nc-dot11wdi-miniport_wdi_rx_return_frames.md) | The MiniportWdiRxReturnFrames handler function returns a NET_BUFFER_LIST structure (and associated data buffers) to the TAL. |
| [MINIPORT_WDI_RX_STOP callback](nc-dot11wdi-miniport_wdi_rx_stop.md) | The MiniportWdiRxStop handler function stops RX on a given port and accepts the wildcard port ID to stop RX across the adapter. |
| [MINIPORT_WDI_RX_THROTTLE callback](nc-dot11wdi-miniport_wdi_rx_throttle.md) | The MiniportWdiRxThrottle handler function tells the TAL/target to enable mechanisms to reduce the rate of RX MSDUs. |
| [MINIPORT_WDI_START_ADAPTER_OPERATION callback](nc-dot11wdi-miniport_wdi_start_adapter_operation.md) | The MiniportWdiStartAdapterOperation handler function can be used by the IHV driver to perform any additional MiniportInitializeEx tasks. |
| [MINIPORT_WDI_STOP_ADAPTER_OPERATION callback](nc-dot11wdi-miniport_wdi_stop_adapter_operation.md) | The MiniportWdiStopAdapterOperation handler function can be used by the IHV driver to undo the operations performed in MiniportWdiStartAdapterOperation. |
| [MINIPORT_WDI_TAL_TXRX_ADD_PORT callback](nc-dot11wdi-miniport_wdi_tal_txrx_add_port.md) | The MiniportWdiTalTxRxAddPort handler function notifies the datapath components of the creation of a new virtual port. |
| [MINIPORT_WDI_TAL_TXRX_DEINITIALIZE callback](nc-dot11wdi-miniport_wdi_tal_txrx_deinitialize.md) | The MiniportWdiTalTxRxDeinitialize handler function is invoked in the context of miniport halt. The functional components RXEngine and TxEngine have already been stopped and any pending data frames completed/returned. |
| [MINIPORT_WDI_TAL_TXRX_DELETE_PORT callback](nc-dot11wdi-miniport_wdi_tal_txrx_delete_port.md) | The MiniportWdiTalTxRxDeletePort handler function notifies the datapath components of the deletion of a virtual port. |
| [MINIPORT_WDI_TAL_TXRX_INITIALIZE callback](nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md) | The MiniportWdiTalTxRxInitialize handler function initializes data structures in the TAL and exchanges datapath component handles between the UE and TAL. |
| [MINIPORT_WDI_TAL_TXRX_PEER_CONFIG callback](nc-dot11wdi-miniport_wdi_tal_txrx_peer_config.md) | The MiniportWdiTalTxRxPeerConfig handler function specifies the port ID, peer ID, and peer capabilities (for example, QoS capabilities). It is invoked after the peer has associated, which involves creation of the peer object in the TAL. |
| [MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM callback](nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm.md) | The MiniportWdiTalTxRxPeerDeleteConfirm handler function is invoked after the completion of a PeerDeleteIndication call which did not return success. |
| [MINIPORT_WDI_TAL_TXRX_RESET_PORT callback](nc-dot11wdi-miniport_wdi_tal_txrx_reset_port.md) | The MiniportWdiTalTxRxResetPort handler function is invoked before a dot11 reset task is issued to the target. |
| [MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE callback](nc-dot11wdi-miniport_wdi_tal_txrx_set_port_opmode.md) | The MiniportWdiTalTxRxSetPortOpMode handler function specifies the opmode used for the port so that the TxEngine and RxEngine enable the corresponding functionality. |
| [MINIPORT_WDI_TAL_TXRX_START callback](nc-dot11wdi-miniport_wdi_tal_txrx_start.md) | The MiniportWdiTalTxRxStart handler function provides TXRX configuration parameters to the TAL. |
| [MINIPORT_WDI_TAL_TXRX_STOP callback](nc-dot11wdi-miniport_wdi_tal_txrx_stop.md) | The MiniportWdiTalTxRxStop handler function stops TXRX communication between the TAL and the target. |
| [MINIPORT_WDI_TX_ABORT callback](nc-dot11wdi-miniport_wdi_tx_abort.md) | The MiniportWdiTxAbort handler function aborts outstanding TX frames for a given port or peer, which includes initiating the completion of frames owned by the TAL/target. |
| [MINIPORT_WDI_TX_DATA_SEND callback](nc-dot11wdi-miniport_wdi_tx_data_send.md) | The MiniportWdiTxDataSend handler function specifies an RA-TID or port queue to transmit from. It is issued in the context of the TX thread from the operating system, resume indication, or a work item. |
| [MINIPORT_WDI_TX_PEER_BACKLOG callback](nc-dot11wdi-miniport_wdi_tx_peer_backlog.md) | The MiniportWdiTxPeerBacklog handler function is issued when a paused peer has a change in backlog state. |
| [MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER callback](nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md) | The MiniportWdiTxTalQueueInOrder handler function notifies the TAL target that one or more paused RA/TID queues (with WDI_TX_PAUSE_REASON_PS) is ready to transmit. |
| [MINIPORT_WDI_TX_TAL_SEND callback](nc-dot11wdi-miniport_wdi_tx_tal_send.md) | The MiniportWdiTxTalSend handler function specifies an RA-TID or port queue to transmit from. |
| [MINIPORT_WDI_TX_TAL_SEND_COMPLETE callback](nc-dot11wdi-miniport_wdi_tx_tal_send_complete.md) | The MiniportWdiTxTalSendComplete handler function returns ownership of one or more TX frame injected by the TAL back to the TxEngine. |
| [MINIPORT_WDI_TX_TARGET_DESC_DEINIT callback](nc-dot11wdi-miniport_wdi_tx_target_desc_deinit.md) | The MINIPORT_WDI_TX_TARGET_DESC_DEINIT callback function informs the TxEngine that the target TX descriptors associated with the NET_BUFFER_LIST (NBLs) in the NBL chain are no longer needed and can be freed. |
| [MINIPORT_WDI_TX_TARGET_DESC_INIT callback](nc-dot11wdi-miniport_wdi_tx_target_desc_init.md) | The MINIPORT_WDI_TX_TARGET_DESC_INIT callback function associates an opaque target TX descriptor with the NET_BUFFER_LIST (MiniportReserved[1] field) and (if applicable) populates the TX cost field (in credit units) in the WDI_FRAME_METADATA buffer of the NET_BUFFER_LIST (MiniportReserved[0]). |
| [NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA callback](nc-dot11wdi-ndis_wdi_allocate_wdi_frame_metadata.md) | The NdisWdiAllocateWiFiFrameMetaData callback function allocates a frame metadata buffer. |
| [NDIS_WDI_CLOSE_ADAPTER_COMPLETE callback](nc-dot11wdi-ndis_wdi_close_adapter_complete.md) | The NdisWdiCloseAdapterComplete callback function is called by the IHV when a Close Task operation from MiniportWdiCloseAdapter has been successfully started. |
| [NDIS_WDI_FREE_WDI_FRAME_METADATA callback](nc-dot11wdi-ndis_wdi_free_wdi_frame_metadata.md) | The NdisWdiFreeWiFiFrameMetaData callback function frees a frame metadata buffer. |
| [NDIS_WDI_IDLE_NOTIFICATION_COMPLETE callback](nc-dot11wdi-ndis_wdi_idle_notification_complete.md) | Miniport drivers call NdisWdiIdleNotificationComplete callback function to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's MiniportWdiIdleNotification handler function. |
| [NDIS_WDI_IDLE_NOTIFICATION_CONFIRM callback](nc-dot11wdi-ndis_wdi_idle_notification_confirm.md) | Miniport drivers call NdisWdiIdleNotificationConfirm callback function to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state. |
| [NDIS_WDI_OPEN_ADAPTER_COMPLETE callback](nc-dot11wdi-ndis_wdi_open_adapter_complete.md) | The NdisWdiOpenAdapterComplete callback function is called by the IHV when an Open Task operation from MiniportWdiOpenAdapter has been successfully started. |
| [NDIS_WDI_PEER_CREATE_IND callback](nc-dot11wdi-ndis_wdi_peer_create_ind.md) | The NdisWdiPeerCreateIndication callback function specifies a peer ID to associate with a peer MAC address. |
| [NDIS_WDI_PEER_DELETE_IND callback](nc-dot11wdi-ndis_wdi_peer_delete_ind.md) | The NdisWdiPeerDeleteIndication callback function initiates the removal of the association of between a peer ID and a peer MAC address. |
| [NDIS_WDI_RX_FLUSH_CONFIRM callback](nc-dot11wdi-ndis_wdi_rx_flush_confirm.md) | The NdisWdiRxFlushConfirm callback function indicates completion of a MiniportWdiRxFlush request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing NdisWdiRxFlushConfirm. |
| [NDIS_WDI_RX_INORDER_DATA_IND callback](nc-dot11wdi-ndis_wdi_rx_inorder_data_ind.md) | The NdisWdiRxInorderDataIndication callback function informs the RxMgr that a list of specified RX frames in the correct order are present. |
| [NDIS_WDI_RX_STOP_CONFIRM callback](nc-dot11wdi-ndis_wdi_rx_stop_confirm.md) | The NdisWdiRxStopConfirm callback function indicates completion of a MiniportWdiRxStop request. |
| [NDIS_WDI_TX_ABORT_CONFIRM callback](nc-dot11wdi-ndis_wdi_tx_abort_confirm.md) | The NdisWdiTxAbortConfirm callback function indicates an asynchronous confirmation of a MiniportWdiTxAbort from WDI. |
| [NDIS_WDI_TX_DEQUEUE_IND callback](nc-dot11wdi-ndis_wdi_tx_dequeue_ind.md) | The NdisWdiTxDequeueIndication callback function is called in the context of a MiniportWdiTxDataSend or MiniportWdiTxTalSend by the IHV miniport to dequeue frames from WDI to the IHV miniport. |
| [NDIS_WDI_TX_INJECT_FRAME_IND callback](nc-dot11wdi-ndis_wdi_tx_inject_frame_ind.md) | The NdisWdiTxInjectFrameIndication callback function allows the LE to inject frames through the regular datapath (for example, authentication/association requests/responses, Wi-Fi Direct action frames). |
| [NDIS_WDI_TX_QUERY_RA_TID_STATE callback](nc-dot11wdi-ndis_wdi_tx_query_ra_tid_state.md) | The NdisWdiTxQueryRATIDState callback function is used by the TxEngine to query the state of a RA/TID or Port queue. |
| [NDIS_WDI_TX_RELEASE_FRAMES_IND callback](nc-dot11wdi-ndis_wdi_tx_release_frames_ind.md) | The NdisWdiTxReleaseFrameIndication callback function releases up to a specified number or aggregate cost of frames queued to a given peer-TID combination when transmission is paused. |
| [NDIS_WDI_TX_SEND_COMPLETE_IND callback](nc-dot11wdi-ndis_wdi_tx_send_complete_ind.md) | The NdisWdiTxSendCompleteIndication callback function specifies an array of frame IDs associated with the target's sent frames. |
| [NDIS_WDI_TX_SEND_PAUSE_IND callback](nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md) | The NdisWdiTxSendPauseIndication callback function pauses transmissions on a given port to a given peer or peer-TID combination. |
| [NDIS_WDI_TX_SEND_RESTART_IND callback](nc-dot11wdi-ndis_wdi_tx_send_restart_ind.md) | The NdisWdiTxSendRestartIndication callback function resumes transmission on a given port to a given peer or peer-TID combination. |
| [NDIS_WDI_TX_TRANSFER_COMPLETE_IND callback](nc-dot11wdi-ndis_wdi_tx_transfer_complete_ind.md) | The NdisWdiTxTransferCompleteIndication callback function specifies a list of frame buffers that have been transferred to the target. Frames with different TX Status values are completed in separate indications. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure](ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md) | The NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure defines the set of handlers that a WDI miniport driver must implement. |
| [_NDIS_MINIPORT_WDI_DATA_HANDLERS structure](ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md) | The NDIS_MINIPORT_WDI_DATA_HANDLERS structure specifies the entry points for the IHV miniport datapath handlers. |
| [_NDIS_WDI_DATA_API structure](ns-dot11wdi-_ndis_wdi_data_api.md) | The NDIS_WDI_DATA_API structure specifies the entry points for WDI data indications. |
| [_NDIS_WDI_INIT_PARAMETERS structure](ns-dot11wdi-_ndis_wdi_init_parameters.md) | The NDIS_WDI_INIT_PARAMETERS structure specifies the WDI functions provided by the operating system and called by the IHV WDI driver. |
| [_TAL_TXRX_PARAMETERS structure](ns-dot11wdi-_tal_txrx_parameters.md) | The TAL_TXRX_PARAMETERS structure defines the TAL TXRX parameters. |
| [_WDI_FRAME_METADATA structure](ns-dot11wdi-_wdi_frame_metadata.md) | The WDI_FRAME_METADATA structure defines the frame metadata. |
| [_WDI_MAC_ADDRESS structure](ns-dot11wdi-_wdi_mac_address.md) | The WDI_MAC_ADDRESS structure defines an IEEE media access control (MAC) address. |
| [_WDI_MESSAGE_HEADER structure](ns-dot11wdi-_wdi_message_header.md) | The WDI_MESSAGE_HEADER structure defines the WDI message header. All WDI command messages must start with this header. |
| [_WDI_P2P_SERVICE_NAME_HASH structure](ns-dot11wdi-_wdi_p2p_service_name_hash.md) | The WDI_P2P_SERVICE_NAME_HASH structure defines a hash of a WFDS Service Name. |
| [_WDI_RX_METADATA structure](ns-dot11wdi-_wdi_rx_metadata.md) | The WDI_RX_METADATA structure defines the RX metadata. |
| [_WDI_TXRX_MPDU_PN structure](ns-dot11wdi-_wdi_txrx_mpdu_pn.md) | The WDI_TXRX_MPDU_PN union defines the parameters that are passed down to the TXRX component. |
| [_WDI_TXRX_PARAMETERS structure](ns-dot11wdi-_wdi_txrx_parameters.md) | The WDI_TXRX_PARAMETERS structure defines the parameters that are passed down to the TXRX component. |
| [_WDI_TXRX_PEER_CFG structure](ns-dot11wdi-_wdi_txrx_peer_cfg.md) | The WDI_TXRX_PEER_CFG structure defines peer configuration. |
| [_WDI_TXRX_TARGET_CAPABILITIES structure](ns-dot11wdi-_wdi_txrx_target_capabilities.md) | The WDI_TXRX_CAPABILITIES structure defines the target capabilities. |
| [_WDI_TXRX_TARGET_CONFIGURATION structure](ns-dot11wdi-_wdi_txrx_target_configuration.md) | The WDI_TXRX_TARGET_CONFIGURATION structure defines the target configuration. |
| [_WDI_TX_COMPLETE_DATA structure](ns-dot11wdi-_wdi_tx_complete_data.md) | The WDI_TX_COMPLETE_DATA structure defines TX completion data. |
| [_WDI_TX_METADATA structure](ns-dot11wdi-_wdi_tx_metadata.md) | The WDI_TX_METADATA structure defines the TX metadata. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDI_EXEMPTION_ACTION_TYPE enumeration](ne-dot11wdi-_wdi_exemption_action_type.md) | The WDI_EXEMPTION_ACTION_TYPE enumeration defines the exemption types. |
| [_WDI_FRAME_PAYLOAD_TYPE enumeration](ne-dot11wdi-_wdi_frame_payload_type.md) | The WDI_FRAME_PAYLOAD_TYPE enumeration defines the frame payload type. |
| [_WDI_INTERCONNECT_TYPE enumeration](ne-dot11wdi-_wdi_interconnect_type.md) | The WDI_INTERCONNECT_TYPE enumeration defines the interconnect types. |
| [_WDI_OPERATION_MODE enumeration](ne-dot11wdi-_wdi_operation_mode.md) | The WDI_OPERATION_MODE enumeration defines operation modes. |
| [_WDI_RX_INDICATION_LEVEL enumeration](ne-dot11wdi-_wdi_rx_indication_level.md) | The WDI_RX_INDICATION_LEVEL enumeration defines the RX indication levels. |
| [_WDI_RX_THROTTLE_LEVEL enumeration](ne-dot11wdi-_wdi_rx_throttle_level.md) | The WDI_RX_THROTTLE_LEVEL enumeration defines the RX throttle level. The interpretation and implementation mechanisms of these throttle levels are defined by the independent hardware vendor (IHV). |
| [_WDI_TXRX_PEER_QOS_CAPS enumeration](ne-dot11wdi-_wdi_txrx_peer_qos_caps.md) | The WDI_TXRX_PEER_QOS_CAPS enumeration defines the Quality of Service (QoS) capabilities. |
| [_WDI_TX_FRAME_STATUS enumeration](ne-dot11wdi-_wdi_tx_frame_status.md) | The WDI_TX_FRAME_STATUS enumeration defines the TX frame status values. |
| [_WDI_TX_PAUSE_REASON enumeration](ne-dot11wdi-_wdi_tx_pause_reason.md) | The WDI_TX_PAUSE_REASON enumeration defines the reasons for a TX pause. |
| [eDiagnoseLevel enumeration](ne-dot11wdi-ediagnoselevel.md) | The eDiagnoseLevel enumeration defines the diagnosis levels for adapter hang diagnosis. |
