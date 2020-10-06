---
UID: NF:ndis.NdisMIndicateReceiveNetBufferLists
title: NdisMIndicateReceiveNetBufferLists function (ndis.h)
description: Miniport drivers call the NdisMIndicateReceiveNetBufferLists function to indicate the receipt of data from the network.
old-location: netvista\ndismindicatereceivenetbufferlists.htm
tech.root: netvista
ms.assetid: b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b
ms.date: 05/02/2018
keywords: ["NdisMIndicateReceiveNetBufferLists function"]
ms.keywords: NdisMIndicateReceiveNetBufferLists, NdisMIndicateReceiveNetBufferLists function [Network Drivers Starting with Windows Vista], ndis/NdisMIndicateReceiveNetBufferLists, ndis_sendrcv_ref_3ef0c38f-53f7-44a0-adfc-443132743f50.xml, netvista.ndismindicatereceivenetbufferlists
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_SendRcv_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMIndicateReceiveNetBufferLists
 - ndis/NdisMIndicateReceiveNetBufferLists
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMIndicateReceiveNetBufferLists
---

# NdisMIndicateReceiveNetBufferLists function


## -description

Miniport drivers call the 
  <b>NdisMIndicateReceiveNetBufferLists</b> function to indicate the receipt of data from the network.

## -parameters

### -param MiniportAdapterHandle 

[in]
The miniport handle that NDIS passed to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.

### -param NetBufferList

A linked list of 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that the
     miniport driver allocated.

### -param PortNumber 

[in]
A port number that identifies a miniport adapter port. To assign a miniport adapter port number,
     call the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocateport">NdisMAllocatePort</a> function. A zero
     value identifies the default port of a miniport adapter. Use the default port if the miniport driver has
     not allocated ports for the specified adapter.

### -param NumberOfNetBufferLists 

[in]
The number of <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that are in the linked list of structures at 
     <i>NetBufferLists</i> .

### -param ReceiveFlags 

[in]
Flags that define attributes for the send operation. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     





#### NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.

#### NDIS_RECEIVE_FLAGS_RESOURCES

Specifies that the miniport driver reclaims ownership of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures and any
       attached <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures immediately after the call to 
       <b>NdisMIndicateReceiveNetBufferLists</b> returns.



#### NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE

Specifies that all of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at <i>NetBufferLists</i> have the same protocol type (EtherType).

**Miniport drivers**

NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE is optionally set by miniport drivers that are certain all NBLs in an NBL chain have the same EtherType. By setting this flag, the miniport driver informs NDIS and upper layer protocols that they do not have to examine each packet for its EtherType, which increases performance. Miniport drivers are never required to set this flag.

**Light-weight filters (LWFs)**

When indicating novel receives, a light-weight filter (LWF) can also optionally set NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE if it is certain that all NBLs in an NBL chain have the same EtherType. However, like miniport drivers, LWFs are never required to set this flag in this case, and can always choose to clear the flag.

When passing through receives from the lower layer, if a LWF changes the EtherType of the NBLs, the LWF **must** clear the flag if the NBLs no longer have the same EtherType.

When passing through receives from the lower layer, if a LWF changes the EtherType of the NBLs, the LWF can set optionally set this flag if it is certain that all NBLs in an NBL chain have the same EtherType. In this case, the LWF is never required to set this flag and can always choose to clear it.

When consuming receives from the lower layer, if this flag is set, a LWF can assume that each NBL in the chain has the same EtherType. The LWF is never required to read this flag and can instead choose to always read the EtherType from every NBL.

When combining multiple NBL chains, a LWF **must** clear this flag unless it is certain that the new NBL chain has a homogenous EtherType.

**Protocol drivers**

When consuming receives from the lower layer, if NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE is set, the protocol can assume that each NBL in the chain has the same EtherType. A protocol is never required to read this flag and can instead choose to always read the EtherType from every NBL.

#### NDIS_RECEIVE_FLAGS_SINGLE_VLAN

Specifies that all of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VLAN.



#### NDIS_RECEIVE_FLAGS_PERFECT_FILTERED

