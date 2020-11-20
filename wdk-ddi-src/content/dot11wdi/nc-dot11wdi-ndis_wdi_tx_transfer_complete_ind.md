---
UID: NC:dot11wdi.NDIS_WDI_TX_TRANSFER_COMPLETE_IND
title: NDIS_WDI_TX_TRANSFER_COMPLETE_IND (dot11wdi.h)
description: The NdisWdiTxTransferCompleteIndication callback function specifies a list of frame buffers that have been transferred to the target. Frames with different TX Status values are completed in separate indications.
old-location: netvista\ndiswditxtransfercompleteindication.htm
tech.root: netvista
ms.assetid: BC66C993-F571-4EB9-8163-65B038ECE754
ms.date: 05/02/2018
keywords: ["NDIS_WDI_TX_TRANSFER_COMPLETE_IND callback function"]
ms.keywords: NDIS_WDI_TX_TRANSFER_COMPLETE_IND, NDIS_WDI_TX_TRANSFER_COMPLETE_IND callback, NdisWdiTxTransferCompleteIndication, NdisWdiTxTransferCompleteIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxTransferCompleteIndication, netvista.ndiswditxtransfercompleteindication
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
 - NDIS_WDI_TX_TRANSFER_COMPLETE_IND
 - dot11wdi/NDIS_WDI_TX_TRANSFER_COMPLETE_IND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - NdisWdiTxTransferCompleteIndication
---

# NDIS_WDI_TX_TRANSFER_COMPLETE_IND callback function


## -description

The NdisWdiTxTransferCompleteIndication callback function specifies a list of frame buffers that have been transferred to the target.
Frames with different TX Status values are completed in separate indications.

If the TX status is a failure code, an <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_complete_ind">NdisWdiTxSendCompleteIndication</a> is not indicated for any of the frames in the <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> (NBL) chain.

This is a callback inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.

## -parameters

### -param NdisMiniportDataPathHandle 

[in]
The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param WifiTxFrameStatus 

[in]
The TX status, specified as a <a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_frame_status">WDI_TX_FRAME_STATUS</a> value.

### -param pNBL 

[in]
The null-terminated list of frame buffers that have been transferred to the target.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_complete_ind">NdisWdiTxSendCompleteIndication</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_frame_status">WDI_TX_FRAME_STATUS</a>