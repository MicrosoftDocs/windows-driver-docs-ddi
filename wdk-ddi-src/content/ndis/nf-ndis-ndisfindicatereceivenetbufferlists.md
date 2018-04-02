---
UID: NF:ndis.NdisFIndicateReceiveNetBufferLists
title: NdisFIndicateReceiveNetBufferLists function
author: windows-driver-content
description: A filter driver calls NdisFIndicateReceiveNetBufferLists to indicate that it has received network data. For more information, see Receiving Data in a Filter Driver.
old-location: netvista\ndisfindicatereceivenetbufferlists.htm
old-project: netvista
ms.assetid: ff2457bb-158a-411c-8c6b-7a7e402497ef
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFIndicateReceiveNetBufferLists, NdisFIndicateReceiveNetBufferLists function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_b3c09e67-4d25-4e8f-89e2-d227cf0f10b8.xml, ndis/NdisFIndicateReceiveNetBufferLists, netvista.ndisfindicatereceivenetbufferlists
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
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
-	NdisFIndicateReceiveNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFIndicateReceiveNetBufferLists function


## -description


A filter driver calls 
  <b>NdisFIndicateReceiveNetBufferLists</b> to indicate that it has received network data. For more information, see <a href="https://msdn.microsoft.com/4f6d44e9-c351-452d-aadf-505e6bb30fc2">Receiving Data in a Filter Driver</a>.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


### -param NetBufferLists [in]

A linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures. Each
     <b>NET_BUFFER_LIST</b> structure contains one 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.


### -param PortNumber [in]

A port number that identifies a miniport adapter port. Miniport adapter port numbers are assigned
     by calling the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a> function. A zero
     value identifies the default port of a miniport adapter.


### -param NumberOfNetBufferLists [in]

The number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that are in the linked list of structures at 
     <i>NetBufferLists</i> .


### -param ReceiveFlags [in]

Flags that define attributes for the receive indication. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     





#### NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is <b>DISPATCH_LEVEL</b>. For more information about this flag, see 
       <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_RECEIVE_FLAGS_RESOURCES

Specifies that the filter driver reclaims ownership of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures and any
       attached <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures immediately after the call to 
       <b>NdisFIndicateReceiveNetBufferLists</b> returns.



#### NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE

Specifies that all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> have the same protocol type (EtherType).



#### NDIS_RECEIVE_FLAGS_SINGLE_VLAN

Specifies that all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VLAN.



#### NDIS_RECEIVE_FLAGS_PERFECT_FILTERED

Specifies that all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
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



#### NDIS_RECEIVE_FLAGS_SWITCH_SINGLE_SOURCE

If this flag is set, all packets in a linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.

For more information, see <a href="https://msdn.microsoft.com/FBA506EC-4E9F-4964-9C9C-FF4910DDA908">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_RETURN_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>ReturnFlags</i> parameter of <a href="https://msdn.microsoft.com/8d7e362f-62da-4ce7-9497-1cfaff2b678e">FilterReturnNetBufferLists</a>  when the receive request completes. The extension must set this flag in the <i>ReturnFlags</i> parameter if it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff562613">NdisFReturnNetBufferLists</a> to return packets that it did not originate or clone.</div>
<div> </div>


#### NDIS_RECEIVE_FLAGS_SWITCH_DESTINATION_GROUP

If this flag is set, all packets in a linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures are to be forwarded to the same extensible switch destination port.

For more information, see <a href="https://msdn.microsoft.com/FBA506EC-4E9F-4964-9C9C-FF4910DDA908">Hyper-V Extensible Switch Send and Receive Flags</a>.


## -returns



None




## -remarks



When a filter driver calls the 
    <b>NdisFIndicateReceiveNetBufferLists</b> function, it specifies a list of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the 
    <i>NetBufferLists</i> parameter. NDIS passes the <b>NET_BUFFER_LIST</b> structures to the overlying drivers.

Filter drivers can call 
    <b>NdisFIndicateReceiveNetBufferLists</b> to originate a receive indication.

Filter drivers can also filter receive indications that are originated by underlying drivers. NDIS
    calls the 
    <a href="https://msdn.microsoft.com/6359c2a7-1208-41ea-bbf9-015c91b6e8f6">
    FilterReceiveNetBufferLists</a> function to filter such receive indications.

A filter driver must set the 
    <b>SourceHandle</b> member of each <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that it originates to the same value as the 
    <i>NdisFilterHandle</i> parameter. The filter driver must not modify the 
    <b>SourceHandle</b> member in any <b>NET_BUFFER_LIST</b> structures that it did not originate.

The filter driver must properly initialize the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures, attached 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures, and any attached MDLs.

If a filter driver calls the 
    <b>NdisFIndicateReceiveNetBufferLists</b> function and clears the <b>NDIS_RECEIVE_FLAG_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter, NDIS returns the indicated <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures to the filter
    driver's 
    <a href="https://msdn.microsoft.com/8d7e362f-62da-4ce7-9497-1cfaff2b678e">
    FilterReturnNetBufferLists</a> function. In this case, the filter driver must not reclaim the
    <b>NET_BUFFER_LIST</b> structures until NDIS returns the <b>NET_BUFFER_LIST</b> structures to 
    <i>FilterReturnNetBufferLists</i>.

If a filter driver calls 
    <b>NdisFIndicateReceiveNetBufferLists</b> and sets the <b>NDIS_RECEIVE_FLAG_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter, this indicates that the filter driver must regain ownership of the
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures immediately. In this case, NDIS does not call the filter driver's 
    <a href="https://msdn.microsoft.com/8d7e362f-62da-4ce7-9497-1cfaff2b678e">FilterReturnNetBufferLists</a> function to return the <b>NET_BUFFER_LIST</b> structures. Instead, NDIS returns
    the <b>NET_BUFFER_LIST</b> structures to the filter driver upon return from 
    <b>NdisFIndicateReceiveNetBufferLists</b>. The filter driver should reclaim the <b>NET_BUFFER_LIST</b>
    structures immediately after 
    <b>NdisFIndicateReceiveNetBufferLists</b> returns. To reclaim the <b>NET_BUFFER_LIST</b> structures, a filter
    driver can call its own 
    <i>FilterReturnNetBufferLists</i> function.

Setting the <b>NDIS_RECEIVE_FLAG_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter forces the overlying drivers to copy the network data and release the
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures to the filter driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/6359c2a7-1208-41ea-bbf9-015c91b6e8f6">FilterReceiveNetBufferLists</a>



<a href="https://msdn.microsoft.com/8d7e362f-62da-4ce7-9497-1cfaff2b678e">FilterReturnNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567211">NDIS_RECEIVE_QUEUE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a>



<a href="https://msdn.microsoft.com/4f6d44e9-c351-452d-aadf-505e6bb30fc2">Receiving Data in a Filter Driver</a>
 

 

