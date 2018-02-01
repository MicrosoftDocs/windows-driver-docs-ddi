---
UID: NC:dot11wdi.MINIPORT_WDI_TX_DATA_SEND
title: MINIPORT_WDI_TX_DATA_SEND
author: windows-driver-content
description: The MiniportWdiTxDataSend handler function specifies an RA-TID or port queue to transmit from. It is issued in the context of the TX thread from the operating system, resume indication, or a work item.
old-location: netvista\miniportwditxdatasend.htm
old-project: netvista
ms.assetid: A9EB1E8C-BD10-450F-9F4B-CD19C8AF13EA
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwditxdatasend, MiniportWdiTxDataSend callback function [Network Drivers Starting with Windows Vista], MiniportWdiTxDataSend, MINIPORT_WDI_TX_DATA_SEND, MINIPORT_WDI_TX_DATA_SEND, dot11wdi/MiniportWdiTxDataSend
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
-	MiniportWdiTxDataSend
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_TX_DATA_SEND callback


## -description


The 
  MiniportWdiTxDataSend handler function specifies an RA-TID or port queue to transmit from. It is issued in the context of the TX thread from the operating system, resume indication, or a work item.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_DATA_SEND</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_TX_DATA_SEND MiniportWdiTxDataSend;

VOID MiniportWdiTxDataSend(
  _In_ TAL_TXRX_HANDLE  MiniportTalTxRxContext,
  _In_ WDI_PORT_ID      PortId,
  _In_ WDI_PEER_ID      PeerId,
  _In_ WDI_EXTENDED_TID ExTid,
  _In_ UINT16           NumQueueFrames,
  _In_ UINT32           NumActiveFrames,
  _In_ BOOLEAN          bRobustnessFlag
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID.


### -param PeerId [in]

The peer ID.


### -param ExTid [in]

The Extended TID.


### -param NumQueueFrames [in]

The queue length, in frames.


### -param NumActiveFrames [in]

The total number of frames in action (schedulable) queues.


### -param bRobustnessFlag [in]

The robustness flag. If the robustness flag is set to TRUE, the NIC ensures reliable delivery within a small number of retries by aggressively lowering the TX data rate used for the frame using CTS and/or other mechanisms.


## -returns


This callback function does not return a value.



## -remarks


In port queuing mode, the <a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a> are set to wildcards.
In the context of the send request, the TxEngine issues <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_dequeue_ind.md">NdisWdiTxDequeueIndication</a> to take ownership of a number of frames from the FIFO RA-TID queue and transfer them to the target. If it cannot dequeue any frames, the TxEngine issues <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a> in the same context instead of <i>NdisWdiTxDequeueIndication</i>.

The TxEngine must issue a transfer complete and send complete indications to return ownership of any frames it dequeues to TxMgr.  If the transfer complete contains a failure code, the TxEngine must not issue a send completion.



## -see-also

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_dequeue_ind.md">NdisWdiTxDequeueIndication</a>

<a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TX_DATA_SEND callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

