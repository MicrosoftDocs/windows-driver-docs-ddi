---
UID: NF:ndis.NdisFSendNetBufferLists
title: NdisFSendNetBufferLists function
description: Filter drivers call the NdisFSendNetBufferLists function to send a list of network data buffers.
old-location: netvista\ndisfsendnetbufferlists.htm
tech.root: netvista
ms.assetid: fe0896ab-2d20-465f-a8bc-bfc0033701d6
ms.date: 05/02/2018
ms.keywords: NdisFSendNetBufferLists, NdisFSendNetBufferLists function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_333e9ef3-6858-4b5b-bca1-4f06da775906.xml, ndis/NdisFSendNetBufferLists, netvista.ndisfsendnetbufferlists
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
-	NdisFSendNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFSendNetBufferLists function


## -description


Filter drivers call the 
  <b>NdisFSendNetBufferLists</b> function to send a list of network data buffers.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param NetBufferList

A pointer to a linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures. Each
     <b>NET_BUFFER_LIST</b> structure describes a list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures.

### -param PortNumber [in]

A port number that identifies a miniport adapter port. Miniport adapter port numbers are assigned
     by calling the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a> function. A zero
     value identifies the default port of a miniport adapter.


### -param SendFlags [in]

Flags that define attributes for the send operation. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     





#### NDIS_SEND_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK

Specifies that NDIS should check for loopback. By default, NDIS does not loop back data to the
       driver that submitted the send request. An overlying driver can override this behavior by setting this
       flag. When this flag is set, NDIS identifies all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures that contain data that
       matches the receive criteria for the binding. NDIS indicates NET_BUFFER structures that match the
       criteria to the overlying driver. This flag has no affect on checking for loopback, or looping back,
       on other bindings.



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


## -returns



None




## -remarks



After a filter driver calls the 
    <b>NdisFSendNetBufferLists</b> function, NDIS submits the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures to the underlying
    drivers.

A filter driver can originate send requests or it can filter the requests that it receives from
    overlying drivers. If the filter driver originates send requests, the driver must allocate buffers pools.
    The filter driver allocates each <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure from a pool.

The filter driver can preallocate <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures or it can allocate the structures just
    before calling 
    <b>NdisFSendNetBufferLists</b> and then free them when the send operation is complete.

A filter driver must set the 
    <b>SourceHandle</b> member of each <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that it originates to the same value that it
    passes to the 
    <i>NdisFilterHandle</i> parameter. The filter handle provides the information that NDIS requires to return
    the <b>NET_BUFFER_LIST</b> structure to the filter driver. The filter driver must not modify the 
    <b>SourceHandle</b> member in any <b>NET_BUFFER_LIST</b> structures that it did not originate.

Before calling 
    <b>NdisFSendNetBufferLists</b>, a filter driver can set information that accompanies the send request
    with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro. The
    underlying drivers can retrieve this information with the <b>NET_BUFFER_LIST_INFO</b> macro.

NDIS calls a filter driver's 
    <a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">
    FilterSendNetBufferLists</a> function to pass on send requests from overlying drivers. A filter driver
    can pass on such requests by passing the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>T structures that it received in 
    <i>FilterSendNetBufferLists</i> to 
    <b>NdisFSendNetBufferLists</b>.

As soon as a filter driver calls the 
    <b>NdisFSendNetBufferLists</b> function, it relinquishes ownership of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures and
    all associated resources. NDIS calls the 
    <a href="https://msdn.microsoft.com/1a3a1e80-29f1-4f19-b3c7-9a8b189f18c4">
    FilterSendNetBufferListsComplete</a> function to return the structures and data to the filter driver.
    NDIS can collect the structures and data from multiple send requests into a single linked list of
    <b>NET_BUFFER_LIST</b> structures before it passes the list to 
    <i>FilterSendNetBufferListsComplete</i>.

Until NDIS calls 
    <a href="https://msdn.microsoft.com/1a3a1e80-29f1-4f19-b3c7-9a8b189f18c4">FilterSendNetBufferListsComplete</a>, the current status of the send request is not available to the
    filter driver. A filter driver temporarily releases ownership of all resources that are associated with a
    send request when it calls 
    <b>NdisFSendNetBufferLists</b>. A filter driver should never try to examine the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
    structures or any associated data after calling 
    <b>NdisFSendNetBufferLists</b>.

<div class="alert"><b>Note</b>  A filter driver should keep track of send requests that it originates and make
      sure that it does not call the 
      <a href="https://msdn.microsoft.com/5a9008eb-86ad-4e3c-85a2-c8fd1b8fb4cb">
      NdisFSendNetBufferListsComplete</a> function when such requests are complete.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">FilterSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/1a3a1e80-29f1-4f19-b3c7-9a8b189f18c4">
   FilterSendNetBufferListsComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a>
 

 

