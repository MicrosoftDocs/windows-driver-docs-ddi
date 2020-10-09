---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CLIENT_CHANNEL_INIT_SET_RING_BUFFER_PAGE_COUNT
title: FN_VMB_CLIENT_CHANNEL_INIT_SET_RING_BUFFER_PAGE_COUNT (vmbuskernelmodeclientlibapi.h)
description: The VmbClientChannelInitSetRingBufferPageCount function sets the number of pages of memory the client allocates for incoming and outgoing ring buffers.
tech.root: netvista
ms.assetid: 895902d8-e337-4e24-aac1-621c578fc259
ms.date: 05/22/2018
keywords: ["FN_VMB_CLIENT_CHANNEL_INIT_SET_RING_BUFFER_PAGE_COUNT callback function"]
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
 - FN_VMB_CLIENT_CHANNEL_INIT_SET_RING_BUFFER_PAGE_COUNT
 - vmbuskernelmodeclientlibapi/FN_VMB_CLIENT_CHANNEL_INIT_SET_RING_BUFFER_PAGE_COUNT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_CLIENT_CHANNEL_INIT_SET_RING_BUFFER_PAGE_COUNT
---

# FN_VMB_CLIENT_CHANNEL_INIT_SET_RING_BUFFER_PAGE_COUNT callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbClientChannelInitSetRingBufferPageCount</b> function sets the number of pages of memory the client allocates for incoming and outgoing ring
buffers.

## -parameters

### -param Channel

A handle for a channel.

### -param IncomingPageCount

Number of pages to allocate for the incoming ring buffer.

### -param OutgoingPageCount

Number of pages to allocate for the outgoing ring buffer.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -prototype

```cpp
//Declaration

FN_VMB_CLIENT_CHANNEL_INIT_SET_RING_BUFFER_PAGE_COUNT FnVmbClientChannelInitSetRingBufferPageCount; 

// Definition

NTSTATUS FnVmbClientChannelInitSetRingBufferPageCount 
(
	VMBCHANNEL Channel
	UINT32 IncomingPageCount
	UINT32 OutgoingPageCount
)
{...}

```

## -remarks

Because the client virtual machine donates the pages for both the incoming and the outgoing ring
buffers, this function can only be invoked on the client endpoint.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

