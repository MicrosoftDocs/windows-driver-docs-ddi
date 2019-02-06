---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_SERVER_CHANNEL_INIT_SET_FLAGS
title: FN_VMB_SERVER_CHANNEL_INIT_SET_FLAGS (vmbuskernelmodeclientlibapi.h)
description: The VmbServerChannelInitSetFlags function sets flags unique to server channel endpoints.
ms.assetid: 0e4db15f-ec69-4c68-8a7e-da24ec7f5718
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
-	FN_VMB_SERVER_CHANNEL_INIT_SET_FLAGS
product: 
- Windows
targetos: Windows
tech.root: netvista
ms.custom: RS5
---

# FN_VMB_SERVER_CHANNEL_INIT_SET_FLAGS callback function

## -description

The <b>VmbServerChannelInitSetFlags</b> function sets flags unique to server channel endpoints.

## -prototype

```cpp
//Declaration

FN_VMB_SERVER_CHANNEL_INIT_SET_FLAGS FnVmbServerChannelInitSetFlags; 

// Definition

NTSTATUS FnVmbServerChannelInitSetFlags 
(
	VMBCHANNEL Channel
	UINT32 Flags
)
{...}

```

## -parameters

### -param Channel

A handle for a channel. 

### -param Flags

A collection of bit flags to set.

## -returns

<b>VmbServerChannelInitSetFlags</b> returns the following status values: 

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
The <i>Flags</i> value has invalid bits set.

</td>
</tr>
</table>

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also
