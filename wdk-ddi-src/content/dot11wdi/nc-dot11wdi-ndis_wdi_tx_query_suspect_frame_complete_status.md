---
UID: NC:dot11wdi.NDIS_WDI_TX_QUERY_SUSPECT_FRAME_COMPLETE_STATUS
title: NDIS_WDI_TX_QUERY_SUSPECT_FRAME_COMPLETE_STATUS
description: The TxQuerySuspectFrameStatus callback function is implemented by the IHV miniport to query the status of a suspect frame.
tech.root: netvista
ms.assetid: b3a6744f-f739-4dcc-b995-482875e552b0
ms.date: 04/02/2018
ms.topic: callback
req.header: dot11wdi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	dot11wdi.h
api_name: 
-	NDIS_WDI_TX_QUERY_SUSPECT_FRAME_COMPLETE_STATUS
product:
-	Windows
targetos: Windows
---

# NDIS_WDI_TX_QUERY_SUSPECT_FRAME_COMPLETE_STATUS callback function

## -description

The *TxQuerySuspectFrameStatus* callback function is implemented by the IHV miniport to query the status of a suspect frame.

## -prototype

```cpp
//Declaration

NDIS_WDI_TX_QUERY_SUSPECT_FRAME_COMPLETE_STATUS NdisWdiTxQuerySuspectFrameCompleteStatus; 

// Definition

void NdisWdiTxQuerySuspectFrameCompleteStatus 
(
	NDIS_HANDLE NdisMiniportDataPathHandle
	UINT64 SuspectFrameContext
	PNET_BUFFER_LIST pNBL
	BOOLEAN *pIsTransferCompleteNeeded
	BOOLEAN *pIsSendCompleteNeeded
	NDIS_STATUS *pWifiStatus
)
{...}

```

## -parameters

### -param NdisMiniportDataPathHandle

The NdisMiniportDataPathHandle passed to the IHV miniport in [MiniportWdiTalTxRxInitialize](nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md).

### -param SuspectFrameContext

Context information about the suspect frame.

### -param pNBL

A pointer to the suspect frame.

### -param *pIsTransferCompleteNeeded

A pointer to a BOOLEAN value that indicates if the frame requires the transfer completion callback to be invoked.

### -param *pIsSendCompleteNeeded

A pointer to a BOOLEAN value that indicates if the frame requires the send completion callback to be invoked.

### -param *pWifiStatus

A pointer to the status set by the IHV miniport to indicate the result of *TxQuerySuspectFrameStatus*.

## -returns

This callback function does not return a value.

## -remarks

Register your implementation of this callback function by setting the appropriate member of the [NDIS_WDI_DATA_API](ns-dot11wdi-_ndis_wdi_data_api.md) structure.

This callback is typically called from the context of the [*TxSuspectFrameListAbort*](nc-dot11wdi-miniport_wdi_tx_suspect_frame_list_abort.md) callback function.

## -see-also
