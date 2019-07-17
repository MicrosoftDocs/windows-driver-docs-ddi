---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_ALLOCATE
title: FN_VMB_CHANNEL_ALLOCATE (vmbuskernelmodeclientlibapi.h)
description:  The VmbChannelAllocate function allocates a new VMBus channel that has default parameters and callbacks. 
tech.root: netvista
ms.assetid: b7d23f6f-cc08-4e0b-aca9-9e8234465acb
ms.date: 05/17/2018
ms.topic: callback
f1_keywords:
 - "vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_ALLOCATE"
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- vmbuskernelmodeclientlibapi.h
api_name: 
- FN_VMB_CHANNEL_ALLOCATE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_ALLOCATE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelAllocate</b> function allocates a new VMBus channel that has default parameters and callbacks. 

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_ALLOCATE FnVmbChannelAllocate; 

// Definition

NTSTATUS FnVmbChannelAllocate 
(
	PDEVICE_OBJECT ParentDeviceObject
	BOOLEAN IsServer
	VMBCHANNEL * Channel
)
{...}

```

## -parameters

### -param ParentDeviceObject

A pointer to the parent device.

### -param IsServer

Whether the new channel is a server endpoint.

### -param Channel

A pointer to an allocated channel.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

The
channel may be further initialized using the VMBus channel initialization routines before
it is enabled by using the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelenable">VmbChannelEnable</a> function. The channel must be freed by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelcleanup">VmbChannelCleanup</a> function.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelcleanup">VmbChannelCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelenable">VmbChannelEnable</a>
