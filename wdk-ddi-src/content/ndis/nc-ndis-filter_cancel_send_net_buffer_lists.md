---
UID: NC:ndis.FILTER_CANCEL_SEND_NET_BUFFER_LISTS
title: FILTER_CANCEL_SEND_NET_BUFFER_LISTS
author: windows-driver-content
description: NDIS calls a filter driver's FilterCancelSendNetBufferLists function to cancel the transmission of all NET_BUFFER_LIST structures that are marked with a specified cancellation identifier.Note  You must declare the function by using the FILTER_CANCEL_SEND_NET_BUFFER_LISTS type. For more information, see the following Examples section.
old-location: netvista\filtercancelsendnetbufferlists.htm
old-project: netvista
ms.assetid: 55979b0d-61a6-43da-8fa5-11159b1a48d1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: (*FILTER_CANCEL_SEND_HANDLER)
req.alt-loc: Ndis.h
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# FILTER_CANCEL_SEND_NET_BUFFER_LISTS callback



## -description
NDIS calls a filter driver's 
  <i>FilterCancelSendNetBufferLists</i> function to cancel the transmission of all 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that are marked
  with a specified cancellation identifier.



## -prototype

````
FILTER_CANCEL_SEND_NET_BUFFER_LISTS FilterCancelSendNetBufferLists;

VOID FilterCancelSendNetBufferLists(
  _In_ NDIS_HANDLE FilterModuleContext,
  _In_ PVOID       CancelId
)
{ ... }

typedef FILTER_CANCEL_SEND_NET_BUFFER_LISTS (*FILTER_CANCEL_SEND_HANDLER);
````


## -parameters

### -param FilterModuleContext [in]

A handle to a context area that the filter driver allocated in its 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function. The filter driver
     uses this context area to maintain state information for a filter module.


### -param CancelId [in]

A cancellation identifier. This identifier specifies the NET_BUFFER_LIST structures that are being
     canceled.


## -returns
None


## -remarks
The
    <i>FilterCancelSendNetBufferLists</i> function is optional. If a filter driver does not filter send
    requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> function.

Filter drivers that queue 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures before sending
    should export a 
    <i>FilterCancelSendNetBufferLists</i> function. The 
    <i>FilterCancelSendNetBufferLists</i> function cancels the pending transmission of the specified
    NET_BUFFER_LIST structures.

When an overlying NDIS driver calls the 
    <a href="..\ndis\nf-ndis-ndiscancelsendnetbufferlists.md">
    NdisCancelSendNetBufferLists</a> or 
    <a href="..\ndis\nf-ndis-ndisfcancelsendnetbufferlists.md">
    NdisFCancelSendNetBufferLists</a> function, NDIS calls the 
    <i>FilterCancelSendNetBufferLists</i> function of the filter modules on the binding.

A filter driver's 
    <i>FilterCancelSendNetBufferLists</i> function performs the following operations:

Traverses its list of queued NET_BUFFER_LIST structures for the specified filter module and calls
      the 
      <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567299">
      NDIS_GET_NET_BUFFER_LIST_CANCEL_ID</a> macro to obtain the cancellation identifier for each queued
      NET_BUFFER_LIST structure. The filter driver compares the cancellation ID that
      NDIS_GET_NET_BUFFER_LIST_CANCEL_ID returns with the cancellation ID that NDIS passed to 
      <i>FilterCancelSendNetBufferLists</i>.

Removes from the send queue (unlinks) all 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures whose
      cancellation identifiers match the specified cancellation identifier.

Calls the 
      <a href="..\ndis\nf-ndis-ndisfsendnetbufferlistscomplete.md">
      NdisFSendNetBufferListsComplete</a> function for all unlinked NET_BUFFER_LIST structures to return
      the structures. The filter driver sets the status field of the NET_BUFFER_LIST structures to
      NDIS_STATUS_SEND_ABORTED.

Calls the 
      <b>NdisFCancelSendNetBufferLists</b> function to pass the cancel send request to underlying drivers.

NDIS calls 
    <i>FilterCancelSendNetBufferLists</i> at IRQL &lt;= DISPATCH_LEVEL.

To define a <i>FilterCancelSendNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterCancelSendNetBufferLists</i> function that is named "MyCancelSendNetBufferLists", use the <b>FILTER_CANCEL_SEND_NET_BUFFER_LISTS</b> type as shown in this code example:

Then, implement your function as follows:

The <b>FILTER_CANCEL_SEND_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_CANCEL_SEND_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567299">
   NDIS_GET_NET_BUFFER_LIST_CANCEL_ID</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscancelsendnetbufferlists.md">NdisCancelSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfcancelsendnetbufferlists.md">
   NdisFCancelSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfsendnetbufferlistscomplete.md">
   NdisFSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_CANCEL_SEND_NET_BUFFER_LISTS callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

