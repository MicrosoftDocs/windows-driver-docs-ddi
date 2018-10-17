---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_RESTORE_FROM_BUFFER
title: FN_VMB_CHANNEL_RESTORE_FROM_BUFFER
author: windows-driver-content
description: The VmbChannelRestoreFromBuffer function restores the client state from previously saved state. The driver must check the return value of the function.
tech.root: netvista
ms.assetid: f555fb01-73c9-449e-88f0-24480e44f86b
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
-	FN_VMB_CHANNEL_RESTORE_FROM_BUFFER
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_RESTORE_FROM_BUFFER callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelRestoreFromBuffer</b>  function restores the client state from previously saved state.
The driver must check the return value of the function.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_RESTORE_FROM_BUFFER FnVmbChannelRestoreFromBuffer; 

// Definition

NTSTATUS FnVmbChannelRestoreFromBuffer 
(
	VMBCHANNEL Channel
	PVOID Buffer
	ULONG BufferSize
)
{...}

```

## -parameters

### -param Channel

 A handle for a channel.

### -param Buffer

A pointer to a buffer that contains previously saved state.

### -param BufferSize 

The size, in bytes, of the buffer.

## -returns

<b>VmbChannelRestoreFromBuffer</b> returns one of the following status values: 

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
<dt><b>STATUS_MORE_PROCESSING_REQUIRED</b></dt>
</dl>
</td>
<td width="60%">
State was restored successfully,     but more chunks were saved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status code for which NT_SUCCESS is FALSE</b></dt>
</dl>
</td>
<td width="60%">
The function failed.

</td>
</tr>
</table>

## -remarks

The caller is expected to call this function with buffers that contain whole
"chunks" of stored data.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also
