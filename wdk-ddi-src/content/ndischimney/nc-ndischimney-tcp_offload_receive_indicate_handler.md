---
UID: NC:ndischimney.TCP_OFFLOAD_RECEIVE_INDICATE_HANDLER
title: TCP_OFFLOAD_RECEIVE_INDICATE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol driver's or intermediate driver's ProtocolTcpOffloadReceiveIndicate function to deliver received data that is being indicated by an underlying driver or offload target.
old-location: netvista\protocoltcpoffloadreceiveindicate.htm
old-project: netvista
ms.assetid: 8a400515-3619-4fe9-8e08-638859442ea3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ProtocolTcpOffloadReceiveIndicate, ProtocolTcpOffloadReceiveIndicate callback function [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_RECEIVE_INDICATE_HANDLER, ndischimney/ProtocolTcpOffloadReceiveIndicate, netvista.protocoltcpoffloadreceiveindicate, tcp_chim_protocol_func_c65e1895-a874-4c93-b25f-f2951a0a19db.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndischimney.h
api_name:
-	ProtocolTcpOffloadReceiveIndicate
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# TCP_OFFLOAD_RECEIVE_INDICATE_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>
  ProtocolTcpOffloadReceiveIndicate</i> function to deliver received data that is being indicated by an
  underlying driver or offload target.


## -parameters




### -param OffloadContext [in]

A pointer to the protocol or intermediate driver's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566705">NDIS_OFFLOAD_HANDLE</a> structure for the
     TCP connection on which the indication is being made. The protocol or intermediate driver supplied this
     pointer as an input parameter to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562743">NdisInitiateOffload</a> function when
     offloading the connection.


### -param NetBufferList [in]

A pointer to a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. Each 
      <b>NET_BUFFER_LIST</b> structure
      describes a list of 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures. Each 
      <b>NET_BUFFER</b> structure in the list maps to a
      chain of 
      <a href="https://msdn.microsoft.com/71524333-dd5d-4f0b-8dd3-034ea926bc93">memory descriptor lists (MDLs)</a>. The MDLs contain the
      received data. The MDLs are locked so that they remain resident, but they are not mapped into system
      memory.

The 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure
      specified by 
      <i>NetBufferList</i> must be a stand-alone structure and cannot be the first
      structure in a linked list of 
      <b>NET_BUFFER_LIST</b> structures.
      Offload targets can work around this limitation by chaining as many MDLs as necessary to the same 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> in an offload receive
      indication.


### -param Status [in]

An intermediate driver should propagate this status when calling 
     <a href="https://msdn.microsoft.com/a45dede9-6559-4207-a49f-d9627054433a">
     NdisTcpOffloadReceiveHandler</a>.


### -param BytesConsumed [out]

A pointer to a ULONG-typed variable that receives the number of bytes that were consumed by the
     client application.


## -returns



The 
     <i>
     ProtocolTcpOffloadReceiveIndicate</i> function can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The client application consumed all the indicated receive data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_OFFLOAD_DATA_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The client application rejected all the indicated receive data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_OFFLOAD_DATA_PARTIALLY_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The client application consumed a subset of the indicated receive data. The amount of data, in
       bytes, that was consumed by the client application is returned in the variable specified by the 
       <i>BytesConsumed</i> parameter.

</td>
</tr>
</table>
 




## -remarks



To propagate the indication to the overlying driver or host stack, the intermediate driver calls the 
    <a href="https://msdn.microsoft.com/a45dede9-6559-4207-a49f-d9627054433a">
    NdisTcpOffloadReceiveHandler</a> function. The intermediate driver passes the following parameters to
    the 
    <b>NdisTcpOffloadReceiveHandler</b> function:

<ul>
<li>
The 
      <b>NdisOffloadHandle</b> that the offload target stored in its context for the offloaded TCP connection.
      For more information, see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

</li>
<li>
The 
      <i>NetBufferList</i> pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadReceiveIndicate</i> function.

</li>
<li>
The 
      <i>Status</i> that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadReceiveIndicate</i> function.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566705">NDIS_OFFLOAD_HANDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562743">NdisInitiateOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563706">NdisOffloadTcpReceiveReturn</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564606">NdisTcpOffloadReceiveHandler</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_RECEIVE_INDICATE_HANDLER callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
