---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY
title: FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY
author: windows-driver-content
description: Guest VM updates to the outgoing monitor latency for MNF interrupts.
tech.root: netvista
ms.assetid: ceafe0bd-0d01-4c86-9812-8baa616e9fd7
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
-	FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Guest VM updates to the outgoing monitor latency for MNF interrupts.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_SET_INTERRUPT_LATENCY FnVmbChannelSetInterruptLatency; 

// Definition

NTSTATUS FnVmbChannelSetInterruptLatency 
(
	VMBCHANNEL Channel
	UINT16 Latency
	PUINT16 OriginalLatency
)
{...}

```

## -parameters

### -param Channel

A handle for the channel. Allocated by [**VmbChannelAllocate**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_allocate.md).

### -param Latency

The desired monitor latency in 100ns units.

### -param OriginalLatency

On success, set to the previous latency value.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

This call is valid for opened channels, that is between the calls to [*EvtChannelOpened*](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened.md) and [*EvtChannelClosed*](nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_closed.md), inclusive.

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
