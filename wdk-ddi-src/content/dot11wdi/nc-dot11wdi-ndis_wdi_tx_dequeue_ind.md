---
UID: NC:dot11wdi.NDIS_WDI_TX_DEQUEUE_IND
title: NDIS_WDI_TX_DEQUEUE_IND
author: windows-driver-content
description: The NdisWdiTxDequeueIndication callback function is called in the context of a MiniportWdiTxDataSend or MiniportWdiTxTalSend by the IHV miniport to dequeue frames from WDI to the IHV miniport.
old-location: netvista\ndiswditxdequeueindication.htm
old-project: netvista
ms.assetid: ACCB45DA-1233-4276-A0F5-466E50D9377B
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndiswditxdequeueindication, NdisWdiTxDequeueIndication callback function [Network Drivers Starting with Windows Vista], NdisWdiTxDequeueIndication, NDIS_WDI_TX_DEQUEUE_IND, NDIS_WDI_TX_DEQUEUE_IND, dot11wdi/NdisWdiTxDequeueIndication
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
-	NdisWdiTxDequeueIndication
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_TX_DEQUEUE_IND callback


## -description


The 
  NdisWdiTxDequeueIndication callback function is called in the context of a <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_data_send.md">MiniportWdiTxDataSend</a> or <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_send.md">MiniportWdiTxTalSend</a> by the IHV miniport to dequeue frames from WDI to the IHV miniport.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_TX_DEQUEUE_IND NdisWdiTxDequeueIndication;

VOID NdisWdiTxDequeueIndication(
  _In_  NDIS_HANDLE      NdisMiniportDataPathHandle,
  _In_  UINT32           Quantum,
  _In_  UINT8            MaxNumFrames,
  _In_  UINT16           Credit,
  _Out_ PNET_BUFFER_LIST *ppNBL
)
{ ... }
````


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param Quantum [in]

The quantum. For more information, see the <i>Host - target TX transfer scheduling</i> section in <a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>.


### -param MaxNumFrames [in]

Maximum frame count.


### -param Credit [in]

Credit value. For more information, see <i>The target-credit scheme and the pause/resume mechanism</i> section in <a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>.


### -param *ppNBL [out]

Pointer to a pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain dequeued by WDI.


## -returns


This callback function does not return a value.



## -remarks


A subset of the parameters may not be applicable to a device. For instance, the maximum frame count may not apply to a store and forward device (message-based bus interface).

The following parameters are ignored by TxMgr under these circumstances.
<ul>
<li><i>Quantum</i> if set to <b>WDI_TX_QUANTUM_INVALID</b> (0xFFFFFFFF)</li>
<li><i>MaxNumFrames</i> if set to <b>WDI_TX_MAX_FRAME_COUNT_INVALID</b> (0xFF)</li>
<li><i>Credit</i> if set to <b>WDI_TX_CREDIT_INVALID</b> (0xFFFF)</li>
</ul>The TAL should provide accurate parameters whenever possible to guarantee fairness and avoid overwhelming TIL/target resources.  

If the TAL does not have enough credit to dequeue a maximum cost frame, it should issue an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a> instead of an <i>NdisWdiTxDequeueIndication</i>.

The TxMgr may return a list of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> that exceed the limit of the number of frames, frame cost, or quantum. This only happens if the frames are being requeued/replayed after being send completed with status of Postponed and with identical sequence number, which indicates they were originally transmitted as part of a single A-MSDU.



## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a>

<a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_dequeue_ind.md">NdisWdiTxDequeueIndication</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_DEQUEUE_IND callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

