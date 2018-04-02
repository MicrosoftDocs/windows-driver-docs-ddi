---
UID: NF:ndis.NdisMIndicateReceiveNetBufferLists
title: NdisMIndicateReceiveNetBufferLists function
author: windows-driver-content
description: Miniport drivers call the NdisMIndicateReceiveNetBufferLists function to indicate the receipt of data from the network.
old-location: netvista\ndismindicatereceivenetbufferlists.htm
old-project: netvista
ms.assetid: b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMIndicateReceiveNetBufferLists, NdisMIndicateReceiveNetBufferLists function [Network Drivers Starting with Windows Vista], ndis/NdisMIndicateReceiveNetBufferLists, ndis_sendrcv_ref_3ef0c38f-53f7-44a0-adfc-443132743f50.xml, netvista.ndismindicatereceivenetbufferlists
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMIndicateReceiveNetBufferLists
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMIndicateReceiveNetBufferLists function


## -description


Miniport drivers call the 
  <b>NdisMIndicateReceiveNetBufferLists</b> function to indicate the receipt of data from the network.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle that NDIS passed to the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param NetBufferList

TBD


### -param PortNumber [in]

A port number that identifies a miniport adapter port. To assign a miniport adapter port number,
     call the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a> function. A zero
     value identifies the default port of a miniport adapter. Use the default port if the miniport driver has
     not allocated ports for the specified adapter.


### -param NumberOfNetBufferLists [in]

The number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that are in the linked list of structures at 
     <i>NetBufferLists</i> .


### -param ReceiveFlags [in]

Flags that define attributes for the send operation. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     





#### NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_RECEIVE_FLAGS_RESOURCES

Specifies that the miniport driver reclaims ownership of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures and any
       attached <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures immediately after the call to 
       <b>NdisMIndicateReceiveNetBufferLists</b> returns.



#### NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE

Specifies that all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> have the same protocol type (EtherType).



#### NDIS_RECEIVE_FLAGS_SINGLE_VLAN

Specifies that all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VLAN.



#### NDIS_RECEIVE_FLAGS_PERFECT_FILTERED

Specifies that all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> include only data that matches the packet filter and multicast address list that are
       assigned to the miniport adapter.



#### NDIS_RECEIVE_FLAGS_SINGLE_QUEUE

Specifies that all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VM queue. A miniport driver must set this flag for all receive
       indications on a queue if the <b>NDIS_RECEIVE_QUEUE_PARAMETERS_PER_QUEUE_RECEIVE_INDICATION</b> flag was set
       in the 
       <b>Flags</b> member of the 
       <a href="https://msdn.microsoft.com/fba87554-766d-45e2-8257-584ee78dd873">
       NDIS_RECEIVE_QUEUE_PARAMETERS</a> structure when that queue was allocated.



#### NDIS_RECEIVE_FLAGS_SHARED_MEMORY_INFO_VALID

Specifies that all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> contain shared memory information that is valid. When this flag is set on a
       received <b>NET_BUFFER_LIST</b>, NDIS treats the shared memory information as valid. When this flag is not
       set, NDIS and drivers ignore the shared memory information. For example, intermediate drivers that
       modify packet data can use this flag to determine if data should be copied. Miniport drivers can use
       the flag to determine how to free the memory that is associated with a VM queue when a queue is
       deleted.



#### NDIS_RECEIVE_FLAGS_MORE_NBLS

Reserved.


#### - NetBufferLists [in]

A linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that the
     miniport driver allocated.


## -returns



None




## -remarks



A miniport driver typically calls the 
    <b>NdisMIndicateReceiveNetBufferLists</b> function from its 
    <a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a> function.
    When a miniport driver calls 
    <b>NdisMIndicateReceiveNetBufferLists</b>, it specifies a list of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the 
    <i>NetBufferLists</i> parameter. NDIS passes the <b>NET_BUFFER_LIST</b> structures to the 
    <a href="https://msdn.microsoft.com/c964b4b8-ab07-4a07-9965-5cc06c028c20">
    ProtocolReceiveNetBufferLists</a> function of bound protocol drivers.

Miniport drivers must set the 
    <b>SourceHandle</b> member of each <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure to the same value as the 
    <i>MiniportAdapterHandle</i> parameter.

If a miniport driver calls 
    <b>NdisMIndicateReceiveNetBufferLists</b> and clears the <b>NDIS_RECEIVE_FLAG_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter, NDIS returns the indicated <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures to the miniport
    driver's 
    <a href="https://msdn.microsoft.com/0f33ae87-164e-40dc-a915-28211a0d74b7">
    MiniportReturnNetBufferLists</a> function. In this case, the miniport driver must not reclaim the
    <b>NET_BUFFER_LIST</b> structures until NDIS returns the <b>NET_BUFFER_LIST</b> structures to the miniport driver's 
    <i>MiniportReturnNetBufferLists</i> function.

If a miniport driver calls 
    <b>NdisMIndicateReceiveNetBufferLists</b> and sets the <b>NDIS_RECEIVE_FLAG_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter, this indicates that the miniport driver must regain ownership of the
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures immediately. In this case, NDIS does not call the miniport driver's 
    <i>MiniportReturnNetBufferLists</i> function to return the <b>NET_BUFFER_LIST</b> structures. Instead, NDIS
    returns the <b>NET_BUFFER_LIST</b> structures to the miniport driver upon return from 
    <b>NdisMIndicateReceiveNetBufferLists</b>. The miniport driver should reclaim the <b>NET_BUFFER_LIST</b>
    structures immediately after 
    <b>NdisMIndicateReceiveNetBufferLists</b> returns. To reclaim the <b>NET_BUFFER_LIST</b> structures, a miniport
    driver can call its own 
    <a href="https://msdn.microsoft.com/0f33ae87-164e-40dc-a915-28211a0d74b7">
    MiniportReturnNetBufferLists</a> function.

Setting the <b>NDIS_RECEIVE_FLAG_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter forces the protocol drivers to copy the network data and release the
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures to the miniport driver. Driver writers should design their miniport drivers
    with enough preallocated <b>NET_BUFFER_LIST</b> structures to avoid unnecessary copying.

The caller of 
    <b>NdisMIndicateReceiveNetBufferLists</b> must properly initialize the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures,
    attached 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures, and any attached MDLs.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/0f33ae87-164e-40dc-a915-28211a0d74b7">
   MiniportReturnNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567211">NDIS_RECEIVE_QUEUE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a>



<a href="https://msdn.microsoft.com/c964b4b8-ab07-4a07-9965-5cc06c028c20">
   ProtocolReceiveNetBufferLists</a>
 

 

