---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST
title: FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST
author: windows-driver-content
description: The VmbChannelSendSynchronousRequest function sends a packet to the opposite endpoint and waits for a response.
tech.root: netvista
ms.assetid: 353b996b-0678-4ce6-aaeb-3835ae05ee3e
ms.author: windowsdriverdev
ms.date: 05/22/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSendSynchronousRequest</b> function sends a packet to the opposite endpoint and waits for a response.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_SEND_SYNCHRONOUS_REQUEST FnVmbChannelSendSynchronousRequest; 

// Definition

NTSTATUS FnVmbChannelSendSynchronousRequest 
(
	VMBCHANNEL Channel
	PVOID Buffer
	UINT32 BufferSize
	PMDL ExternalDataMdl
	UINT32 Flags
	PVOID CompletionBuffer
	PUINT32 CompletionBufferSize
	PLARGE_INTEGER Timeout
)
{...}

```

## -parameters

### -param Channel

A handle for the channel. 

### -param Buffer

Data to send.

### -param BufferSize

The size, in bytes, of the data to send.

### -param ExternalDataMdl

A Memory Descriptor List (MDL) that describes an additional buffer to send.

### -param Flags

Standard flags.

### -param CompletionBuffer

Buffer in which to store completion packet results.

### -param CompletionBufferSize

The size, in bytes, of the <i>CompletionBuffer</i> value. This value must be rounded up to nearest 8 bytes, or else the function fails. On success,
returns the number of bytes written into <i>CompletionBuffer</i>.

### -param Timeout

A timeout in the style of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a> routing.
After this time elapses, the packet is cancelled. For a timeout of zero (0), if a packet does not fir in the ring buffer, it is not queued.

## -returns

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
The functions finished successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The packet did not fit in the buffer and
was not queued.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The packet was canceled.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The channel is being shut down.

</td>
</tr>
</table>

## -remarks

Clients can run this function with any combination of parameters. 

The root may only call
this if <code>*Timeout == 0</code> and the <b>VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION</b> flag is not set.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
