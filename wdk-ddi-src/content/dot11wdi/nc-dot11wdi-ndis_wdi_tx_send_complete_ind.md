---
UID: NC:dot11wdi.NDIS_WDI_TX_SEND_COMPLETE_IND
title: NDIS_WDI_TX_SEND_COMPLETE_IND (dot11wdi.h)
description: The NdisWdiTxSendCompleteIndication callback function specifies an array of frame IDs associated with the target's sent frames.
old-location: netvista\ndiswditxsendcompleteindication.htm
tech.root: netvista
ms.assetid: A38BA15D-FDD8-41D1-87ED-2CABC1926962
ms.date: 05/02/2018
keywords: ["NDIS_WDI_TX_SEND_COMPLETE_IND callback function"]
ms.keywords: NDIS_WDI_TX_SEND_COMPLETE_IND, NDIS_WDI_TX_SEND_COMPLETE_IND callback, NdisWdiTxSendCompleteIndication, NdisWdiTxSendCompleteIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxSendCompleteIndication, netvista.ndiswditxsendcompleteindication
f1_keywords:
 - "dot11wdi/NdisWdiTxSendCompleteIndication"
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
- NdisWdiTxSendCompleteIndication
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_TX_SEND_COMPLETE_IND callback function


## -description


The NdisWdiTxSendCompleteIndication callback function specifies an array of frame IDs associated with the target's sent frames.

This is a callback inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.

Frames with different TX status values are completed in separate indications.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


### -param WifiTxFrameStatus [in]

The TX status, specified as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_frame_status">WDI_TX_FRAME_STATUS</a> value.


### -param NumCompletedSends [in]

The number of completed sends.


### -param *WifiTxFrameIdList [in]

An array of frame IDs. The size of the array is the value of <i>NumCompletedSends</i>.


### -param *WifiTxCompleteList [in, optional]

An array of TX completion data. The size of the array is the value of <i>NumCompletedSends</i>.


## -remarks




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_tx_complete_data">WDI_TX_COMPLETE_DATA</a> is optional for all status values unless the indicated frames are sent over-the-air and have a status of <b>WDI_TxFrameStatus_SendPostponed</b>. In that case, <b>WDI_TX_COMPLETE_DATA</b> is required.

A TX completion with a frame with <b>WDI_TxFrameStatus_SendPostponed</b> is identical to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_pause_ind">NdisWdiTxSendPauseIndication</a> with <b>WDI_TX_PAUSE_REASON_PS</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_pause_ind">NdisWdiTxSendPauseIndication</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_tx_complete_data">WDI_TX_COMPLETE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_frame_status">WDI_TX_FRAME_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_pause_reason">WDI_TX_PAUSE_REASON</a>
 

 

