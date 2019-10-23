---
UID: NC:ndis.FILTER_RECEIVE_NET_BUFFER_LISTS
title: FILTER_RECEIVE_NET_BUFFER_LISTS (ndis.h)
description: NDIS calls the FilterReceiveNetBufferLists function to request a filter driver to process a receive indication.Note  You must declare the function by using the FILTER_RECEIVE_NET_BUFFER_LISTS type.
old-location: netvista\filterreceivenetbufferlists.htm
tech.root: netvista
ms.assetid: 6359c2a7-1208-41ea-bbf9-015c91b6e8f6
ms.date: 05/02/2018
ms.keywords: FILTER_RECEIVE_NET_BUFFER_LISTS, FILTER_RECEIVE_NET_BUFFER_LISTS callback, FilterReceiveNetBufferLists, FilterReceiveNetBufferLists callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_c78036bd-cb6a-4898-b8b3-2d8585c7cfde.xml, ndis/FilterReceiveNetBufferLists, netvista.filterreceivenetbufferlists
ms.topic: callback
f1_keywords:
 - "ndis/FilterReceiveNetBufferLists"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- FilterReceiveNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: 
---

# FILTER_RECEIVE_NET_BUFFER_LISTS callback function


## -description


NDIS calls the 
  <i>FilterReceiveNetBufferLists</i> function to request a filter driver to process a receive
  indication.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_RECEIVE_NET_BUFFER_LISTS</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param NetBufferLists [in]

A linked list of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that were
     allocated by underlying drivers. Each <b>NET_BUFFER_LIST</b> structure contains one 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.


### -param PortNumber [in]

A port number that identifies a miniport adapter port. Miniport adapter port numbers are assigned
     by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocateport">NdisMAllocatePort</a> function. A zero
     value identifies the default port of a miniport adapter.


### -param NumberOfNetBufferLists [in]

The number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that are in the linked list of structures at 
     <i>NetBufferLists</i> .


### -param ReceiveFlags [in]

Flags that define attributes for the receive indication. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     





#### NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.



#### NDIS_RECEIVE_FLAGS_RESOURCES

Specifies that NDIS reclaims ownership of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures and any attached
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures immediately after the call to 
       <i>FilterReceiveNetBufferLists</i> returns.



#### NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE

Specifies that all the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> have the same protocol type (EtherType).



#### NDIS_RECEIVE_FLAGS_SINGLE_VLAN

Specifies that all the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VLAN.



#### NDIS_RECEIVE_FLAGS_PERFECT_FILTERED

Specifies that all the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> include only data that matches the packet filter and multicast address list that are
       assigned to the miniport adapter.



#### NDIS_RECEIVE_FLAGS_SINGLE_QUEUE

Specifies that all the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VM queue. A miniport driver must set this flag for all receive
       indications on a queue if the NDIS_RECEIVE_QUEUE_PARAMETERS_PER_QUEUE_RECEIVE_INDICATION flag was set
       in the 
       <b>Flags</b> member of the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_parameters">
       NDIS_RECEIVE_QUEUE_PARAMETERS</a> structure when that queue was allocated.



#### NDIS_RECEIVE_FLAGS_SHARED_MEMORY_INFO_VALID

Specifies that all the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> contain shared memory information that is valid. When this flag is set on a
       received <b>NET_BUFFER_LIST</b>, NDIS treats the shared memory information as valid. When this flag is not
       set, NDIS and drivers ignore the shared memory information. For example, intermediate drivers that
       modify packet data can use this flag to determine if data should be copied. Miniport drivers can use
       the flag to determine how to free the memory that is associated with a VM queue when a queue is
       deleted.



#### NDIS_RECEIVE_FLAGS_MORE_NBLS

Reserved.



#### NDIS_RECEIVE_FLAGS_SWITCH_SINGLE_SOURCE

If this flag is set, all packets in a linked list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-send-and-receive-flags">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_RETURN_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>ReturnFlags</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_return_net_buffer_lists">FilterReturnNetBufferLists</a>  when the receive request completes. The extension must set this flag in the <i>ReturnFlags</i> parameter if it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreturnnetbufferlists">NdisFReturnNetBufferLists</a> to return packets that it did not originate or clone.</div>
<div> </div>


#### NDIS_RECEIVE_FLAGS_SWITCH_DESTINATION_GROUP

If this flag is set, all packets in a linked list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures are to be forwarded to the same extensible switch destination port.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-send-and-receive-flags">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures uses the same destination ports, the extension should set the <b>NDIS_RECEIVE_FLAGS_SWITCH_DESTINATION_GROUP</b> flag in the <i>ReturnFlags</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_return_net_buffer_lists">FilterReturnNetBufferLists</a>  when the receive request completes. The extension must set this flag in the <i>ReturnFlags</i> parameter if it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreturnnetbufferlists">NdisFReturnNetBufferLists</a> to return packets that it did not originate or clone.</div>
<div> </div>

## -returns



None




## -remarks



<i>FilterReceiveNetBufferLists</i> is an optional function. If a filter driver does not filter receive
    indications, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function.

