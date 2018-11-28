---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_SERVER_CHANNEL_INIT_SET_VMBUS_HANDLE
title: FN_VMB_SERVER_CHANNEL_INIT_SET_VMBUS_HANDLE
author: windows-driver-content
description: The VmbServerChannelInitSetVmbusHandle function associates an instance of VMBus with this channel.  
ms.assetid: 9f0c59b3-8b3d-4122-97c5-689c4ccb19b2
ms.date: 09/13/2018
ms.topic: callback
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
-	FN_VMB_SERVER_CHANNEL_INIT_SET_VMBUS_HANDLE
product: 
- Windows
targetos: Windows
tech.root: netvista
ms.custom: RS5
---

# FN_VMB_SERVER_CHANNEL_INIT_SET_VMBUS_HANDLE callback function

## -description

The <b>VmbServerChannelInitSetVmbusHandle</b> function associates an instance of VMBus with this channel.  

## -prototype

```cpp
//Declaration

FN_VMB_SERVER_CHANNEL_INIT_SET_VMBUS_HANDLE FnVmbServerChannelInitSetVmbusHandle; 

// Definition

NTSTATUS FnVmbServerChannelInitSetVmbusHandle 
(
	VMBCHANNEL Channel
	HANDLE VmbusHandle
)
{...}

```

## -parameters

### -param Channel

A handle for a channel.

### -param VmbusHandle

A kernel mode handle to the VMBus vdev of the partition.

## -returns

Returns STATUS_SUCCESS if the operation is successful. Otherwise, returns an approprite NTSTATUS error code.

## -remarks

The VMBus instance was previously initialized for the specific guest virtual machine. Therefore, invoking this function identifies the child virtual machine to which this channel is offered.

Obtain a value for the <i>VmbusHandle</i> parameter by using the <a href="https://msdn.microsoft.com/C549B9C7-221D-4DD8-9D8D-24BC729099C7">VmbConvertVmbusHandleToKernelHandle</a> function.

This function can be called while running in any thread context.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

<a href="https://msdn.microsoft.com/C549B9C7-221D-4DD8-9D8D-24BC729099C7">VmbConvertVmbusHandleToKernelHandle</a>
