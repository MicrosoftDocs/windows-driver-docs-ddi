---
UID: NF:ndischimney.NdisOffloadTcpReceiveReturn
title: NdisOffloadTcpReceiveReturn function (ndischimney.h)
description: A protocol driver or intermediate driver calls the NdisOffloadTcpReceiveReturn function to return ownership of NET_BUFFER_LIST and associated structures to an underlying offload target.
old-location: netvista\ndisoffloadtcpreceivereturn.htm
tech.root: netvista
ms.assetid: 39f541be-c514-4cd4-bf7d-03b7a318b663
ms.date: 05/02/2018
ms.keywords: NdisOffloadTcpReceiveReturn, NdisOffloadTcpReceiveReturn function [Network Drivers Starting with Windows Vista], ndischimney/NdisOffloadTcpReceiveReturn, netvista.ndisoffloadtcpreceivereturn, tcp_chim_ndis_func_2fe6d15f-5e88-4aec-9c5b-281b0e002d8f.xml
ms.topic: function
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Ndis.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisOffloadTcpReceiveReturn
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisOffloadTcpReceiveReturn function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or intermediate driver calls the 
  <b>NdisOffloadTcpReceiveReturn</b> function to return ownership of NET_BUFFER_LIST and associated structures
  to an underlying offload target.


## -parameters




### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     The linked list can contain NET_BUFFER_LIST structures from one or more calls to the 
     <a href="https://msdn.microsoft.com/a45dede9-6559-4207-a49f-d9627054433a">
     NdisTcpOffloadReceiveHandler</a> function.


## -returns



The 
     <b>NdisOffloadTcpReceiveReturn</b> function always returns NDIS_STATUS_SUCCESS. The receive return
     operation is always completed synchronously.




## -remarks



In response to a call to its 
    <a href="https://msdn.microsoft.com/b746f58d-d029-4fcd-a59d-baba037fc38e">
    MiniportTcpOffloadReceiveReturn</a> function, an intermediate driver calls the 
    <b>NdisOffloadTcpReceiveReturn</b> function to propagate the receive return operation to the underlying
    intermediate driver or offload target. For more information, see 
    <a href="https://msdn.microsoft.com/009159ad-81c0-4555-8e6b-a4fec2c7f1d5">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcpReceiveReturn</b> function, the intermediate driver passes the following:

<ul>
<li>
An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

</li>
<li>
The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadReceiveReturn</i> function.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/b746f58d-d029-4fcd-a59d-baba037fc38e">
   MiniportTcpOffloadReceiveReturn</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566705">NDIS_OFFLOAD_HANDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564606">NdisTcpOffloadReceiveHandler</a>
 

 

