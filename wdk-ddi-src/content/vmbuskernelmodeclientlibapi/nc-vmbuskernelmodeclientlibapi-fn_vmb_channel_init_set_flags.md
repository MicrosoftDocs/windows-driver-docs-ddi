---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_INIT_SET_FLAGS
title: FN_VMB_CHANNEL_INIT_SET_FLAGS
author: windows-driver-content
description: The VmbChannelInitSetFlags function sets flags common to server or client channel endpoints.
tech.root: netvista
ms.assetid: 52b07c01-e194-436c-8c93-1d88d9a34499
ms.date: 05/21/2018
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
-	FN_VMB_CHANNEL_INIT_SET_FLAGS
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_INIT_SET_FLAGS callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetFlags</b> function sets flags common to server or client channel endpoints.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_INIT_SET_FLAGS FnVmbChannelInitSetFlags; 

// Definition

NTSTATUS FnVmbChannelInitSetFlags 
(
	VMBCHANNEL Channel
	UINT32 Flags
)
{...}

```

## -parameters

### -param Channel

A handle for the channel.

### -param Flags

A collection of bit flags to set.

## -returns

<b>VmbChannelInitSetFlags</b> can return one of the following status values:

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The value in <i>Flags</i> has invalid bits.

</td>
</tr>
</table>

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
