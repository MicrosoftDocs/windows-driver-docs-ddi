---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_INTERFACE_ID
title: FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_INTERFACE_ID (vmbuskernelmodeclientlibapi.h)
description: The VmbServerChannelInitSetTargetInterfaceId function sets the target interface type GUID and instance GUID of the channel offer.
ms.assetid: 895117ce-880e-4f45-95bc-a283087490d1
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
- apiref
api_type: 
- UserDefined
api_location: 
- vmbuskernelmodeclientlibapi.h
api_name: 
- FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_INTERFACE_ID
product: 
- Windows
targetos: Windows
tech.root: netvista
ms.custom: RS5
---

# FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_INTERFACE_ID callback function

## -description

The <b>VmbServerChannelInitSetTargetInterfaceId</b> function sets the target interface type GUID and instance GUID of the channel offer.

## -prototype

```cpp
//Declaration

FN_VMB_SERVER_CHANNEL_INIT_SET_TARGET_INTERFACE_ID FnVmbServerChannelInitSetTargetInterfaceId; 

// Definition

NTSTATUS FnVmbServerChannelInitSetTargetInterfaceId 
(
	VMBCHANNEL Channel
	GUID InterfaceType
	GUID InterfaceInstance
)
{...}

```

## -parameters

### -param Channel

A handle for a channel. 

### -param InterfaceType

A pointer to the interface type GUID.

### -param InterfaceInstance

A pointer to the instance type GUID.

## -returns

Returns STATUS_SUCCESS if the operation is successful. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

The <i>InterfaceType</i>
GUID identifies the type of channel and, specifically, the protocol that is used with
the channel.  If the VMBus in the child partition is creating a Physical Device Object
(PDO) that is associated with this channel, this GUID is the basis of the PDO's hardware
ID reported to the PnP Manager.  

The <i>InterfaceInstance</i> GUID identifies a specific instance
of the service.  For instance, If you have two paravirtual network interfaces, they
have the same interface type, but different interface instance values.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also
