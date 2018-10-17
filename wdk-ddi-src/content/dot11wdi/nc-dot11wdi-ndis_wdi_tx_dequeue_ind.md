---
UID: NC:dot11wdi.NDIS_WDI_TX_DEQUEUE_IND
title: NDIS_WDI_TX_DEQUEUE_IND
author: windows-driver-content
description: The NdisWdiTxDequeueIndication callback function is called in the context of a MiniportWdiTxDataSend or MiniportWdiTxTalSend by the IHV miniport to dequeue frames from WDI to the IHV miniport.
old-location: netvista\ndiswditxdequeueindication.htm
tech.root: netvista
ms.assetid: ACCB45DA-1233-4276-A0F5-466E50D9377B
ms.date: 5/2/2018
ms.keywords: NDIS_WDI_TX_DEQUEUE_IND, NDIS_WDI_TX_DEQUEUE_IND callback, NdisWdiTxDequeueIndication, NdisWdiTxDequeueIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxDequeueIndication, netvista.ndiswditxdequeueindication
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	NdisWdiTxDequeueIndication
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_TX_DEQUEUE_IND callback function


## -description


The 
  NdisWdiTxDequeueIndication callback function is called in the context of a <a href="https://msdn.microsoft.com/A9EB1E8C-BD10-450F-9F4B-CD19C8AF13EA">MiniportWdiTxDataSend</a> or <a href="https://msdn.microsoft.com/42489ADA-78BF-4EBF-A6EC-5484F82C46ED">MiniportWdiTxTalSend</a> by the IHV miniport to dequeue frames from WDI to the IHV miniport.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param Quantum [in]

The quantum. For more information, see the <i>Host - target TX transfer scheduling</i> section in <a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>.


### -param MaxNumFrames [in]

Maximum frame count.


### -param Credit [in]

Credit value. For more information, see <i>The target-credit scheme and the pause/resume mechanism</i> section in <a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>.


### -param *ppNBL [out]

Pointer to a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> chain dequeued by WDI.


## -returns



This callback function does not return a value.




## -remarks



A subset of the parameters may not be applicable to a device. For instance, the maximum frame count may not apply to a store and forward device (message-based bus interface).

The following parameters are ignored by TxMgr under these circumstances.

<ul>
<li><i>Quantum</i> if set to <b>WDI_TX_QUANTUM_INVALID</b> (0xFFFFFFFF)</li>
<li><i>MaxNumFrames</i> if set to <b>WDI_TX_MAX_FRAME_COUNT_INVALID</b> (0xFF)</li>
<li><i>Credit</i> if set to <b>WDI_TX_CREDIT_INVALID</b> (0xFFFF)</li>
</ul>
The TAL should provide accurate parameters whenever possible to guarantee fairness and avoid overwhelming TIL/target resources.  

If the TAL does not have enough credit to dequeue a maximum cost frame, it should issue an <a href="https://msdn.microsoft.com/A8001D08-36B8-4557-A763-103BDC807CA4">NdisWdiTxSendPauseIndication</a> instead of an <i>NdisWdiTxDequeueIndication</i>.

The TxMgr may return a list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> that exceed the limit of the number of frames, frame cost, or quantum. This only happens if the frames are being requeued/replayed after being send completed with status of Postponed and with identical sequence number, which indicates they were originally transmitted as part of a single A-MSDU.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/ACCB45DA-1233-4276-A0F5-466E50D9377B">NdisWdiTxDequeueIndication</a>



<a href="https://msdn.microsoft.com/A8001D08-36B8-4557-A763-103BDC807CA4">NdisWdiTxSendPauseIndication</a>



<a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>
 

 

