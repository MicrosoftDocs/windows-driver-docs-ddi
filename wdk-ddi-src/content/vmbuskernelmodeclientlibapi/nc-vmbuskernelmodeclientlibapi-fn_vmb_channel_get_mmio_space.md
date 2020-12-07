---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_GET_MMIO_SPACE
title: FN_VMB_CHANNEL_GET_MMIO_SPACE (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelGetMmioSpace function retrieves the kernel virtual address of the MMIO space allocated to a channel.
tech.root: netvista
ms.date: 05/21/2018
keywords: ["FN_VMB_CHANNEL_GET_MMIO_SPACE callback function"]
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
 - FN_VMB_CHANNEL_GET_MMIO_SPACE
 - vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_GET_MMIO_SPACE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_CHANNEL_GET_MMIO_SPACE
---

# FN_VMB_CHANNEL_GET_MMIO_SPACE callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The **VmbChannelGetMmioSpace** function retrieves the kernel virtual address of the MMIO space allocated to a channel. This MMIO space is reserved via [**VmbServerChannelInitSetMmioMegabytes**](nc-vmbuskernelmodeclientlibapi-fn_vmb_server_channel_init_set_mmio_megabytes.md). This function is only valid after the open channel callback has been received.

## -parameters

### -param Channel

A handle for the channel. Allocated by [**VmbChannelAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_allocate.md).

### -param MmioAddress

A pointer to a **PVOID** to fill with the MMIO physical address.

### -param MmioSize

A pointer to the returned size of the MMIO space.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_GET_MMIO_SPACE FnVmbChannelGetMmioSpace; 

// Definition

VOID FnVmbChannelGetMmioSpace 
(
	VMBCHANNEL Channel
	UINT64 *MmioAddress
	UINT64 *MmioSize
)
{...}

```

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

[**VmbServerChannelInitSetMmioMegabytes**](nc-vmbuskernelmodeclientlibapi-fn_vmb_server_channel_init_set_mmio_megabytes.md)

[**VmbChannelAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_allocate.md)

