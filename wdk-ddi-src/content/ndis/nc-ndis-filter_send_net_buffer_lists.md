---
UID: NC:ndis.FILTER_SEND_NET_BUFFER_LISTS
title: FILTER_SEND_NET_BUFFER_LISTS
author: windows-driver-content
description: NDIS calls the FilterSendNetBufferLists function to allow a filter driver to filter a linked list of NET_BUFFER_LIST structures.Note  You must declare the function by using the FILTER_SEND_NET_BUFFER_LISTS type.
old-location: netvista\filtersendnetbufferlists.htm
old-project: netvista
ms.assetid: 1b3fc0c8-95da-47e5-8ff1-b7967f5148e7
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FILTER_SEND_NET_BUFFER_LISTS, FILTER_SEND_NET_BUFFER_LISTS callback, FilterSendNetBufferLists, FilterSendNetBufferLists callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_576e3ac8-da80-4302-a0d5-41a1168336ee.xml, ndis/FilterSendNetBufferLists, netvista.filtersendnetbufferlists
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
-	FilterSendNetBufferLists
product: Windows
targetos: Windows
req.typenames: 
---

# FILTER_SEND_NET_BUFFER_LISTS callback function


## -description


NDIS calls the 
  <i>FilterSendNetBufferLists</i> function to allow a filter driver to filter a linked list of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_SEND_NET_BUFFER_LISTS</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


### -param NetBufferList


### -param PortNumber [in]

A port number that identifies a miniport adapter port. Miniport adapter port numbers are assigned
     by calling the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a> function. A zero
     value identifies the default port of a miniport adapter.


### -param SendFlags [in]

Flags that define attributes for the send operation. The flags can be combined with an OR operation.
      To clear all the flags, set this member to zero. This function supports the following flags:





#### NDIS_SEND_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
        <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK

Specifies that NDIS should check for loopback. By default, NDIS does not loop back data to the
        driver that submitted the send request. An overlying driver can override this behavior by setting
        this flag. When this flag is set, NDIS identifies all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures that contain data
        that matches the receive criteria for the binding. NDIS indicates <b>NET_BUFFER</b> structures that match
        the criteria to the overlying driver. This flag has no affect on checking for loopback, or looping
        back, on other bindings.



#### NDIS_SEND_FLAGS_SWITCH_SINGLE_SOURCE

If this flag is set, all packets in a linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.

For more information, see <a href="https://msdn.microsoft.com/FBA506EC-4E9F-4964-9C9C-FF4910DDA908">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_SEND_COMPLETE_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>SendCompleteFlags</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff562618">NdisFSendNetBufferListsComplete</a> when it completes the send request.</div>
<div> </div>
<div class="alert"><b>Note</b>  This flag is available in NDIS 6.30 and later.</div>
<div> </div>


#### NDIS_SEND_FLAGS_SWITCH_DESTINATION_GROUP

If this flag is set, all packets in a linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures are to be forwarded to the same extensible switch destination port.

For more information, see <a href="https://msdn.microsoft.com/FBA506EC-4E9F-4964-9C9C-FF4910DDA908">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  This flag is available in NDIS 6.30 and later.</div>
<div> </div>

#### - NetBufferLists [in]

A pointer to a linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that specify
     lists of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures. Each <b>NET_BUFFER</b> in the
     list maps a chain of MDLs that contain the transmit data.


## -returns



None




## -remarks



<i>FilterSendNetBufferLists</i> is an optional function. If a filter driver does not filter send requests,
    it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> function.

If a filter driver specifies a 
    <i>FilterSendNetBufferLists</i> function and it queues send requests, it must also specify a 
    <a href="https://msdn.microsoft.com/55979b0d-61a6-43da-8fa5-11159b1a48d1">
    FilterCancelSendNetBufferLists</a> function.

The filter driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function,
    from the 
    <a href="https://msdn.microsoft.com/04b7ac32-8996-4648-8c88-aa9f630b1bc4">FilterSetModuleOptions</a> function, to
    specify a 
    <i>FilterSendNetBufferLists</i> function for a filter module.

