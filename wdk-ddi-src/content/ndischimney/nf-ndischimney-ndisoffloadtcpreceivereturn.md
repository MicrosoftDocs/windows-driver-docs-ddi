---
UID: NF:ndischimney.NdisOffloadTcpReceiveReturn
title: NdisOffloadTcpReceiveReturn function
author: windows-driver-content
description: A protocol driver or intermediate driver calls the NdisOffloadTcpReceiveReturn function to return ownership of NET_BUFFER_LIST and associated structures to an underlying offload target.
old-location: netvista\ndisoffloadtcpreceivereturn.htm
old-project: netvista
ms.assetid: 39f541be-c514-4cd4-bf7d-03b7a318b663
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisOffloadTcpReceiveReturn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisOffloadTcpReceiveReturn
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: 
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisOffloadTcpReceiveReturn function



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or intermediate driver calls the 
  <b>NdisOffloadTcpReceiveReturn</b> function to return ownership of NET_BUFFER_LIST and associated structures
  to an underlying offload target.



## -syntax

````
VOID NdisOffloadTcpReceiveReturn(
  _In_ NDIS_HANDLE      NdisBindingHandle,
  _In_ PNET_BUFFER_LIST NetBufferList
);
````


## -parameters

### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.


### -param NetBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     The linked list can contain NET_BUFFER_LIST structures from one or more calls to the 
     <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">
     NdisTcpOffloadReceiveHandler</a> function.


## -returns
The 
     <b>NdisOffloadTcpReceiveReturn</b> function always returns NDIS_STATUS_SUCCESS. The receive return
     operation is always completed synchronously.


## -remarks
In response to a call to its 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_return_handler.md">
    MiniportTcpOffloadReceiveReturn</a> function, an intermediate driver calls the 
    <b>NdisOffloadTcpReceiveReturn</b> function to propagate the receive return operation to the underlying
    intermediate driver or offload target. For more information, see 
    <a href="https://msdn.microsoft.com/009159ad-81c0-4555-8e6b-a4fec2c7f1d5">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcpReceiveReturn</b> function, the intermediate driver passes the following:

An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadReceiveReturn</i> function.


## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_return_handler.md">
   MiniportTcpOffloadReceiveReturn</a>
</dt>
<dt>
<a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">NdisTcpOffloadReceiveHandler</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOffloadTcpReceiveReturn function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

