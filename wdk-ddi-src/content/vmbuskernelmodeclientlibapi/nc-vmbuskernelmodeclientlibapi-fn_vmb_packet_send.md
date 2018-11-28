---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_SEND
title: FN_VMB_PACKET_SEND
author: windows-driver-content
description: The VmbPacketSend function sends the data in a packet buffer or external data Memory Descriptor List (MDL). The function associates that data with the VMBus packet object, which represents the packet throughout the lifetime of the transaction.
tech.root: netvista
ms.assetid: e701d946-e2cb-4fc4-b098-0cc6f3734305
ms.date: 05/22/2018
ms.topic: callback
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	vmbuskernelmodeclientlibapi.h
api_name: 
-	FN_VMB_PACKET_SEND
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_PACKET_SEND callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSend</b> function  sends the data in a packet buffer or external data Memory Descriptor List (MDL). The function associates that data with the VMBus packet object, which represents the packet
throughout the lifetime of the transaction.

## -prototype

```cpp
//Declaration

FN_VMB_PACKET_SEND FnVmbPacketSend; 

// Definition

NTSTATUS FnVmbPacketSend 
(
	__drv_aliasesMem VMBPACKET PacketObject
	PVOID Buffer
	UINT32 BufferLength
	PMDL ExternalDataMdl
	UINT32 Flags
)
{...}

```

## -parameters

### -param PacketObject

A handle to the VMBus packet object.

### -param Buffer

A buffer that contains the command packet that is sent
through the VMBus ring buffer.

### -param BufferLength

The length, in bytes, of the buffer in the <i>Buffer</i> parameter.

### -param ExternalDataMdl

An MDL that describes a data buffer associated with the packet.

### -param Flags

Flags. The following are pertinent flags:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION"></a><a id="vmbus_channel_format_flag_wait_for_completion"></a><dl>
<dt><b>VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION</b></dt>
</dl>
</td>
<td width="60%">
This packet cannot be considered complete and its resources cannot be released until a
completion packet comes back from the opposite endpoint.

</td>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_FORMAT_FLAG_PAGED_BUFFER"></a><a id="vmbus_channel_format_flag_paged_buffer"></a><dl>
<dt><b>VMBUS_CHANNEL_FORMAT_FLAG_PAGED_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The inline buffer is
paged and must be treated accordingly, which means it must be copied before entering DPC level.
Probing user-mode buffers or handling access violations is the
responsibility of the caller.

</td>
</tr>
</table>

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

For information on other ways to send packets, see the <a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>, <a href="https://msdn.microsoft.com/312DED8E-570E-4DEC-B084-36894970F49F">VmbChannelSendSynchronousRequest</a>, and <a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a> functions.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://msdn.microsoft.com/312DED8E-570E-4DEC-B084-36894970F49F">VmbChannelSendSynchronousRequest</a>



<a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>



<a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a>
