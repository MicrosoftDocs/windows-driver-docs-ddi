---
UID: NC:dot11wdi.MINIPORT_WDI_TX_TARGET_DESC_DEINIT
title: MINIPORT_WDI_TX_TARGET_DESC_DEINIT
author: windows-driver-content
description: The MINIPORT_WDI_TX_TARGET_DESC_DEINIT callback function informs the TxEngine that the target TX descriptors associated with the NET_BUFFER_LIST (NBLs) in the NBL chain are no longer needed and can be freed.
old-location: netvista\miniportwditxtargetdescdeinit.htm
old-project: netvista
ms.assetid: C7C6C175-5E9D-4C6B-8A6B-F903DDE4DC78
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: MINIPORT_WDI_TX_TARGET_DESC_DEINIT, MiniportWdiTxTargetDescDeInit, MiniportWdiTxTargetDescDeInit callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxTargetDescDeInit, netvista.miniportwditxtargetdescdeinit
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
-	MiniportWdiTxTargetDescDeInit
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_TX_TARGET_DESC_DEINIT callback


## -description


The 
  <i>MINIPORT_WDI_TX_TARGET_DESC_DEINIT</i> callback function informs the TxEngine that the target TX descriptors associated with the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> (NBLs) in the NBL chain are no longer needed and can be freed.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_TARGET_DESC_DEINIT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_TX_TARGET_DESC_DEINIT MiniportWdiTxTargetDescDeInit;

VOID MiniportWdiTxTargetDescDeInit(
  _In_ TAL_TXRX_HANDLE  MiniportTalTxRxContext,
  _In_ PNET_BUFFER_LIST pNBL
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MINIPORT_WDI_TAL_TXRX_INITIALIZE</a> callback function.


### -param pNBL [in]

Pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain.


## -returns



This callback function does not return a value.




## -remarks



<div class="alert"><b>Important</b>  The IHV miniport is not permitted to make any indication in the context of this call.
The TxMgr serializes calls to <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">TxTargetDescDeInitHandler</a>.</div>
<div> </div>

#### Examples

To define a <i>MINIPORT_WDI_TX_TARGET_DESC_DEINIT</i> callback function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MINIPORT_WDI_TX_TARGET_DESC_DEINIT</i> callback function that is named "MyTxTargetDescDeInit", use the <b>MINIPORT_WDI_TX_TARGET_DESC_DEINIT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_WDI_TX_TARGET_DESC_DEINIT MyTxTargetDescDeInit;</pre>
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
 MyTxTargetDescDeInit(
    TAL_TXRX_HANDLE MiniportTalTxRxContext,
    PNET_BUFFER_LIST pNBL
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_WDI_TX_TARGET_DESC_DEINIT</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_TX_TARGET_DESC_DEINIT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TX_TARGET_DESC_DEINIT callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

