---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SAVE_CONTINUE
title: FN_VMB_CHANNEL_SAVE_CONTINUE
description: The VmbChannelSaveContinue function saves the channel state to a buffer. Run the VmbChannelSaveBegin before you run this function. The driver must check the return value of the function.
tech.root: netvista
ms.assetid: 020dcfd9-f552-4b0a-ad82-0dea44bcec28
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
-	FN_VMB_CHANNEL_SAVE_CONTINUE
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_SAVE_CONTINUE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSaveContinue</b> function saves the channel state to a buffer.  Run the <a href="https://msdn.microsoft.com/A0946287-3ED2-4DE1-A3D7-46611B25BB93">VmbChannelSaveBegin</a> before you run this function. The driver must check the return value of the function.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_SAVE_CONTINUE FnVmbChannelSaveContinue; 

// Definition

NTSTATUS FnVmbChannelSaveContinue 
(
	VMBCHANNEL Channel
	PVOID SaveBuffer
	ULONG SaveBufferSize
	PULONG BytesFilled
	PULONG BytesRequired
)
{...}

```

## -parameters

### -param Channel

A handle for a channel to save. 

### -param SaveBuffer

A pointer to the buffer into which to save state information. 

### -param SaveBufferSize

The size, in bytes, of the save buffer.

### -param BytesFilled

A pointer to a variable that receives the number of bytes
that were copied to the save buffer.

### -param BytesRequired

A pointer to a variable that receives the number of
bytes that are needed for this function to make progress on the next
call.

## -returns

<b>VmbChannelSaveContinue</b> returns the following values: 

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
The state was saved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL </b></dt>
</dl>
</td>
<td width="60%">
The save buffer was too small.  The <i>BytesNeeded</i>
parameter     contains the number of bytes that are required to make any progress.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
Some data was written to the save
buffer, but there is more data to be saved.

</td>
</tr>
</table>

## -remarks

The save process saves
the data in "chunks" and can continue from the point it stopped. 

If the caller did not allocate enough space in advance, multiple calls may be needed.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

<a href="https://msdn.microsoft.com/A0946287-3ED2-4DE1-A3D7-46611B25BB93">VmbChannelSaveBegin</a>
