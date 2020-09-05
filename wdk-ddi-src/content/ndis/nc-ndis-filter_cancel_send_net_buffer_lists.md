---
UID: NC:ndis.FILTER_CANCEL_SEND_NET_BUFFER_LISTS
title: FILTER_CANCEL_SEND_NET_BUFFER_LISTS (ndis.h)
description: NDIS calls a filter driver's FilterCancelSendNetBufferLists function to cancel the transmission of all NET_BUFFER_LIST structures that are marked with a specified cancellation identifier.Note  You must declare the function by using the FILTER_CANCEL_SEND_NET_BUFFER_LISTS type. For more information, see the following Examples section.
old-location: netvista\filtercancelsendnetbufferlists.htm
tech.root: netvista
ms.assetid: 55979b0d-61a6-43da-8fa5-11159b1a48d1
ms.date: 05/02/2018
keywords: ["FILTER_CANCEL_SEND_NET_BUFFER_LISTS callback function"]
ms.keywords: "(*FILTER_CANCEL_SEND_HANDLER), (*FILTER_CANCEL_SEND_HANDLER) callback function [Network Drivers Starting with Windows Vista], FILTER_CANCEL_SEND_NET_BUFFER_LISTS, FILTER_CANCEL_SEND_NET_BUFFER_LISTS callback, FilterCancelSendNetBufferLists, FilterCancelSendNetBufferLists callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_4538f981-3e2c-496b-bbea-e85baf122257.xml, ndis/FilterCancelSendNetBufferLists, netvista.filtercancelsendnetbufferlists"
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FILTER_CANCEL_SEND_NET_BUFFER_LISTS
 - ndis/FILTER_CANCEL_SEND_NET_BUFFER_LISTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - (*FILTER_CANCEL_SEND_HANDLER)
---

# FILTER_CANCEL_SEND_NET_BUFFER_LISTS callback function


## -description

NDIS calls a filter driver's 
  <i>FilterCancelSendNetBufferLists</i> function to cancel the transmission of all 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that are marked
  with a specified cancellation identifier.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_CANCEL_SEND_NET_BUFFER_LISTS</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param FilterModuleContext 

[in]
A handle to a context area that the filter driver allocated in its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function. The filter driver
     uses this context area to maintain state information for a filter module.

### -param CancelId 

[in]
A cancellation identifier. This identifier specifies the NET_BUFFER_LIST structures that are being
     canceled.

## -remarks

The
    <i>FilterCancelSendNetBufferLists</i> function is optional. If a filter driver does not filter send
    requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function.

Filter drivers that queue 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures before sending
    should export a 
    <i>FilterCancelSendNetBufferLists</i> function. The 
    <i>FilterCancelSendNetBufferLists</i> function cancels the pending transmission of the specified
    NET_BUFFER_LIST structures.

When an overlying NDIS driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscancelsendnetbufferlists">
    NdisCancelSendNetBufferLists</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfcancelsendnetbufferlists">
    NdisFCancelSendNetBufferLists</a> function, NDIS calls the 
    <i>FilterCancelSendNetBufferLists</i> function of the filter modules on the binding.

A filter driver's 
    <i>FilterCancelSendNetBufferLists</i> function performs the following operations:

<ol>
<li>
Traverses its list of queued NET_BUFFER_LIST structures for the specified filter module and calls
      the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-set-net-buffer-list-cancel-id">
      NDIS_GET_NET_BUFFER_LIST_CANCEL_ID</a> macro to obtain the cancellation identifier for each queued
      NET_BUFFER_LIST structure. The filter driver compares the cancellation ID that
      NDIS_GET_NET_BUFFER_LIST_CANCEL_ID returns with the cancellation ID that NDIS passed to 
      <i>FilterCancelSendNetBufferLists</i>.

</li>
<li>
Removes from the send queue (unlinks) all 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures whose
      cancellation identifiers match the specified cancellation identifier.

</li>
<li>
Calls the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlistscomplete">
      NdisFSendNetBufferListsComplete</a> function for all unlinked NET_BUFFER_LIST structures to return
      the structures. The filter driver sets the status field of the NET_BUFFER_LIST structures to
      NDIS_STATUS_SEND_ABORTED.

</li>
<li>
Calls the 
      <b>NdisFCancelSendNetBufferLists</b> function to pass the cancel send request to underlying drivers.

</li>
</ol>
NDIS calls 
    <i>FilterCancelSendNetBufferLists</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterCancelSendNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterCancelSendNetBufferLists</i> function that is named "MyCancelSendNetBufferLists", use the <b>FILTER_CANCEL_SEND_NET_BUFFER_LISTS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_CANCEL_SEND_NET_BUFFER_LISTS MyCancelSendNetBufferLists;</pre>
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
 MyCancelSendNetBufferLists(
    NDIS_HANDLE  FilterModuleContext,
    PVOID  CancelId
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_CANCEL_SEND_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_CANCEL_SEND_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-set-net-buffer-list-cancel-id">
   NDIS_GET_NET_BUFFER_LIST_CANCEL_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscancelsendnetbufferlists">NdisCancelSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfcancelsendnetbufferlists">
   NdisFCancelSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlistscomplete">
   NdisFSendNetBufferListsComplete</a>

