---
UID: NC:dot11wdi.MINIPORT_WDI_TX_TARGET_DESC_INIT
title: MINIPORT_WDI_TX_TARGET_DESC_INIT
author: windows-driver-content
description: The MINIPORT_WDI_TX_TARGET_DESC_INIT callback function associates an opaque target TX descriptor with the NET_BUFFER_LIST (MiniportReserved[1] field) and (if applicable) populates the TX cost field (in credit units) in the WDI_FRAME_METADATA buffer of the NET_BUFFER_LIST (MiniportReserved[0]).
old-location: netvista\miniportwditxtargetdescinit.htm
tech.root: netvista
ms.assetid: EAFE6F7D-6820-4626-863D-C28FBFFCE6A0
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: MINIPORT_WDI_TX_TARGET_DESC_INIT, MINIPORT_WDI_TX_TARGET_DESC_INIT callback, MiniportWdiTxTargetDescInit, MiniportWdiTxTargetDescInit callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxTargetDescInit, netvista.miniportwditxtargetdescinit
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
-	MiniportWdiTxTargetDescInit
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TX_TARGET_DESC_INIT callback function


## -description


The 
  <i>MINIPORT_WDI_TX_TARGET_DESC_INIT</i> callback function associates an opaque target TX descriptor with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> (<b>MiniportReserved[1]</b> field) and (if applicable) populates the TX cost field (in credit units) in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn897827">WDI_FRAME_METADATA</a> buffer of the <b>NET_BUFFER_LIST</b> (<b>MiniportReserved[0]</b>).

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_TARGET_DESC_INIT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt297580">MINIPORT_WDI_TAL_TXRX_INITIALIZE</a> callback function.


### -param pNBL [in]

Pointer to a single <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>.


### -param *pWifiStatus [out]

Pointer to the status set by the IHV to indicate the result of the <i>MINIPORT_WDI_TX_TARGET_DESC_INIT</i> callback function.


## -returns



This callback function does not return a value.




## -remarks



A status of <b>NDIS_STATUS_RESOURCES</b> must only be used when Tx descriptors are exhausted.  The best behavior occurs if the IHV miniport does not use <b>NDIS_STATUS_RESOURCES</b>.  Any status other than <b>NDIS_STATUS_SUCCESS</b> and <b>NDIS_STATUS_RESOURCES</b> must be used for any other error that indicates the IHV miniport or firmware is unable to process the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>.

The IHV miniport may utilize the backfill in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> by using the appropriate NDIS retreat and advance functions.  The start of the packet offset must be restored before or in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt297593">MINIPORT_WDI_TX_TARGET_DESC_DEINIT</a> callback function.  The TxMgr determines the frame length during dequeue time so any change to the frame length in the <i>MINIPORT_WDI_TX_TARGET_DESC_INIT</i> callback function is included in limiting the dequeue size to the quantum.  In this case, the IHV miniport should appropriately adjust the quantum to account for the delta.

<div class="alert"><b>Important</b>  The IHV miniport is not permitted to make any indication in the context of this call.
The TxMgr serializes calls to <a href="https://msdn.microsoft.com/DBDB5F08-9988-4D9B-A731-DA65BBA67813">TxTargetDescInitHandler</a>.</div>
<div> </div>

#### Examples

To define a <i>MINIPORT_WDI_TX_TARGET_DESC_INIT</i> callback function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MINIPORT_WDI_TX_TARGET_DESC_INIT</i> callback function that is named "MyTxTargetDescInit", use the <b>MINIPORT_WDI_TX_TARGET_DESC_INIT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_WDI_TX_TARGET_DESC_INIT MyTxTargetDescInit;</pre>
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
 MyTxTargetDescInit(
    TAL_TXRX_HANDLE MiniportTalTxRxContext,
    PNET_BUFFER_LIST pNBL,
    NDIS_STATUS *pWifiStatus
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_WDI_TX_TARGET_DESC_INIT</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_TX_TARGET_DESC_INIT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297593">MINIPORT_WDI_TX_TARGET_DESC_DEINIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn897827">WDI_FRAME_METADATA</a>
 

 