<div class="alert"><b>Note</b>  A filter driver that does provide a 
    <i>FilterReceiveNetBufferLists</i> function must provide a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_status">FilterStatus</a> function.</div>
<div> </div>
The filter driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a> function,
    from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_set_module_options">FilterSetModuleOptions</a> function,
    to specify a 
    <i>FilterReceiveNetBufferLists</i> function for a filter module.

NDIS calls 
    <i>FilterReceiveNetBufferLists</i> to process receive indications that are initiated by underlying
    drivers. NDIS can also call this function as a result of loopback.

If the filter driver did not specify a 
    <i>FilterReceiveNetBufferLists</i> function, NDIS calls the next higher filter driver in the stack that did specify a 
    <i>FilterReceiveNetBufferLists</i> function. If there is no such filter driver, NDIS calls an overlying
    driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_receive_net_buffer_lists">
    ProtocolReceiveNetBufferLists</a> function.

If the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter is not set, the filter driver retains ownership of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>
    structures until it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreturnnetbufferlists">
    NdisFReturnNetBufferLists</a> function.

If the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter is set, the filter driver cannot keep the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure and
    associated underlying-driver-allocated resources. This flag can indicate that the underlying driver is
    running low on receive resources. The 
    <i>FilterReceiveNetBufferLists</i> function should return as quickly as possible. Before returning, the 
    <i>FilterReceiveNetBufferLists</i> function can copy the received data into filter-driver-allocated
    storage or pass the buffer on by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfindicatereceivenetbufferlists">
    NdisFIndicateReceiveNetBufferLists</a> function.

<div class="alert"><b>Note</b>  If the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag is set, the filter driver must retain the
    original set of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the linked list. For example, when this flag is set the
    driver might process the structures and indicate them up the stack one at a time but before the function
    returns it must restore the original linked list.</div>
<div> </div>
Filter drivers can filter received data before indicating the data to overlying drivers. For each
    buffer that is submitted to its 
    <i>FilterReceiveNetBufferLists</i> function, a filter driver can do the following:

<ul>
<li>
Pass the buffer on to the next overlying driver by calling the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfindicatereceivenetbufferlists">
      NdisFIndicateReceiveNetBufferLists</a> function.

The driver can modify the contents of the buffer before calling 
      <b>NdisFIndicateReceiveNetBufferLists</b>.

The driver can change the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag setting that NDIS passed to 
      <i>FilterReceiveNetBufferLists</i> or simply pass it on to 
      <b>NdisFIndicateReceiveNetBufferLists</b>.

</li>
<li>
Discard the buffer. If NDIS cleared the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag, call the 
      <b>NdisFReturnNetBufferLists</b> function to discard the buffer. If NDIS set the
      <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag, take no action and return from 
      <i>FilterReceiveNetBufferLists</i> to discard the buffer.

</li>
<li>
Queue the buffer in a local data structure for later processing. If NDIS set the
      <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag of 
      <i>FilterReceiveNetBufferLists</i>, the filter driver must create a copy before returning from 
      <i>FilterReceiveNetBufferLists</i>.

</li>
<li>
Copy the buffer and originate a receive indication with the copy. The receive indication is similar
      to a filter-driver-initiated receive indication. In this case, the driver must return the original
      buffer to the underlying driver.

</li>
</ul>
If the filter driver called 
    <b>NdisFIndicateReceiveNetBufferLists</b> and did not set the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag, NDIS
    calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_return_net_buffer_lists">
    FilterReturnNetBufferLists</a> function for the filter module. In its 
    <i>FilterReturnNetBufferLists</i> function, the filter driver will undo the operations that it performed
    on the buffer on the receive indication path.

If a filter module is in the 
    <i>Paused</i> state, the filter driver must not originate any receive indications for that filter module.
    The filter driver must not pass buffers that it created to 
    <b>NdisFIndicateReceiveNetBufferLists</b>. However, the driver can pass on a receive indication from an
    underlying driver.

NDIS calls 
    <i>FilterReceiveNetBufferLists</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterReceiveNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterReceiveNetBufferLists</i> function that is named "MyReceiveNetBufferLists", use the <b>FILTER_RECEIVE_NET_BUFFER_LISTS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_RECEIVE_NET_BUFFER_LISTS MyReceiveNetBufferLists;</pre>
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
 MyReceiveNetBufferLists(
    NDIS_HANDLE  FilterModuleContext,
    PNET_BUFFER_LIST  NetBufferLists,
    NDIS_PORT_NUMBER  PortNumber,
    ULONG  NumberOfNetBufferLists,
    ULONG  ReceiveFlags
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_RECEIVE_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_RECEIVE_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_return_net_buffer_lists">FilterReturnNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_set_module_options">FilterSetModuleOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_parameters">NDIS_RECEIVE_QUEUE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfindicatereceivenetbufferlists">
   NdisFIndicateReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreturnnetbufferlists">NdisFReturnNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocateport">NdisMAllocatePort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_receive_net_buffer_lists">
   ProtocolReceiveNetBufferLists</a>
 

 