If the filter driver specifies a 
    <i>FilterSendNetBufferLists</i> function, NDIS calls this function to filter the data that is contained in
    a list of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures over the network. NDIS
    specifies a list of <b>NET_BUFFER</b> structures in each 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.

If the filter driver did not specify 
    <i>FilterSendNetBufferLists</i>, NDIS calls the next filter driver that is lower in the driver stack that
    did specify a 
    <i>FilterSendNetBufferLists</i> function. If there are no such underlying filter drivers, NDIS calls an
    underlying driver's 
    <a href="https://msdn.microsoft.com/0bd5966d-66a6-4548-8c84-7cedced2cf40">
    MiniportSendNetBufferLists</a> function.

The filter driver can filter the data and send the filtered data to underlying drivers. For each
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure submitted to 
    <i>FilterSendNetBufferLists</i>, a filter driver can do the following:

<ul>
<li>
Pass the buffer on to the next underlying driver by calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff562616">NdisFSendNetBufferLists</a> function. The filter driver can modify the buffer contents before calling
      
      <b>NdisFSendNetBufferLists</b>. In this case NDIS calls the 
      <a href="https://msdn.microsoft.com/1a3a1e80-29f1-4f19-b3c7-9a8b189f18c4">
      FilterSendNetBufferListsComplete</a> function after the underlying drivers complete the send
      request.

</li>
<li>
Reject the buffer by calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff562618">NdisFSendNetBufferListsComplete</a> function.

</li>
<li>
Queue the buffer in a local data structure for later processing.

</li>
<li>
Copy the buffer and originate a send request with the copy. The send operation is similar to a
      filter-driver initiated send request. In this case, the driver must return the original buffer to the
      overlying driver by calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff562618">NdisFSendNetBufferListsComplete</a> function.

</li>
</ul>
After the send operation is complete, a filter driver reverses the modifications, if any, to the
    buffer descriptors that it made in the 
    <i>FilterSendNetBufferLists</i> function. The driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562618">NdisFSendNetBufferListsComplete</a> function to return the linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures to
    the overlying drivers and to return the final status of the send request.

If a filter module is in the 
    <i>Paused</i> state, the filter driver must not originate any send requests for that filter module. If
    NDIS calls 
    <i>FilterSendNetBufferLists</i>, the driver must not call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562616">NdisFSendNetBufferLists</a> to pass on the data until the driver is restarted. The driver should call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562618">NdisFSendNetBufferListsComplete</a> immediately to complete the send operation. It should set the
    complete status in each <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure to NDIS_STATUS_PAUSED.

NDIS calls 
    <i>FilterSendNetBufferLists</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterSendNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterSendNetBufferLists</i> function that is named "MySendNetBufferLists", use the <b>FILTER_SEND_NET_BUFFER_LISTS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_SEND_NET_BUFFER_LISTS MySendNetBufferLists;</pre>
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
 MySendNetBufferLists(
    NDIS_HANDLE  FilterModuleContext,
    PNET_BUFFER_LIST  NetBufferLists,
    NDIS_PORT_NUMBER  PortNumber,
    ULONG  SendFlags
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_SEND_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_SEND_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/55979b0d-61a6-43da-8fa5-11159b1a48d1">
   FilterCancelSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/1a3a1e80-29f1-4f19-b3c7-9a8b189f18c4">
   FilterSendNetBufferListsComplete</a>



<a href="https://msdn.microsoft.com/04b7ac32-8996-4648-8c88-aa9f630b1bc4">FilterSetModuleOptions</a>



<a href="https://msdn.microsoft.com/0bd5966d-66a6-4548-8c84-7cedced2cf40">MiniportSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562616">NdisFSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/5a9008eb-86ad-4e3c-85a2-c8fd1b8fb4cb">
   NdisFSendNetBufferListsComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564672">NdisWriteEventLogEntry</a>
 

 

