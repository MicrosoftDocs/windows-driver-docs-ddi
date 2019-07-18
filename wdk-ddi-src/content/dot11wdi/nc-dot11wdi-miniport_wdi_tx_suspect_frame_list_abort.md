---
UID: NC:dot11wdi.MINIPORT_WDI_TX_SUSPECT_FRAME_LIST_ABORT
title: MINIPORT_WDI_TX_SUSPECT_FRAME_LIST_ABORT (dot11wdi.h)
description: The TxSuspectFrameListAbort callback function is implemented by the client driver to inform the TxEngine that the TxMgr has identified frames which are suspected of being hung or pending completion for a significant length of time.
tech.root: netvista
ms.assetid: c6d6e415-4995-4b26-b58e-a3b868ab5398
ms.date: 04/02/2018
ms.topic: callback
f1_keywords:
 - "dot11wdi/MINIPORT_WDI_TX_SUSPECT_FRAME_LIST_ABORT"
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
- apiref
api_type: 
- UserDefined
api_location: 
- dot11wdi.h
api_name: 
- MINIPORT_WDI_TX_SUSPECT_FRAME_LIST_ABORT
product:
- Windows
targetos: Windows
---

# MINIPORT_WDI_TX_SUSPECT_FRAME_LIST_ABORT callback function

## -description

The *TxSuspectFrameListAbort* callback function is implemented by the IHV miniport to inform the TxEngine that the TxMgr has identified frames which are suspected of being hung or pending completion for a significant length of time.

## -prototype

```cpp
//Declaration

MINIPORT_WDI_TX_SUSPECT_FRAME_LIST_ABORT MiniportWdiTxSuspectFrameListAbort; 

// Definition

void MiniportWdiTxSuspectFrameListAbort 
(
	TAL_TXRX_HANDLE MiniportTalTxRxContext
	UINT64 SuspectFrameContext
	UINT16 NumSuspectFrames
	PNET_BUFFER_LIST *SuspectFrameList
)
{...}

```

## -parameters

### -param MiniportTalTxRxContext

The TAL device handle returned by the IHV miniport in [MiniportWdiTalTxRxInitialize](nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md).

### -param SuspectFrameContext

Context information about the suspected frame. 

### -param NumSuspectFrames

The number of suspect frames.

### -param *SuspectFrameList

The list of suspected frames. For more information, see the Remarks section.

## -returns

This function does not return a value.

## -remarks

Register your implementation of this callback function by setting the appropriate member of the [NDIS_MINIPORT_WDI_DATA_HANDLERS](ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md) structure.

This is an optional handler. If the IHV miniport does not implement this callback's behavior, it should not set the function pointer in [NDIS_MINIPORT_WDI_DATA_HANDLERS](ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md) and WDI will not call this handler. However, if this callback's behavior is not implemented, the function pointer might still be set if the IHV miniport uses the *SuspectFrameList* to log IHV state for diagnostic purposes.

This callback function informs the TxEngine that the TxMgr has identified frames which are suspected of being hung or pending completion for a significant length of time. The *SuspectFrameList* array of NBL pointers, of which the **Next** pointer is not applicable, represent frames which the TxMgr is requesting prompt completion even if that results in the frame not being transmitted over the air.

The TxEngine might check the status of an NBL in the *SuspectFrameList* array by calling [*TxQuerySuspectFrameStatus*](nc-dot11wdi-ndis_wdi_tx_query_suspect_frame_complete_status.md) from the context of *TxSuspectFrameListAbort* with the *SuspectFrameContext* passed to the handler. The TxMgr will not call [TxTargetDescDeinit](nc-dot11wdi-miniport_wdi_tx_target_desc_deinit.md) for any NBLs in *SuspectFrameList* during the duration of *TxSuspectFrameAbort*, nor will it complete the frames to NDIS.

If the TxEngine or firmware has no knowledge or state for the suspect frame it should not issue completions for that suspect frame, as this might cause system corruption and/or double completions.

If a firmware stall or corruption is detected, an [NDIS_STATUS_WDI_INDICATION_FIRMWARE_STALLED](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wdi-indication-firmware-stalled) notification should be made to attempt recovery.

## -see-also
