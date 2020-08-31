---
UID: NS:dot11wdi._NDIS_WDI_DATA_API
title: _NDIS_WDI_DATA_API (dot11wdi.h)
description: The NDIS_WDI_DATA_API structure specifies the entry points for WDI data indications.
old-location: netvista\ndis_wdi_data_api.htm
tech.root: netvista
ms.assetid: 8C26D62E-711A-4CE7-BD2B-D78B794C67FB
ms.date: 05/02/2018
keywords: ["NDIS_WDI_DATA_API structure"]
ms.keywords: "*PNDIS_WDI_DATA_API, NDIS_WDI_DATA_API, NDIS_WDI_DATA_API structure [Network Drivers Starting with Windows Vista], PNDIS_WDI_DATA_API, PNDIS_WDI_DATA_API structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WDI_DATA_API, dot11wdi/NDIS_WDI_DATA_API, dot11wdi/PNDIS_WDI_DATA_API, netvista.ndis_wdi_data_api"
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
targetos: Windows
req.typenames: NDIS_WDI_DATA_API, *PNDIS_WDI_DATA_API
f1_keywords:
 - _NDIS_WDI_DATA_API
 - dot11wdi/_NDIS_WDI_DATA_API
 - PNDIS_WDI_DATA_API
 - dot11wdi/PNDIS_WDI_DATA_API
 - NDIS_WDI_DATA_API
 - dot11wdi/NDIS_WDI_DATA_API
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - NDIS_WDI_DATA_API
---

# _NDIS_WDI_DATA_API structure


## -description

The 
  NDIS_WDI_DATA_API structure specifies the entry points for WDI data indications.

## -struct-fields

### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_WDI_DATA_API structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_WDI_DATA_API.
     

To indicate the version of the NDIS_WDI_DATA_API structure, set the 
     <b>Revision</b> member to the following value:





#### NDIS_OBJECT_TYPE_WDI_DATA_API_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_WDI_DATA_API_REVISION_1.

### -field TxDequeueIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_dequeue_ind">NdisWdiTxDequeueIndication</a> callback function.

### -field TxTransferCompleteIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_transfer_complete_ind">NdisWdiTxTransferCompleteIndication</a> callback function.

### -field TxSendCompleteIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_complete_ind">NdisWdiTxSendCompleteIndication</a> callback function.

### -field TxQueryRATIDState

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_query_ra_tid_state">NdisWdiTxQueryRATIDState</a> callback function.

### -field TxSendPauseIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_pause_ind">NdisWdiTxSendPauseIndication</a> callback function.

### -field TxSendRestartIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_restart_ind">NdisWdiTxSendRestartIndication</a> callback function.

### -field TxReleaseFrameIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_release_frames_ind">NdisWdiTxReleaseFrameIndication</a> callback function.

### -field TxInjectFrameIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_inject_frame_ind">NdisWdiTxInjectFrameIndication</a> callback function.

### -field TxAbortConfirm

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_abort_confirm">NdisWdiTxAbortConfirm</a> callback function.

### -field RxInorderDataIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_rx_inorder_data_ind">NdisWdiRxInorderDataIndication</a> callback function.

### -field RxStopConfirm

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_rx_stop_confirm">NdisWdiRxStopConfirm</a> callback function.

### -field RxFlushConfirm

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_rx_flush_confirm">NdisWdiRxFlushConfirm</a> callback function.

### -field PeerCreateIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_peer_create_ind">NdisWdiPeerCreateIndication</a> callback function.

### -field PeerDeleteIndication

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_peer_delete_ind">NdisWdiPeerDeleteIndication</a> callback function.

### -field AllocateWiFiFrameMetaData

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_allocate_wdi_frame_metadata">NdisWdiAllocateWiFiFrameMetaData</a> callback function.

### -field FreeWiFiFrameMetaData

The entry point of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_free_wdi_frame_metadata">NdisWdiFreeWiFiFrameMetaData</a> callback function.

### -field TxQuerySuspectFrameCompleteStatus

The entry point of the [NdisWdiTxQuerySuspectFrameCompleteStatus](nc-dot11wdi-ndis_wdi_tx_query_suspect_frame_complete_status.md) callback function.

