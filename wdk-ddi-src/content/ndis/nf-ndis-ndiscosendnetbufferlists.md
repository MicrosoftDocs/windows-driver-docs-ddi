---
UID: NF:ndis.NdisCoSendNetBufferLists
title: NdisCoSendNetBufferLists function
description: The NdisCoSendNetBufferLists function sends network data that is contained in a specified list of NET_BUFFER_LIST structures.
old-location: netvista\ndiscosendnetbufferlists.htm
tech.root: netvista
ms.assetid: 8284fdd4-26de-4622-b164-f33aee1d8742
ms.date: 05/02/2018
ms.keywords: NdisCoSendNetBufferLists, NdisCoSendNetBufferLists function [Network Drivers Starting with Windows Vista], condis_sendrcv_ref_6d1dfac7-b538-402c-ae8b-04f74bd188e9.xml, ndis/NdisCoSendNetBufferLists, netvista.ndiscosendnetbufferlists
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 drivers in Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Connection_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisCoSendNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCoSendNetBufferLists function


## -description


The 
  <b>NdisCoSendNetBufferLists</b> function sends network data that is contained in a specified list of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures.


## -parameters




### -param NdisVcHandle [in]

A handle to a virtual connection (VC) that identifies the target of the send request.


### -param NetBufferLists [in]

A pointer to a linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures. Each
     NET_BUFFER_LIST structure describes a list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures.


### -param SendFlags [in]

Flags that define attributes for the send operation. The flags can be combined with a bitwise OR
     operation. To clear all of the flags, set this parameter to zero. 
     <b>NdisCoSendNetBufferLists</b> supports the following flags:
     





#### NDIS_SEND_FLAGS_DISPATCH_LEVEL

The current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK

NDIS should check for loopback. By default, NDIS does not loop back data to the driver that
       submitted the send request. An overlying driver can override this behavior by setting
       NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK. When this flag is set, NDIS identifies all of the NET_BUFFER
       structures that contain data that matches the receive criteria for the binding. NDIS indicates
       NET_BUFFER structures that match the criteria to the overlying driver. This flag does not affect
       checking for loopback, or looping back, on other bindings.


## -returns



None




## -remarks



After a CoNDIS protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, NDIS submits the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that the 
    <i>NetBufferLists</i> parameter specifies to an underlying driver's 
    <a href="https://msdn.microsoft.com/4a717842-6d71-488e-a56a-57c6e6e0c5d7">
    MiniportCoSendNetBufferLists</a> function.

The protocol driver must allocate each NET_BUFFER_LIST structure from a pool by calling one of the
    following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a>


</li>
<li>

<a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
       NdisAllocateNetBufferAndNetBufferList</a>


</li>
<li>

<a href="https://msdn.microsoft.com/357605a1-5c57-44ed-97b3-f466f9a7182c">
       NdisAllocateCloneNetBufferList</a>


</li>
</ul>
The protocol driver can preallocate NET_BUFFER_LIST structures--for example, in its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. Alternatively, the protocol
    driver can allocate the structures immediately prior to calling 
    <b>NdisCoSendNetBufferLists</b> and then can free them when the send operation is complete. When NDIS
    returns a NET_BUFFER_LIST structure to the 
    <a href="https://msdn.microsoft.com/fb4b00c0-0b14-48dd-a6f2-aae659c6bb28">
    ProtocolCoSendNetBufferListsComplete</a> function, the protocol driver can prepare the NET_BUFFER_LIST
    structure and any associated resources for reuse. If you reuse the NET_BUFFER_LIST structures, you can
    get better performance than returning the structures to a pool and then reallocating them for another
    send operation.

A protocol driver must set the 
    <b>SourceHandle</b> member of each 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure to the same value
    that it passes at the 
    <i>NdisVcHandle</i> parameter. The source handle provides the information that NDIS requires to return the
    NET_BUFFER_LIST structure to the protocol driver after the underlying miniport driver calls the 
    <a href="https://msdn.microsoft.com/c4978122-6d13-4e9b-8eb7-d06cd7372268">
    NdisMCoSendNetBufferListsComplete</a> function.

Before a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, the driver can set information that accompanies the send request with
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro. The
    underlying driver can retrieve this information with the NET_BUFFER_LIST_INFO macro.

Before a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b> with a list of NET_BUFFER_LIST structures, the protocol driver must ensure
    that the NET_BUFFER_LIST structures are set up in the order that the network data should be sent.

As soon as a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, it no longer owns the NET_BUFFER_LIST structures and all of the
    associated resources. NDIS calls the 
    <i>ProtocolCoSendNetBufferListsComplete</i> function to return the structures and data to the protocol
    driver. NDIS can collect the structures and data from multiple send requests into a single linked list of
    NET_BUFFER_LIST structures before it passes the list to 
    <i>ProtocolCoSendNetBufferListsComplete</i>.

Until NDIS calls 
    <i>ProtocolCoSendNetBufferListsComplete</i>, the current status of a protocol driver-initiated send is
    not available to the protocol driver. A protocol driver temporarily releases ownership of all of the
    resources that it allocated for a send request when it calls 
    <b>NdisCoSendNetBufferLists</b>. A protocol driver should never attempt to examine the NET_BUFFER_LIST
    structures or any associated data after the driver calls 
    <b>NdisCoSendNetBufferLists</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/4a717842-6d71-488e-a56a-57c6e6e0c5d7">
   MiniportCoSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/357605a1-5c57-44ed-97b3-f466f9a7182c">
   NdisAllocateCloneNetBufferList</a>



<a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a>



<a href="https://msdn.microsoft.com/c4978122-6d13-4e9b-8eb7-d06cd7372268">
   NdisMCoSendNetBufferListsComplete</a>



<a href="https://msdn.microsoft.com/fb4b00c0-0b14-48dd-a6f2-aae659c6bb28">
   ProtocolCoSendNetBufferListsComplete</a>
 

 

