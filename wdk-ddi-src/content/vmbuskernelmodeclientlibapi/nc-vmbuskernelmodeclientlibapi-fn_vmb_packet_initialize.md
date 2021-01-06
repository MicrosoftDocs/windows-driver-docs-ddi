---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_INITIALIZE
title: FN_VMB_PACKET_INITIALIZE (vmbuskernelmodeclientlibapi.h)
description: The VmbPacketInitialize function initializes a buffer to contain a VMBus packet.
tech.root: netvista
ms.date: 05/22/2018
keywords: ["FN_VMB_PACKET_INITIALIZE callback function"]
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - FN_VMB_PACKET_INITIALIZE
 - vmbuskernelmodeclientlibapi/FN_VMB_PACKET_INITIALIZE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_PACKET_INITIALIZE
---

# FN_VMB_PACKET_INITIALIZE callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketInitialize</b> function initializes a buffer to contain a VMBus packet.

## -parameters

### -param Channel

A handle for a channel.

### -param VmbPacket

The buffer to use to store the VMBus packet.

### -param ByteCount

The size of <i>Buffer</i>, in bytes.

## -returns

<b>VmbPacketInitialize</b> returns the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
 The function finished successfully.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
The value of  <i>ByteCount</i> is not valid. It needs to be greater than the maximum packet size plus the size of a void pointer. 

</td>
</tr>
</table>

## -prototype

```cpp
//Declaration

FN_VMB_PACKET_INITIALIZE FnVmbPacketInitialize; 

// Definition

NTSTATUS FnVmbPacketInitialize 
(
	VMBCHANNEL Channel
	VMBPACKET VmbPacket
	UINT32 ByteCount
)
{...}

```

## -remarks

The size of the buffer must be at
least the size calculated by using the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsizeofpacket">VmbChannelSizeofPacket</a> function.  

<b>VmbPacketInitialize</b> is  an alternative
to the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketallocate">VmbPacketAllocate</a> function. Use the current function if the caller supplies the
memory for the packet object. 

The packet's initial completion routine is invalid and must be set before
sending the packet.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsizeofpacket">VmbChannelSizeofPacket</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketallocate">VmbPacketAllocate</a>
