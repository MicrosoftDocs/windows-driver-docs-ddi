---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_INIT_SET_CLIENT_CONTEXT_SIZE
title: FN_VMB_CHANNEL_INIT_SET_CLIENT_CONTEXT_SIZE
author: windows-driver-content
description: The VmbChannelInitSetClientContextSize function sets the size of the optional context area allocated for the client driver on each incoming packet.
ms.assetid: 6bf397fd-8c16-4bea-abed-9d1b71c3e66b
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
-	FN_VMB_CHANNEL_INIT_SET_CLIENT_CONTEXT_SIZE
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_INIT_SET_CLIENT_CONTEXT_SIZE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetClientContextSize</b> function sets the size of the optional context area allocated for the client driver
on each incoming packet.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_INIT_SET_CLIENT_CONTEXT_SIZE FnVmbChannelInitSetClientContextSize; 

// Definition

NTSTATUS FnVmbChannelInitSetClientContextSize 
(
	VMBCHANNEL Channel
	UINT32 ContextSize
)
{...}

```

## -parameters

### -param Channel

A handle for a channel.

### -param ContextSize

The size of the context area allocated on each packet object.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

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