---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP
title: FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP
author: windows-driver-content
description: The VmbClientChannelInitSetTargetPnp function sets a client channel's target by interface type and instance IDs.
ms.assetid: 0c201a5e-9e06-4cab-a062-b6c9aab7ec40
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
-	FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP
product: Windows
targetos: Windows
---

# FN_VMB_CLIENT_CHANNEL_INIT_SET_TARGET_PNP callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbClientChannelInitSetTargetPnp</b> function sets a client channel's target by interface type and instance IDs. If this
function is called, Kernel Mode Client Library (KMCL) uses PnP to find the VMBus Physical Device Object (PDO) that corresponds to the
provided interface. 

## -prototype

```
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
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. 
>
> To access the KMCL interface, allocate a **KMCL_CLIENT_INTERFACE_V1** structure to receive the interface, then call either [**WdfFdoQueryForInterface**](../wdffdo/nf-wdffdo-wdffdoqueryforinterface.md) or [**WdfIoTargetQueryForInterface**](../wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface.md) with these parameters:
> 
> - *InterfaceType* parameter: **KMCL_CLIENT_INTERFACE_TYPE**
> - *Size* parameter: `sizeof(KMCL_CLIENT_INTERFACE_V1)`
> - *Version* parameter: **KMCL_CLIENT_INTERFACE_VERSION_LATEST** 
>
> If the interface query function succeeds, the **KMCL_CLIENT_INTERFACE_V1** structure contains function pointers for the VMBus KMCL functions that you can use to call them.
>
> For more information about driver-defined interfaces, see [Using Driver-Defined Interfaces](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces).

## -see-also