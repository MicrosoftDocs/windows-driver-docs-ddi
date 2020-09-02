---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_SERVER_CHANNEL_INIT_SET_MMIO_MEGABYTES
title: FN_VMB_SERVER_CHANNEL_INIT_SET_MMIO_MEGABYTES (vmbuskernelmodeclientlibapi.h)
description: The VmbServerChannelInitSetMmioMegabytes function specifies the amount, megabytes, of guest memory-mapped I/O (MMIO) space to reserve for the device.
ms.assetid: d08cc2fd-2418-4047-b34c-09519ae0b531
ms.date: 09/13/2018
keywords: ["FN_VMB_SERVER_CHANNEL_INIT_SET_MMIO_MEGABYTES callback function"]
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
 - FN_VMB_SERVER_CHANNEL_INIT_SET_MMIO_MEGABYTES
 - vmbuskernelmodeclientlibapi/FN_VMB_SERVER_CHANNEL_INIT_SET_MMIO_MEGABYTES
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_SERVER_CHANNEL_INIT_SET_MMIO_MEGABYTES
product:
 - Windows
---

# FN_VMB_SERVER_CHANNEL_INIT_SET_MMIO_MEGABYTES callback function


## -description

The <b>VmbServerChannelInitSetMmioMegabytes</b> function specifies the amount, megabytes, of guest memory-mapped I/O (MMIO) space to reserve for the device.

## -parameters

### -param Channel

A handle for a channel.

### -param MmioMegabytes

The amount of MMIO space, in megabytes, to reserve.

### -param MmioMegabytesOptional

The amount of extra optional MMIO space, in megabytes, to reserve.

## -returns

<b>VmbServerChannelInitSetMmioMegabytes</b> returns the following status values: 

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
 Both <i>MmioMegabytes</i> and <i>MmioMegabytesOptional</i> have a value of zero (0). One of these parameters must be greater than zero 

</td>
</tr>
</table>

## -prototype

```cpp
//Declaration

FN_VMB_SERVER_CHANNEL_INIT_SET_MMIO_MEGABYTES FnVmbServerChannelInitSetMmioMegabytes; 

// Definition

NTSTATUS FnVmbServerChannelInitSetMmioMegabytes 
(
	VMBCHANNEL Channel
	UINT16 MmioMegabytes
	UINT16 MmioMegabytesOptional
)
{...}

```

## -remarks

This function exists as a convenience for driver creators. Everything it does could be done by interacting the with the guest plug-and-play manager and requesting memory-mapped I/O space directly. It is a common requirement that the Windows and Linux VMBus drivers have the capacity to reserve MMIO space on behalf of the client. This function allows the server endpoint to suggest the right amount of MMIO space to reserve.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

