---
UID: NC:dot11wdi.NDIS_WDI_TX_RELEASE_FRAMES_IND
title: NDIS_WDI_TX_RELEASE_FRAMES_IND (dot11wdi.h)
description: The NdisWdiTxReleaseFrameIndication callback function releases up to a specified number or aggregate cost of frames queued to a given peer-TID combination when transmission is paused.
old-location: netvista\ndiswditxreleaseframesindication.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WDI_TX_RELEASE_FRAMES_IND callback function"]
ms.keywords: NDIS_WDI_TX_RELEASE_FRAMES_IND, NDIS_WDI_TX_RELEASE_FRAMES_IND callback, NdisWdiTxReleaseFrameIndication, NdisWdiTxReleaseFrameIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxReleaseFrameIndication, netvista.ndiswditxreleaseframesindication
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
 - NDIS_WDI_TX_RELEASE_FRAMES_IND
 - dot11wdi/NDIS_WDI_TX_RELEASE_FRAMES_IND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - NdisWdiTxReleaseFrameIndication
---

# NDIS_WDI_TX_RELEASE_FRAMES_IND callback function


## -description

The NdisWdiTxReleaseFrameIndication callback function releases up to a specified number or aggregate cost of frames queued to a given peer-TID combination when transmission is paused.  If the specified queues are not paused, none of the NET_BUFFER_LISTs are released.

This is a callback inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.

## -parameters

### -param NdisMiniportDataPathHandle 

[in]
The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId 

[in]
The port ID. Must be a non-wildcard value.

### -param PeerId 

[in]
The peer ID. Must be a non-wildcard value.

### -param ExTidBitmask 

[in]
The Extended TID bitmask.

### -param MaxNumFrames 

[in]
Maximum frame count. <i>MaxNumFrames</i> is ignored if it is set to <b>WDI_TX_MAX_FRAME_COUNT_INVALID</b> (0xFF).

### -param Credit 

[in]
Credit. <i>Credit</i> is ignored if it is set to <b>WDI_TX_CREDIT_INVALID</b> (0xFFFF).

### -param ppNBL 

[out]
Pointer to a pointer to a <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> chain of released frames.

## -remarks

if one of the specified queues is paused with <b>WDI_TX_PAUSE_REASON_PS</b>, the TAL/Target does not issue this indication until it has received a <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order">MiniportWdiTxTalQueueInOrder</a> indication for that queue.

This indication is only allowed when <b>TargetPriorityQueueing</b> is false.

The TxMgr may return a list of <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> that exceed the limit of the number of frames or frame cost. This only happens if the frames are being requeued after being send completed with status of Postponed and with identical sequence number, which indicates they were originally transmitted as part of a single A-MSDU.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order">MiniportWdiTxTalQueueInOrder</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a>



<a href="/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_txrx_target_capabilities">WDI_TXRX_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_pause_reason">WDI_TX_PAUSE_REASON</a>
