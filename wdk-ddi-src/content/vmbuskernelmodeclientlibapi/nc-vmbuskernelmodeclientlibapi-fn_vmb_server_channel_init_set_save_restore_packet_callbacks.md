---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS
title: FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS (vmbuskernelmodeclientlibapi.h)
description: The VmbServerChannelInitSetSaveRestorePacketCallbacks function sets the save and restore callback functions that are called for each packet when the driver calls a save function, such as VmbChannelSaveBegin, VmbChannelSaveContinue, and VmbChannelSaveEnd, or the VmbChannelRestoreFromBuffer function.
ms.date: 09/13/2018
keywords: ["FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS callback function"]
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
targetos: Windows
tech.root: netvista
ms.custom: RS5
f1_keywords:
 - FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS
 - vmbuskernelmodeclientlibapi/FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS
---

# FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS callback function


## -description

The <b>VmbServerChannelInitSetSaveRestorePacketCallbacks</b> function sets the save and restore callback functions that are called for each packet when the
driver calls a save function, such as <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsavebegin">VmbChannelSaveBegin</a>, <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue">VmbChannelSaveContinue</a>, and <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend">VmbChannelSaveEnd</a>, or the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelrestorefrombuffer">VmbChannelRestoreFromBuffer</a> function.

## -parameters

### -param Channel

A handle for a channel.

### -param SavePacketCallback

A callback function to call during channel save.

### -param RestorePacketCallback

A callback function to call during channel restore.

## -returns

<b>VmbServerChannelInitSetSaveRestorePacketCallbacks</b> returns the following status values:

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

## -prototype

```cpp
//Declaration

FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS FnVmbServerChannelInitSetSaveRestorePacketCallbacks; 

// Definition

NTSTATUS FnVmbServerChannelInitSetSaveRestorePacketCallbacks 
(
	VMBCHANNEL Channel
	PFN_VMB_CHANNEL_SAVE_PACKET SavePacketCallback
	PFN_VMB_CHANNEL_RESTORE_PACKET RestorePacketCallback
)
{...}

```

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelrestorefrombuffer">VmbChannelRestoreFromBuffer</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsavebegin">VmbChannelSaveBegin</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsavecontinue">VmbChannelSaveContinue</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsaveend">VmbChannelSaveEnd</a>
