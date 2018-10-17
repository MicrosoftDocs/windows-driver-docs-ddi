---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS
title: FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS
author: windows-driver-content
description: The VmbServerChannelInitSetSaveRestorePacketCallbacks function sets the save and restore callback functions that are called for each packet when the driver calls a save function, such as VmbChannelSaveBegin, VmbChannelSaveContinue, and VmbChannelSaveEnd, or the VmbChannelRestoreFromBuffer function.
ms.assetid: b79bf865-ba3d-4309-8991-a9b8e2ba335f
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
-	FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS
product: 
- Windows
targetos: Windows
tech.root: netvista
---

# FN_VMB_SERVER_CHANNEL_INIT_SET_SAVE_RESTORE_PACKET_CALLBACKS callback function

## -description

The <b>VmbServerChannelInitSetSaveRestorePacketCallbacks</b> function sets the save and restore callback functions that are called for each packet when the
driver calls a save function, such as <a href="https://msdn.microsoft.com/A0946287-3ED2-4DE1-A3D7-46611B25BB93">VmbChannelSaveBegin</a>, <a href="https://msdn.microsoft.com/57266CAE-C069-4379-92FD-0F93FECC6EB5">VmbChannelSaveContinue</a>, and <a href="https://msdn.microsoft.com/0E61AF98-DC71-4234-B337-71B2AF65D858">VmbChannelSaveEnd</a>, or the <a href="https://msdn.microsoft.com/5A063585-AC45-44DF-BE21-FA1BB6283E6F">VmbChannelRestoreFromBuffer</a> function.

## -prototype

```
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

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

<a href="https://msdn.microsoft.com/5A063585-AC45-44DF-BE21-FA1BB6283E6F">VmbChannelRestoreFromBuffer</a>



<a href="https://msdn.microsoft.com/A0946287-3ED2-4DE1-A3D7-46611B25BB93">VmbChannelSaveBegin</a>



<a href="https://msdn.microsoft.com/57266CAE-C069-4379-92FD-0F93FECC6EB5">VmbChannelSaveContinue</a>



<a href="https://msdn.microsoft.com/0E61AF98-DC71-4234-B337-71B2AF65D858">VmbChannelSaveEnd</a>
