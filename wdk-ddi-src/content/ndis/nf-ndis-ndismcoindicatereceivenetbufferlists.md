---
UID: NF:ndis.NdisMCoIndicateReceiveNetBufferLists
title: NdisMCoIndicateReceiveNetBufferLists function (ndis.h)
description: The NdisMCoIndicateReceiveNetBufferLists function indicates that the miniport driver received data from the network.
old-location: netvista\ndismcoindicatereceivenetbufferlists.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMCoIndicateReceiveNetBufferLists function"]
ms.keywords: NdisMCoIndicateReceiveNetBufferLists, NdisMCoIndicateReceiveNetBufferLists function [Network Drivers Starting with Windows Vista], condis_sendrcv_ref_98f228ff-027c-4b60-b469-3d9ead72ed6f.xml, ndis/NdisMCoIndicateReceiveNetBufferLists, netvista.ndismcoindicatereceivenetbufferlists
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCO_Function
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
 - NdisMCoIndicateReceiveNetBufferLists
 - ndis/NdisMCoIndicateReceiveNetBufferLists
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMCoIndicateReceiveNetBufferLists
---

# NdisMCoIndicateReceiveNetBufferLists function


## -description

The 
  <b>NdisMCoIndicateReceiveNetBufferLists</b> function indicates that the miniport driver received data from
  the network.

## -parameters

### -param NdisVcHandle [in]


A handle that identifies a virtual connection (VC). The miniport driver obtained this handle as an
     input parameter to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> function, either
     when a client set up an outgoing call or when the call manager created a VC for a client-registered
     service access point (SAP) to indicate an incoming-call notification on.

### -param NetBufferLists [in]


A linked list of 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures that the
     miniport driver allocated.

### -param NumberOfNetBufferLists [in]


The number of NET_BUFFER_LIST structures that are in the linked list of structures that 
     <i>NetBufferLists</i> specifies.

### -param CoReceiveFlags [in]


Flags that define attributes for the send operation. The flags can be combined with a bitwise OR
     operation. To clear all of the flags, set this parameter to zero. 
     <b>NdisMCoIndicateReceiveNetBufferLists</b> supports the following flags:
     





#### NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

The current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.



#### NDIS_RECEIVE_FLAGS_RESOURCES

The miniport driver reclaims ownership of the NET_BUFFER_LIST structures and any attached
       NET_BUFFER structures immediately after 
       <b>NdisMCoIndicateReceiveNetBufferLists</b> returns.

## -remarks

A miniport driver typically calls the 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> function from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a> function.
    When a miniport driver calls 
    <b>NdisMCoIndicateReceiveNetBufferLists</b>, it specifies a list of 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures at the 
    <i>NetBufferLists</i> parameter. NDIS then passes the NET_BUFFER_LIST structures to bound protocol drivers.

Miniport drivers must set the 
    <b>SourceHandle</b> member of each NET_BUFFER_LIST structure to the same value as the 
    <i>NdisVcHandle</i> parameter so that NDIS can return the NET_BUFFER_LIST structures to the correct
    miniport driver.

If a miniport driver calls 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> and clears the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>CoReceiveFlags</i> parameter, NDIS returns the NET_BUFFER_LIST structures that 
    <i>NetBufferLists</i> specifies to the miniport driver's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
    MiniportReturnNetBufferLists</a> function. In this case, the miniport driver must not reclaim the
    NET_BUFFER_LIST structures until NDIS returns the NET_BUFFER_LIST structures to the miniport driver's 
    <i>MiniportReturnNetBufferLists</i> function.

If a miniport driver calls 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> and sets the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>CoReceiveFlags</i> parameter, the miniport driver must regain ownership of the NET_BUFFER_LIST
    structures immediately. In this case, NDIS does not call the miniport driver's 
    <i>MiniportReturnNetBufferLists</i> function to return the NET_BUFFER_LIST structures. Instead, NDIS
    returns the NET_BUFFER_LIST structures to the miniport driver when 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> returns. The miniport driver should reclaim the
    NET_BUFFER_LIST structures immediately after 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> returns. To reclaim the NET_BUFFER_LIST structures, a miniport
    driver can call its own 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
    MiniportReturnNetBufferLists</a> function.

If a miniport driver sets the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>CoReceiveFlags</i> parameter, the protocol drivers must copy the network data and release the
    NET_BUFFER_LIST structures to the miniport driver. You should design your miniport drivers with enough
    preallocated NET_BUFFER_LIST structures to avoid unnecessary copying.

The caller of 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> must properly initialize the NET_BUFFER_LIST structures, the
    attached 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer">NET_BUFFER</a> structures, and any attached memory
    descriptor lists (MDLs).

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_return_net_buffer_lists">
   MiniportReturnNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>