Specifies that all of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> include only data that matches the packet filter and multicast address list that are
       assigned to the miniport adapter.



#### NDIS_RECEIVE_FLAGS_SINGLE_QUEUE

Specifies that all the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VM queue. A miniport driver must set this flag for all receive
       indications on a queue if the <b>NDIS_RECEIVE_QUEUE_PARAMETERS_PER_QUEUE_RECEIVE_INDICATION</b> flag was set
       in the 
       <b>Flags</b> member of the 
       <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_parameters">
       NDIS_RECEIVE_QUEUE_PARAMETERS</a> structure when that queue was allocated.



#### NDIS_RECEIVE_FLAGS_SHARED_MEMORY_INFO_VALID

Specifies that all the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> contain shared memory information that is valid. When this flag is set on a
       received <b>NET_BUFFER_LIST</b>, NDIS treats the shared memory information as valid. When this flag is not
       set, NDIS and drivers ignore the shared memory information. For example, intermediate drivers that
       modify packet data can use this flag to determine if data should be copied. Miniport drivers can use
       the flag to determine how to free the memory that is associated with a VM queue when a queue is
       deleted.



#### NDIS_RECEIVE_FLAGS_MORE_NBLS

Reserved.

## -remarks

A miniport driver typically calls the 
    <b>NdisMIndicateReceiveNetBufferLists</b> function from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a> function.
    When a miniport driver calls 
    <b>NdisMIndicateReceiveNetBufferLists</b>, it specifies a list of 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures in the 
    <i>NetBufferLists</i> parameter. NDIS passes the <b>NET_BUFFER_LIST</b> structures to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_receive_net_buffer_lists">
    ProtocolReceiveNetBufferLists</a> function of bound protocol drivers.

Miniport drivers must set the 
    <b>SourceHandle</b> member of each <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure to the same value as the 
    <i>MiniportAdapterHandle</i> parameter.

If a miniport driver calls 
    <b>NdisMIndicateReceiveNetBufferLists</b> and clears the <b>NDIS_RECEIVE_FLAG_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter, NDIS returns the indicated <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures to the miniport
    driver's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
    MiniportReturnNetBufferLists</a> function. In this case, the miniport driver must not reclaim the
    <b>NET_BUFFER_LIST</b> structures until NDIS returns the <b>NET_BUFFER_LIST</b> structures to the miniport driver's 
    <i>MiniportReturnNetBufferLists</i> function.

If a miniport driver calls 
    <b>NdisMIndicateReceiveNetBufferLists</b> and sets the <b>NDIS_RECEIVE_FLAG_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter, this indicates that the miniport driver must regain ownership of the
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures immediately. In this case, NDIS does not call the miniport driver's 
    <i>MiniportReturnNetBufferLists</i> function to return the <b>NET_BUFFER_LIST</b> structures. Instead, NDIS
    returns the <b>NET_BUFFER_LIST</b> structures to the miniport driver upon return from 
    <b>NdisMIndicateReceiveNetBufferLists</b>. The miniport driver should reclaim the <b>NET_BUFFER_LIST</b>
    structures immediately after 
    <b>NdisMIndicateReceiveNetBufferLists</b> returns. To reclaim the <b>NET_BUFFER_LIST</b> structures, a miniport
    driver can call its own 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
    MiniportReturnNetBufferLists</a> function.

Setting the <b>NDIS_RECEIVE_FLAG_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter forces the protocol drivers to copy the network data and release the
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures to the miniport driver. Driver writers should design their miniport drivers
    with enough preallocated <b>NET_BUFFER_LIST</b> structures to avoid unnecessary copying.

The caller of 
    <b>NdisMIndicateReceiveNetBufferLists</b> must properly initialize the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures,
    attached 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures, and any attached MDLs.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
   MiniportReturnNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_parameters">NDIS_RECEIVE_QUEUE_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocateport">NdisMAllocatePort</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_receive_net_buffer_lists">
   ProtocolReceiveNetBufferLists</a>