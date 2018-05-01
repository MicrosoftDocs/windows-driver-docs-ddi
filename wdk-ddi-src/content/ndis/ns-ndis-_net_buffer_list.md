---
UID: NS:ndis._NET_BUFFER_LIST
title: "_NET_BUFFER_LIST"
author: windows-driver-content
description: The NET_BUFFER_LIST structure specifies a linked list of NET_BUFFER structures.
old-location: netvista\net_buffer_list.htm
old-project: netvista
ms.assetid: 3b61a424-33f8-4b33-aaef-f68f0026ce27
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNET_BUFFER_LIST, NET_BUFFER_LIST, NET_BUFFER_LIST structure [Network Drivers Starting with Windows Vista], PNET_BUFFER_LIST, PNET_BUFFER_LIST structure pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_LIST, ndis/NET_BUFFER_LIST, ndis/PNET_BUFFER_LIST, ndis_netbuf_structures_ref_7320b98f-6600-44e4-a6e8-a7d7becaaa32.xml, netvista.net_buffer_list"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NET_BUFFER_LIST
product: Windows
targetos: Windows
req.typenames: NET_BUFFER_LIST, *PNET_BUFFER_LIST
---

# _NET_BUFFER_LIST structure


## -description


The NET_BUFFER_LIST structure specifies a linked list of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures.


## -struct-fields




### -field Next

 


### -field FirstNetBuffer

 


### -field Link

 


### -field NetBufferListHeader

A 
     <a href="https://msdn.microsoft.com/49169618-c42d-4bae-b1df-1426059d60d7">
     NET_BUFFER_LIST_HEADER</a> structure.


### -field Context

A pointer to a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568389">NET_BUFFER_LIST_CONTEXT</a> structure.
      Protocol and miniport drivers use this structure to store information about the NET_BUFFER_LIST
      structure. Information stored in the NET_BUFFER_LIST_CONTEXT structure is opaque to NDIS and other
      drivers in the stack.

Use the following functions and macros to access data in the NET_BUFFER_LIST_CONTEXT structure:


<a href="https://msdn.microsoft.com/3bbad723-86bf-4206-9e51-52a66efaec20">
         NdisAllocateNetBufferListContext</a>



<a href="https://msdn.microsoft.com/e5554790-a7a2-4c0d-a6ae-585ea909cd3d">
         NdisFreeNetBufferListContext</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568391">
         NET_BUFFER_LIST_CONTEXT_DATA_START</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568390">
         NET_BUFFER_LIST_CONTEXT_DATA_SIZE</a>



### -field ParentNetBufferList

If this NET_BUFFER_LIST structure is a clone of another NET_BUFFER_LIST structure, this member
     specifies a pointer to the parent NET_BUFFER_LIST structure. Otherwise, this parameter is <b>NULL</b>. A driver
     uses the 
     <a href="https://msdn.microsoft.com/357605a1-5c57-44ed-97b3-f466f9a7182c">
     NdisAllocateCloneNetBufferList</a> function to create a clone.


### -field NdisPoolHandle

A pool handle that identifies the NET_BUFFER_LIST pool from which the NET_BUFFER_LIST structure
     was allocated.


### -field NdisReserved

Reserved for use by NDIS.


### -field ProtocolReserved

Reserved for use by protocol drivers.


### -field MiniportReserved

Reserved for use by miniport drivers.


### -field Scratch

Data that is defined by the current owner of the NET_BUFFER_LIST structure. The current owner,
     either NDIS or an NDIS driver, can use this member for their own purposes. When the NET_BUFFER_LIST
     structure is initially allocated, this member is <b>NULL</b>. After the current owner relinquishes ownership,
     NDIS or another driver can overwrite this member.


### -field SourceHandle

A handle that NDIS provided to the driver in a binding or attaching operation by using one of the
     following driver-supplied routines:
     





#### Miniport Driver


<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>




#### Protocol Driver


<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>




#### Filter Driver


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>


NDIS uses 
     <b>SourceHandle</b> to return the NET_BUFFER_LIST structure to the driver that sent the NET_BUFFER_LIST
     structure.


