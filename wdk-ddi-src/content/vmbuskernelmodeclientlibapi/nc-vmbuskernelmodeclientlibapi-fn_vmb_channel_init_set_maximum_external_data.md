---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_INIT_SET_MAXIMUM_EXTERNAL_DATA
title: FN_VMB_CHANNEL_INIT_SET_MAXIMUM_EXTERNAL_DATA (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelInitSetMaximumExternalData function sets the maximum size and chain length of data that is described by a packet, but not directly sent in the packet. That is, the maximum size of the buffer described by an ExternalDataMdl.
tech.root: netvista
ms.assetid: 09e113ef-d1a5-444a-99c9-06a2a46c9734
ms.date: 05/21/2018
keywords: ["FN_VMB_CHANNEL_INIT_SET_MAXIMUM_EXTERNAL_DATA callback function"]
f1_keywords:
 - "vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_INIT_SET_MAXIMUM_EXTERNAL_DATA"
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
- FN_VMB_CHANNEL_INIT_SET_MAXIMUM_EXTERNAL_DATA
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_INIT_SET_MAXIMUM_EXTERNAL_DATA callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetMaximumExternalData</b> function sets the maximum size and chain length of data that is described by a
packet, but not directly sent in the packet. That is, the maximum size of the
buffer described by an <b>ExternalDataMdl</b>.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_INIT_SET_MAXIMUM_EXTERNAL_DATA FnVmbChannelInitSetMaximumExternalData; 

// Definition

NTSTATUS FnVmbChannelInitSetMaximumExternalData 
(
	VMBCHANNEL Channel
	UINT32 DataSize
	UINT32 ChainLength
)
{...}

```

## -parameters

### -param Channel

A pointer to a Kernel Mode Client Library (KMCL) channel.

### -param DataSize

The maximum size of external data.

### -param ChainLength

The maximum number of Memory Descriptor Lists (MDLs) in an incoming MDL chain.

## -returns

<b>VmbChannelInitSetMaximumExternalData</b> can return one of the following status values: 

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
The <i>DataSize</i> value is invalid. Zero (0) is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
The <i>ChainLength</i> value is  invalid. Zero (0) is invalid.

</td>
</tr>
</table>

## -remarks

The KMCL ensures that your ring buffers are large enough to send packets that contain buffers in the specified limits.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also
