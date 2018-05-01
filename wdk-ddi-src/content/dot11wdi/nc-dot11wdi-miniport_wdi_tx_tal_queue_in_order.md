---
UID: NC:dot11wdi.MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER
title: MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER
author: windows-driver-content
description: The MiniportWdiTxTalQueueInOrder handler function notifies the TAL target that one or more paused RA/TID queues (with WDI_TX_PAUSE_REASON_PS) is ready to transmit.
old-location: netvista\miniportwditxtalqueueinorder.htm
old-project: netvista
ms.assetid: E82E19EA-4336-49DE-9CE4-DFBA0A347DFE
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER, MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER callback, MiniportWdiTxTalQueueInOrder, MiniportWdiTxTalQueueInOrder callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxTalQueueInOrder, netvista.miniportwditxtalqueueinorder
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	MiniportWdiTxTalQueueInOrder
product: Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER callback function


## -description


The 
  MiniportWdiTxTalQueueInOrder handler function notifies the TAL target that one or more paused RA/TID queues (with <b>WDI_TX_PAUSE_REASON_PS</b>) is ready to transmit.

This means:
<ul>
<li>Each of the queues has no outstanding TX frames with TAL/target.</li>
<li>All frames that were TX completed with <b>WDI_TxFrameStatus_SendPostponed</b> were inserted in the RA-TID queue in the correct order.</li>
</ul>This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param PeerId [in]

The peer ID.


### -param ExTidBitmask [in]

The Extended TID bitmask.


## -returns



This callback function does not return a value.




## -remarks



The TAL/target waits for this notification before issuing a TX restart indication to a paused queue with <b>WDI_TX_PAUSE_REASON_PS</b>.

<div class="alert"><b>Note</b>  <b>WDI_TxFrameStatus_SendPostponed</b> is not allowed when <b>TargetPriorityQueueing</b> is TRUE, so this request is never made when in that mode. </div>
<div> </div>

#### Examples

To define a MiniportWdiTxTalQueueInOrder function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiTxTalQueueInOrder function that is named "MyTxTalQueueInOrder", use the <b>MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER MyTxTalQueueInOrder;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyTxTalQueueInOrder(
    TAL_TXRX_HANDLE MiniportTalTxRxContext,
    WDI_PEER_ID PeerId,
    UINT32 ExTidBitmask
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898187">WDI_TXRX_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898194">WDI_TX_FRAME_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898196">WDI_TX_PAUSE_REASON</a>
 

 

