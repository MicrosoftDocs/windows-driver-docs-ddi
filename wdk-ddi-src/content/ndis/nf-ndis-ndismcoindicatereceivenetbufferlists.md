---
UID: NF:ndis.NdisMCoIndicateReceiveNetBufferLists
title: NdisMCoIndicateReceiveNetBufferLists function
author: windows-driver-content
description: The NdisMCoIndicateReceiveNetBufferLists function indicates that the miniport driver received data from the network.
old-location: netvista\ndismcoindicatereceivenetbufferlists.htm
old-project: netvista
ms.assetid: dabd472f-9877-4434-a534-e07a047e092f
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisMCoIndicateReceiveNetBufferLists, NdisMCoIndicateReceiveNetBufferLists function [Network Drivers Starting with Windows Vista], condis_sendrcv_ref_98f228ff-027c-4b60-b469-3d9ead72ed6f.xml, ndis/NdisMCoIndicateReceiveNetBufferLists, netvista.ndismcoindicatereceivenetbufferlists
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
req.ddi-compliance: Irql_MCO_Function
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
-	NdisMCoIndicateReceiveNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: 
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
     <a href="https://msdn.microsoft.com/99eaba29-ce17-4e79-878e-5fdf7411e56c">MiniportCoCreateVc</a> function, either
     when a client set up an outgoing call or when the call manager created a VC for a client-registered
     service access point (SAP) to indicate an incoming-call notification on.


### -param NetBufferLists [in]

A linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that the
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
       <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_RECEIVE_FLAGS_RESOURCES

The miniport driver reclaims ownership of the NET_BUFFER_LIST structures and any attached
       NET_BUFFER structures immediately after 
       <b>NdisMCoIndicateReceiveNetBufferLists</b> returns.


## -returns



None




## -remarks



A miniport driver typically calls the 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> function from its 
    <a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a> function.
    When a miniport driver calls 
    <b>NdisMCoIndicateReceiveNetBufferLists</b>, it specifies a list of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures at the 
    <i>NetBufferLists</i> parameter. NDIS then passes the NET_BUFFER_LIST structures to bound protocol drivers.

Miniport drivers must set the 
    <b>SourceHandle</b> member of each NET_BUFFER_LIST structure to the same value as the 
    <i>NdisVcHandle</i> parameter so that NDIS can return the NET_BUFFER_LIST structures to the correct
    miniport driver.

If a miniport driver calls 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> and clears the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>CoReceiveFlags</i> parameter, NDIS returns the NET_BUFFER_LIST structures that 
    <i>NetBufferLists</i> specifies to the miniport driver's 
    <a href="https://msdn.microsoft.com/0f33ae87-164e-40dc-a915-28211a0d74b7">
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
    <a href="https://msdn.microsoft.com/0f33ae87-164e-40dc-a915-28211a0d74b7">
    MiniportReturnNetBufferLists</a> function.

If a miniport driver sets the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>CoReceiveFlags</i> parameter, the protocol drivers must copy the network data and release the
    NET_BUFFER_LIST structures to the miniport driver. You should design your miniport drivers with enough
    preallocated NET_BUFFER_LIST structures to avoid unnecessary copying.

The caller of 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> must properly initialize the NET_BUFFER_LIST structures, the
    attached 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures, and any attached memory
    descriptor lists (MDLs).




## -see-also




<a href="https://msdn.microsoft.com/99eaba29-ce17-4e79-878e-5fdf7411e56c">MiniportCoCreateVc</a>



<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/0f33ae87-164e-40dc-a915-28211a0d74b7">
   MiniportReturnNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
 

 

