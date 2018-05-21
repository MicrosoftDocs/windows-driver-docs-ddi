---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_INIT_SET_MAXIMUM_PACKET_SIZE
title: FN_VMB_CHANNEL_INIT_SET_MAXIMUM_PACKET_SIZE
author: windows-driver-content
description: The VmbChannelInitSetMaximumPacketSize function sets the maximum packet size that can be delivered through a channel, which is the maximum size that will ever be specified by the VmbPacketSend function.
ms.assetid: 88bb4032-3349-485a-a276-48f993c68a88
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
-	FN_VMB_CHANNEL_INIT_SET_MAXIMUM_PACKET_SIZE
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_INIT_SET_MAXIMUM_PACKET_SIZE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The  <b>VmbChannelInitSetMaximumPacketSize</b> function sets the maximum packet size that can be delivered through a channel, which is the maximum size that will ever be specified by the <a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a> function.  

## -prototype

```
//Declaration

FN_VMB_CHANNEL_INIT_SET_MAXIMUM_PACKET_SIZE FnVmbChannelInitSetMaximumPacketSize; 

// Definition

NTSTATUS FnVmbChannelInitSetMaximumPacketSize 
(
	VMBCHANNEL Channel
	UINT32 PacketSize
)
{...}

```

## -parameters

### -param Channel

A handle for the channel. 

### -param PacketSize

Maximum size, in bytes, of a packet.

## -returns

<b>VmbChannelInitSetMaximumPacketSize</b> returns one of the following status values: 

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
The <i>PacketSize</i> value is invalid. Zero (0) is invalid.

</td>
</tr>
</table>

## -remarks

This function can only be called during channel initialization. 

The size of the ring buffers is, in part, based on this maximum packet size. 

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

<a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a>