---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP
title: FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP (vmbuskernelmodeclientlibapi.h)
description: The VmbClientChannelInitSetTargetPnp function sets a client channel's target by interface type and instance IDs.
tech.root: netvista
ms.assetid: 0c201a5e-9e06-4cab-a062-b6c9aab7ec40
ms.date: 05/22/2018
keywords: ["FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP callback function"]
f1_keywords:
 - "vmbuskernelmodeclientlibapi/FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP"
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
- apiref
api_type: 
- UserDefined
api_location: 
- vmbuskernelmodeclientlibapi.h
api_name: 
- FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbClientChannelInitSetTargetPnp</b> function sets a client channel's target by interface type and instance IDs. If this
function is called, Kernel Mode Client Library (KMCL) uses PnP to find the VMBus Physical Device Object (PDO) that corresponds to the
provided interface. 

## -prototype

```cpp
//Declaration

FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP FnVmbClientChannelInitSetTargetPnp; 

// Definition

NTSTATUS FnVmbClientChannelInitSetTargetPnp 
(
	VMBCHANNEL Channel
	LPCGUID InterfaceType
	LPCGUID InterfaceInstance
	PFN_VMB_CHANNEL_PNP_FAILURE PnpFailureCallback
)
{...}

```

## -parameters

### -param Channel

A pointer to a channel.

### -param InterfaceType

A pointer to the interface type GUID.
This GUID identifies the 
type of channel and the protocol that is used with the channel.

### -param InterfaceInstance

A pointer to the instance type GUID. This is a 
specific instance of the service. If not
provided, any instance with the provided type is accepted.

### -param PnpFailureCallback

A pointer to an event callback to call if the
device asynchronously fails to connect even though the PnP device was
located.

## -returns

<b>VmbClientChannelInitSetTargetPnp</b> returns the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

</td>
</tr>
</table>

## -remarks

If you 
have two paravirtual network interfaces, they will have the 
same <i>InterfaceType</i> but different <i>InterfaceInstance</i> values. 

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
