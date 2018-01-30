---
UID: NC:dot11wdi.MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER
title: MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER
author: windows-driver-content
description: The MiniportWdiTxTalQueueInOrder handler function notifies the TAL target that one or more paused RA/TID queues (with WDI_TX_PAUSE_REASON_PS) is ready to transmit.
old-location: netvista\miniportwditxtalqueueinorder.htm
old-project: netvista
ms.assetid: E82E19EA-4336-49DE-9CE4-DFBA0A347DFE
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwditxtalqueueinorder, MiniportWdiTxTalQueueInOrder callback function [Network Drivers Starting with Windows Vista], MiniportWdiTxTalQueueInOrder, MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER, MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER, dot11wdi/MiniportWdiTxTalQueueInOrder
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	MiniportWdiTxTalQueueInOrder
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER callback


## -description


The 
  MiniportWdiTxTalQueueInOrder handler function notifies the TAL target that one or more paused RA/TID queues (with <b>WDI_TX_PAUSE_REASON_PS</b>) is ready to transmit.

This means:
<ul>
<li>Each of the queues has no outstanding TX frames with TAL/target.</li>
<li>All frames that were TX completed with <b>WDI_TxFrameStatus_SendPostponed</b> were inserted in the RA-TID queue in the correct order.</li>
</ul>This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER MiniportWdiTxTalQueueInOrder;

VOID MiniportWdiTxTalQueueInOrder(
  _In_ TAL_TXRX_HANDLE MiniportTalTxRxContext,
  _In_ WDI_PEER_ID     PeerId,
  _In_ UINT32          ExTidBitmask
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param PeerId [in]

The peer ID.


### -param ExTidBitmask [in]

The Extended TID bitmask.


## -returns


This callback function does not return a value.



## -remarks


The TAL/target waits for this notification before issuing a TX restart indication to a paused queue with <b>WDI_TX_PAUSE_REASON_PS</b>.
<div class="alert"><b>Note</b>  <b>WDI_TxFrameStatus_SendPostponed</b> is not allowed when <b>TargetPriorityQueueing</b> is TRUE, so this request is never made when in that mode. </div><div> </div>


## -see-also

<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_frame_status.md">WDI_TX_FRAME_STATUS</a>

<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>

<a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_target_capabilities.md">WDI_TXRX_CAPABILITIES</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