### -field NblFlags

This member contains flags that can be combined with a bitwise OR operation.
     

Use the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564620">NdisTestNblFlag</a>, 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564626">NdisTestNblFlags</a>, 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564542">NdisSetNblFlag</a>, and 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561630">NdisClearNblFlag</a> macros to access the
     flags.

Intermediate drivers and filter drivers can set the following flags if they do not modify data that
     is associated with a NET_BUFFER_LIST. For example, if the data did not change, NDIS might reuse the
     original information from which the NET_BUFFER_LIST was created.:





#### NDIS_NBL_FLAGS_SEND_READ_ONLY

If set, the NET_BUFFER_LIST structure and its data are read-only for send operations.



#### NDIS_NBL_FLAGS_RECV_READ_ONLY

If set, the NET_BUFFER_LIST structure and its data are read-only for receive operations.

A driver can set the following flags even if it does not split the associated Ethernet frame:





#### NDIS_NBL_FLAGS_IS_IPV4

All of the Ethernet frames in this NET_BUFFER_LIST structure are IPv4 frames. If this flag is
       set, the header-data split provider must not set the NDIS_NBL_FLAGS_IS_IPV6 flag.



#### NDIS_NBL_FLAGS_IS_IPV6

All of the Ethernet frames in this NET_BUFFER_LIST structure are IPv6 frames. If this flag is
       set, the header-data split provider must not set the NDIS_NBL_FLAGS_IS_IPV4 flag.



#### NDIS_NBL_FLAGS_IS_TCP

All of the Ethernet frames in this NET_BUFFER_LIST structure are TCP frames. If this flag is
       set, the header-data split provider must not set the NDIS_NBL_FLAGS_IS_UDP flag, and the provider must
       set the NDIS_NBL_FLAGS_IS_IPV4 flag or the NDIS_NBL_FLAGS_IS_IPV6 flag.



#### NDIS_NBL_FLAGS_IS_UDP

All of the Ethernet frames in this NET_BUFFER_LIST structure are UDP frames. If this flag is
       set, the header-data split provider must not set the NDIS_NBL_FLAGS_IS_TCP flag, and the provider must
       set the NDIS_NBL_FLAGS_IS_IPV4 flag or the NDIS_NBL_FLAGS_IS_IPV6 flag.



#### NDIS_NBL_FLAGS_IS_LOOPBACK_PACKET

All of the packets that are associated with this NET_BUFFER_LIST structure are loopback
       packets.

If the header-data split provider does not split the associated Ethernet frame, the miniport driver
     must indicate the NET_BUFFER_LIST structure with the following flags cleared:





#### NDIS_NBL_FLAGS_HD_SPLIT

The header and data are split in all of the Ethernet frames that are associated with this
       NET_BUFFER_LIST structure.



#### NDIS_NBL_FLAGS_SPLIT_AT_UPPER_LAYER_PROTOCOL_HEADER

All of the Ethernet frames in this NET_BUFFER_LIST are split at the beginning of the upper layer
       protocol header. If this flag is set, the header-data split provider must set the
       NDIS_NBL_FLAGS_IS_IPV4 flag or the NDIS_NBL_FLAGS_IS_IPV6 flag. Also, the provider can set the
       NDIS_NBL_FLAGS_IS_TCP flag or the NDIS_NBL_FLAGS_IS_UDP flag, but the provider must not set the
       NDIS_NBL_FLAGS_SPLIT_AT_UPPER_LAYER_PROTOCOL_PAYLOAD flag.



#### NDIS_NBL_FLAGS_SPLIT_AT_UPPER_LAYER_PROTOCOL_PAYLOAD

All of the Ethernet frames in this NET_BUFFER_LIST structure are split at the beginning of the
       TCP or UDP payload. If this flag is set, the header-data split provider must set the
       NDIS_NBL_FLAGS_IS_IPV4 flag or the NDIS_NBL_FLAGS_IS_IPV6 flag. Also, the provider must set the
       NDIS_NBL_FLAGS_IS_TCP flag or the NDIS_NBL_FLAGS_IS_UDP flag, but the provider must not set the
       NDIS_NBL_FLAGS_SPLIT_AT_UPPER_LAYER_PROTOCOL_HEADER flag.


