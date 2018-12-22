---
UID: NC:ndis.MINIPORT_CANCEL_SEND
title: MINIPORT_CANCEL_SEND
description: NDIS calls a miniport driver's MiniportCancelSend function to cancel the transmission of all NET_BUFFER_LIST structures that are marked with a specified cancellation identifier.
old-location: netvista\miniportcancelsend.htm
tech.root: netvista
ms.assetid: 17111aa3-c02f-494a-af97-5ab34c152451
ms.date: 05/02/2018
ms.keywords: MINIPORT_CANCEL_SEND, MINIPORT_CANCEL_SEND callback, MiniportCancelSend, MiniportCancelSend callback function [Network Drivers Starting with Windows Vista], ndis/MiniportCancelSend, ndis_sendrcv_ref_86f1ff8c-c68b-49e3-8d77-883d7e055961.xml, netvista.miniportcancelsend
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	MiniportCancelSend
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_CANCEL_SEND callback function


## -description


NDIS calls a miniport driver's 
   <i>MiniportCancelSend</i> function to cancel the transmission of all 
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that are marked
   with a specified cancellation identifier.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CANCEL_SEND</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information about an adapter.


### -param CancelId [in]

A cancellation identifier. This identifier specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that are being
     canceled.


## -returns



None




## -remarks



Miniport drivers and intermediate drivers that queue send 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures export a 
    <i>MiniportCancelSend</i> function. The 
    <i>MiniportCancelSend</i> function cancels the pending transmission of the specified NET_BUFFER_LIST
    structures.

When an overlying NDIS driver calls the 
    <a href="https://msdn.microsoft.com/7b61db73-ddd4-4d46-b378-9a82fdf041ea">
    NdisCancelSendNetBufferLists</a> function, NDIS calls the 
    <i>MiniportCancelSend</i> function of the appropriate lower-level driver on the binding. NDIS makes this
    call only if the lower-level driver exports a 
    <i>MiniportCancelSend</i> function.

A miniport driver's 
    <i>MiniportCancelSend</i> function performs the following operations:

<ol>
<li>
Traverses its list of queued NET_BUFFER_LIST structures for the specified adapter and calls the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff567299">
      NDIS_GET_NET_BUFFER_LIST_CANCEL_ID</a> macro to obtain the cancellation identifier for each queued
      NET_BUFFER_LIST structure. The miniport driver compares the cancellation identifier that
      NDIS_GET_NET_BUFFER_LIST_CANCEL_ID returns with the cancellation identifier that NDIS passed to 
      <i>MiniportCancelSend</i>.

</li>
<li>
Removes from the send queue (un-links) all NET_BUFFER_LIST structures whose cancellation identifiers
      match the specified cancellation identifier.

</li>
<li>
Calls the 
      <a href="https://msdn.microsoft.com/33890582-5eba-4cc1-a0d9-ec07f18da453">
      NdisMSendNetBufferListsComplete</a> function for all unlinked NET_BUFFER_LIST structures to return
      the structures .The miniport driver sets the status field of the NET_BUFFER_LIST structures to
      NDIS_STATUS_SEND_ABORTED.

</li>
</ol>
An intermediate driver's 
    <i>MiniportCancelSend</i> function performs the following operations:

<ol>
<li>
Performs the operations in the preceding list for a miniport driver's
      <i>MiniportCancelSend</i> function.

</li>
<li>
Calls the 
      <a href="https://msdn.microsoft.com/7b61db73-ddd4-4d46-b378-9a82fdf041ea">
      NdisCancelSendNetBufferLists</a> function, specifying the binding that maps to the adapter that NDIS
      specified in the call to 
      <i>MiniportCancelSend</i>.

</li>
</ol>
NDIS calls 
    <i>MiniportCancelSend</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCancelSend</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCancelSend</i> function that is named "MyCancelSend", use the <b>MINIPORT_CANCEL_SEND</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_CANCEL_SEND MyCancelSend;</pre>
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
 MyCancelSend(
    NDIS_HANDLE  MiniportAdapterContext,
    PVOID  CancelId
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_CANCEL_SEND</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CANCEL_SEND</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567299">
   NDIS_GET_NET_BUFFER_LIST_CANCEL_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561623">NdisCancelSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/33890582-5eba-4cc1-a0d9-ec07f18da453">
   NdisMSendNetBufferListsComplete</a>
 

 

