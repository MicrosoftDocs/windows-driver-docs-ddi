---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS
title: FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS
author: windows-driver-content
description: The VmbChannelInitSetProcessPacketCallbacks function sets callback functions for packet processing.
tech.root: netvista
ms.assetid: 863dc828-cd80-480a-99ee-0314824e4b8b
ms.author: windowsdriverdev
ms.date: 05/21/2018
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
-	FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetProcessPacketCallbacks</b>  function sets callback functions for packet processing.  

## -prototype

```
//Declaration

FN_VMB_CHANNEL_INIT_SET_PROCESS_PACKET_CALLBACKS FnVmbChannelInitSetProcessPacketCallbacks; 

// Definition

NTSTATUS FnVmbChannelInitSetProcessPacketCallbacks 
(
	VMBCHANNEL Channel
	PFN_VMB_CHANNEL_PROCESS_PACKET ProcessPacketCallback
	PFN_VMB_CHANNEL_PROCESSING_COMPLETE ProcessingCompleteCallback
)
{...}

```

## -parameters

### -param Channel

A handle for the channel. 

### -param ProcessPacketCallback

A callback function to call when a packet is ready for processing.

### -param ProcessingCompleteCallback

A callback function to call when processing of a batch of packets has been completed.

## -returns

**VmbChannelInitSetProcessPacketCallbacks** returns one of the following status values: 

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
<dt><b> STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

</td>
</tr>
</table>

## -remarks

This function is only meaningful if Kernel Mode Client Library (KMCL) queue
management is not suppressed.  

<b>ProcessPacketCallback</b> is invoked for every packet that
is received.  <a href="https://msdn.microsoft.com/E30A169E-0EC6-4128-B268-5FC1CD37A877">EvtVmbChannelProcessingComplete</a> will be invoked every time the ring buffer that contains incoming packets transitions from non-empty to empty. This happens
after the last invocation of <b>ProcessPacketCallback</b> in a single batch.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://msdn.microsoft.com/E30A169E-0EC6-4128-B268-5FC1CD37A877">EvtVmbChannelProcessingComplete</a>



<a href="https://msdn.microsoft.com/437DC9C5-CE73-45E8-AC4A-CFF9249809AD">ProcessPacketCallback</a>