### -field ChildRefCount

If this NET_BUFFER_LIST structure has clones (is a parent), this member specifies the number of
     outstanding clones. Otherwise, this member is zero.


### -field Flags

Attributes of the NET_BUFFER_LIST structure. The following definitions specify a bit mask for a set
      of flags:





#### NBL_FLAGS_PROTOCOL_RESERVED

This set is reserved for protocol drivers.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, two additional bits are available for protocol use: 0x00000003.  A NDIS 6.30 protocol may use these bits if and only if <a href="https://msdn.microsoft.com/library/windows/hardware/ff562680">NdisGetVersion</a> returns a value greater than or equal to <b>NDIS_RUNTIME_VERSION_630</b>.  Protocols must not use these bits on earlier versions of NDIS, because prior to 6.30, NDIS uses them internally.</div>
<div> </div>


#### NBL_FLAGS_MINIPORT_RESERVED

This set is reserved for miniport drivers.



#### NBL_FLAGS_SCRATCH

The current owner of the NET_BUFFER_LIST structure, either NDIS or an NDIS driver, can use this
        set. When the current owner relinquishes ownership, NDIS or another driver can overwrite these
        flags.



#### NBL_FLAGS_NDIS_RESERVED

This set is reserved for NDIS.


### -field Status

The final completion status of a network data operation on this NET_BUFFER_LIST structure.
     Miniport drivers write this value before calling the 
     <a href="https://msdn.microsoft.com/33890582-5eba-4cc1-a0d9-ec07f18da453">
     NdisMSendNetBufferListsComplete</a> function. Miniport drivers specify one of the following values:
     





#### NDIS_STATUS_SUCCESS

All the network data described by NET_BUFFER structures associated with this NET_BUFFER_LIST
       structure was successfully transmitted over the network.



#### NDIS_STATUS_INVALID_LENGTH

The size of the data in some NET_BUFFER structures associated with this NET_BUFFER_LIST
       structure was too large for the underlying NIC.



#### NDIS_STATUS_RESOURCES

The send request for this NET_BUFFER_LIST structure failed due to insufficient resources.



#### NDIS_STATUS_FAILURE

This send request for this NET_BUFFER_LIST structure failed due to some reason other than those
       stated in the previous three values.



#### NDIS_STATUS_SEND_ABORTED

NDIS called the 
       <a href="https://msdn.microsoft.com/17111aa3-c02f-494a-af97-5ab34c152451">MiniportCancelSend</a> function to
       cancel the send operation for this NET_BUFFER_LIST structure.



#### NDIS_STATUS_RESET_IN_PROGRESS

The miniport driver aborted the send request due to a reset.



#### NDIS_STATUS_PAUSED

If a driver must reject send requests because it is paused, it sets the complete status in each
       affected NET_BUFFER_LIST to NDIS_STATUS_PAUSED.


### -field NdisReserved2

 


### -field NetBufferListInfo

An array of values containing information that is common to all NET_BUFFER structures in the list.
     This information is often referred to as "out-of-band (OOB) data."

Use the 
     <a href="https://msdn.microsoft.com/79327b2b-e97b-42dc-8d15-9d774c424cae">
     NDIS_NET_BUFFER_LIST_INFO</a> enumeration values with the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro to set and
     get values in the 
     <b>NetBufferListInfo</b> array.


## -remarks



NDIS drivers can call any of the following functions to allocate and initialize a NET_BUFFER_LIST
    structure:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a>



<a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
       NdisAllocateNetBufferAndNetBufferList</a>



<a href="https://msdn.microsoft.com/357605a1-5c57-44ed-97b3-f466f9a7182c">
       NdisAllocateCloneNetBufferList</a>



<a href="https://msdn.microsoft.com/40b6596b-7ab8-4336-8c38-21b9f32d8558">
       NdisAllocateFragmentNetBufferList</a>



<a href="https://msdn.microsoft.com/6a7fcb43-93bf-4351-8198-1d788b1bcc8c">
       NdisAllocateReassembledNetBufferList</a>


