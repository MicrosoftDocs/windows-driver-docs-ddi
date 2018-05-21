---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_CLEANUP
title: FN_VMB_CHANNEL_CLEANUP
author: windows-driver-content
description: The VmbChannelCleanup function disposes of a channel that was allocated by using the VmbChannelAllocate function or initialized by using a VMBus channel initialization function.
ms.assetid: 08ed4d5b-5a84-43ac-b8b4-1bce6ece7f67
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
-	FN_VMB_CHANNEL_CLEANUP
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_CLEANUP callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelCleanup</b> function disposes of a channel that was allocated by using the <a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a> function  or initialized by using a  VMBus channel initialization function. 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_CLEANUP FnVmbChannelCleanup; 

// Definition

VOID FnVmbChannelCleanup 
(
	__drv_freesMem(Mem)VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel

The channel to clean up.

## -returns

This function does not return a value.

## -remarks

If the channel was allocated by <a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a>, <b>VmbChannelCleanup</b> also releases the channel. 

Before you call this function, the channel must be disabled.

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

<a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a>