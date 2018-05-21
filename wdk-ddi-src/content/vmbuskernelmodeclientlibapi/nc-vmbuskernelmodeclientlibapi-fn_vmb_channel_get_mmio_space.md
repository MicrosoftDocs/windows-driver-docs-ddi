---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_GET_MMIO_SPACE
title: FN_VMB_CHANNEL_GET_MMIO_SPACE
author: windows-driver-content
description: The VmbChannelGetMmioSpace function retrieves the kernel virtual address of the MMIO space allocated to a channel.
ms.assetid: c34ca88d-10bb-49c5-bddc-606367926b0c
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
-	FN_VMB_CHANNEL_GET_MMIO_SPACE
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_GET_MMIO_SPACE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The **VmbChannelGetMmioSpace** function retrieves the kernel virtual address of the MMIO space allocated to a channel. This MMIO space is reserved via [**VmbServerChannelInitSetMmioMegabytes**](nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetmmiomegabytes.md). This function is only valid after the open channel callback has been received.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_GET_MMIO_SPACE FnVmbChannelGetMmioSpace; 

// Definition

VOID FnVmbChannelGetMmioSpace 
(
	VMBCHANNEL Channel
	UINT64 *MmioAddress
	UINT64 *MmioSize
)
{...}

```

## -parameters

### -param Channel

A handle for the channel. Allocated by [**VmbChannelAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_allocate.md).

### -param *MmioAddress

A pointer to a **PVOID** to fill with the MMIO physical address.

### -param *MmioSize

A pointer to the returned size of the MMIO space.

## -returns

This function does not return a value.

## -remarks

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

[**VmbServerChannelInitSetMmioMegabytes**](nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetmmiomegabytes.md)

[**VmbChannelAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_allocate.md)