All NET_BUFFER structures associated with a NET_BUFFER_LIST structure have the attributes that are
    specified by the 
    <b>NetBufferListInfo</b> and 
    <b>Context</b> members.

When a driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564535">NdisSendNetBufferLists</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562616">NdisFSendNetBufferLists</a> function,
    it loses ownership of:

<ul>
<li>
The specified NET_BUFFER_LIST structure.

</li>
<li>
The attached 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures and MDLs.

</li>
<li>
Any attached NDIS_REQUEST_CONTROLs.

</li>
<li>
All 
      <b>NetBufferListInfo</b> data that is associated with the NET_BUFFER_LIST structure.

</li>
</ul>
The current owner of a list of NET_BUFFER_LIST structures can move a NET_BUFFER_LIST structure to
    another list. However, all NET_BUFFER structures associated with a NET_BUFFER_LIST structure should stay
    with the same NET_BUFFER_LIST structure. Only the driver that created the NET_BUFFER structures can move
    them to a different NET_BUFFER_LIST structure. The current owner cannot modify a NET_BUFFER structure's 
    <b>Next</b> member.

A list of NET_BUFFER_LIST structures is a simple singly linked and NULL-terminated list. To move a
    NET_BUFFER_LIST structure to a different list, make appropriate updates to the 
    <b>Next</b> members in both the source and destination lists.

To access members of the NET_BUFFER_LIST structure, use the following macros and functions:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff568404">NET_BUFFER_LIST_NEXT_NBL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568394">NET_BUFFER_LIST_FIRST_NB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568395">NET_BUFFER_LIST_FLAGS</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568388">
       NET_BUFFER_LIST_MINIPORT_RESERVED</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568391">
       NET_BUFFER_LIST_CONTEXT_DATA_START</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568390">
       NET_BUFFER_LIST_CONTEXT_DATA_SIZE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568411">NET_BUFFER_LIST_STATUS</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568388">
       NET_BUFFER_LIST_PROTOCOL_RESERVED</a>



<a href="https://msdn.microsoft.com/645fd5f6-32b5-4ef6-9583-1418291d55d3">
       NdisGetPoolFromNetBufferList</a>


For more information on how to use net buffers, see 
    <a href="https://msdn.microsoft.com/97cddcd1-7242-4cc5-9af9-fe82a2ef995f">NET_BUFFER Architecture</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566569">NDIS_NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568389">NET_BUFFER_LIST_CONTEXT</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568390">
   NET_BUFFER_LIST_CONTEXT_DATA_SIZE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568391">
   NET_BUFFER_LIST_CONTEXT_DATA_START</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568394">NET_BUFFER_LIST_FIRST_NB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568395">NET_BUFFER_LIST_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568400">NET_BUFFER_LIST_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568388">
   NET_BUFFER_LIST_MINIPORT_RESERVED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568404">NET_BUFFER_LIST_NEXT_NBL</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568388">
   NET_BUFFER_LIST_PROTOCOL_RESERVED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568411">NET_BUFFER_LIST_STATUS</a>



<a href="https://msdn.microsoft.com/357605a1-5c57-44ed-97b3-f466f9a7182c">
   NdisAllocateCloneNetBufferList</a>



<a href="https://msdn.microsoft.com/40b6596b-7ab8-4336-8c38-21b9f32d8558">
   NdisAllocateFragmentNetBufferList</a>



<a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a>



<a href="https://msdn.microsoft.com/3bbad723-86bf-4206-9e51-52a66efaec20">
   NdisAllocateNetBufferListContext</a>



<a href="https://msdn.microsoft.com/6a7fcb43-93bf-4351-8198-1d788b1bcc8c">
   NdisAllocateReassembledNetBufferList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561623">NdisCancelSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561630">NdisClearNblFlag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562587">NdisFreeNetBufferListContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562623">NdisGeneratePartialCancelId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562659">NdisGetPoolFromNetBufferList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564535">NdisSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564542">NdisSetNblFlag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564620">NdisTestNblFlag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564626">NdisTestNblFlags</a>
 

 

