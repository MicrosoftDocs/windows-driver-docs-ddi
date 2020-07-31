---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_INIT_SET_STATE_CHANGE_CALLBACKS
title: FN_VMB_CHANNEL_INIT_SET_STATE_CHANGE_CALLBACKS (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelInitSetStateChangeCallbacks function sets optional callback functions for state changes.
tech.root: netvista
ms.assetid: fb182313-12a8-4886-bc16-9255ac998684
ms.date: 05/21/2018
keywords: ["FN_VMB_CHANNEL_INIT_SET_STATE_CHANGE_CALLBACKS callback function"]
f1_keywords:
 - "vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_INIT_SET_STATE_CHANGE_CALLBACKS"
 - "FN_VMB_CHANNEL_INIT_SET_STATE_CHANGE_CALLBACKS"
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
- FN_VMB_CHANNEL_INIT_SET_STATE_CHANGE_CALLBACKS
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_INIT_SET_STATE_CHANGE_CALLBACKS callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetStateChangeCallbacks</b>  function sets optional callback functions for state changes.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_INIT_SET_STATE_CHANGE_CALLBACKS FnVmbChannelInitSetStateChangeCallbacks; 

// Definition

NTSTATUS FnVmbChannelInitSetStateChangeCallbacks 
(
	VMBCHANNEL Channel
	PVMB_CHANNEL_STATE_CHANGE_CALLBACKS StateChangeCallbacks
)
{...}

```

## -parameters

### -param Channel

A handle for a channel.  

### -param StateChangeCallbacks

A structure of state change callbacks to set.

## -returns

<b>VmbChannelInitSetStateChangeCallbacks</b> returns one of the following status values: 

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
The function finished successfully.

</td>
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
The <i>StateChangeCallbacks</i> value is the wrong version or size. 

</td>
</tr>
</table>

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
