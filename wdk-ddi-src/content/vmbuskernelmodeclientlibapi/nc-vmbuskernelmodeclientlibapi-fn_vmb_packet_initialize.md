---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_INITIALIZE
title: FN_VMB_PACKET_INITIALIZE
author: windows-driver-content
description: The VmbPacketInitialize function initializes a buffer to contain a VMBus packet.
ms.assetid: 440d75dc-1b2e-4460-b0b4-d0e949e2e165
ms.author: windowsdriverdev
ms.date: 05/22/2018
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
-	FN_VMB_PACKET_INITIALIZE
product: Windows
targetos: Windows
---

# FN_VMB_PACKET_INITIALIZE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketInitialize</b> function initializes a buffer to contain a VMBus packet. 

## -prototype

```
//Declaration

FN_VMB_PACKET_INITIALIZE FnVmbPacketInitialize; 

// Definition

NTSTATUS FnVmbPacketInitialize 
(
	VMBCHANNEL Channel
	VMBPACKET VmbPacket
	UINT32 ByteCount
)
{...}

```

## -parameters

### -param Channel

A handle for a channel.

### -param VmbPacket

The buffer to use to store the VMBus packet.

### -param ByteCount

The size of <i>Buffer</i>, in bytes.

## -returns

<b>VmbPacketInitialize</b> returns the following status codes:

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
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
The value of  <i>ByteCount</i> is not valid. It needs to be greater than the maximum packet size plus the size of a void pointer. 

</td>
</tr>
</table>

## -remarks

The size of the buffer must be at
least the size calculated by using the <a href="https://msdn.microsoft.com/3E7EE060-4B1F-4B28-A617-5B1393CEE936">VmbChannelSizeofPacket</a> function.  

<b>VmbPacketInitialize</b> is  an alternative
to the <a href="https://msdn.microsoft.com/F121A7BC-5504-4CF5-8C8A-0568D6C4F77F">VmbPacketAllocate</a> function. Use the current function if the caller supplies the
memory for the packet object. 

The packet's initial completion routine is invalid and must be set before
sending the packet.

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

<a href="https://msdn.microsoft.com/3E7EE060-4B1F-4B28-A617-5B1393CEE936">VmbChannelSizeofPacket</a>



<a href="https://msdn.microsoft.com/F121A7BC-5504-4CF5-8C8A-0568D6C4F77F">VmbPacketAllocate</a>