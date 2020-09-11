---
UID: NC:dot11wdi.MINIPORT_WDI_TX_DATA_SEND
title: MINIPORT_WDI_TX_DATA_SEND (dot11wdi.h)
description: The MiniportWdiTxDataSend handler function specifies an RA-TID or port queue to transmit from. It is issued in the context of the TX thread from the operating system, resume indication, or a work item.
old-location: netvista\miniportwditxdatasend.htm
tech.root: netvista
ms.assetid: A9EB1E8C-BD10-450F-9F4B-CD19C8AF13EA
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_TX_DATA_SEND callback function"]
ms.keywords: MINIPORT_WDI_TX_DATA_SEND, MINIPORT_WDI_TX_DATA_SEND callback, MiniportWdiTxDataSend, MiniportWdiTxDataSend callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxDataSend, netvista.miniportwditxdatasend
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
 - MINIPORT_WDI_TX_DATA_SEND
 - dot11wdi/MINIPORT_WDI_TX_DATA_SEND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiTxDataSend
---

# MINIPORT_WDI_TX_DATA_SEND callback function


## -description

The 
  MiniportWdiTxDataSend handler function specifies an RA-TID or port queue to transmit from. It is issued in the context of the TX thread from the operating system, resume indication, or a work item.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_DATA_SEND</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext 

[in]
TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId 

[in]
The port ID.

### -param PeerId 

[in]
The peer ID.

### -param ExTid 

[in]
The Extended TID.

### -param NumQueueFrames 

[in]
The queue length, in frames.

### -param NumActiveFrames 

[in]
The total number of frames in action (schedulable) queues.

### -param bRobustnessFlag 

[in]
The robustness flag. If the robustness flag is set to TRUE, the NIC ensures reliable delivery within a small number of retries by aggressively lowering the TX data rate used for the frame using CTS and/or other mechanisms.

## -remarks

In port queuing mode, the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-extended-tid">WDI_EXTENDED_TID</a> are set to wildcards.
In the context of the send request, the TxEngine issues <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_dequeue_ind">NdisWdiTxDequeueIndication</a> to take ownership of a number of frames from the FIFO RA-TID queue and transfer them to the target. If it cannot dequeue any frames, the TxEngine issues <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_pause_ind">NdisWdiTxSendPauseIndication</a> in the same context instead of <i>NdisWdiTxDequeueIndication</i>.

The TxEngine must issue a transfer complete and send complete indications to return ownership of any frames it dequeues to TxMgr.  If the transfer complete contains a failure code, the TxEngine must not issue a send completion.


#### Examples

To define a MiniportWdiTxDataSend function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiTxDataSend function that is named "MyTxDataSend", use the <b>MINIPORT_WDI_TX_DATA_SEND</b> type as shown in this code example:


```
MINIPORT_WDI_TX_DATA_SEND MyTxDataSend;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyTxDataSend(
    TAL_TXRX_HANDLE MiniportTalTxRxContext,
    WDI_PORT_ID PortId,
    WDI_PEER_ID PeerId,
    WDI_EXTENDED_TID ExTid,
    UINT16 NumQueueFrames,
    UINT32 NumActiveFrames,
    BOOLEAN bRobustnessFlag
    )
  {...}
```

The <b>MINIPORT_WDI_TX_DATA_SEND</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_TX_DATA_SEND</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_dequeue_ind">NdisWdiTxDequeueIndication</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_pause_ind">NdisWdiTxSendPauseIndication</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-tx-path">WDI TX path</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-extended-tid">WDI_EXTENDED_TID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>

