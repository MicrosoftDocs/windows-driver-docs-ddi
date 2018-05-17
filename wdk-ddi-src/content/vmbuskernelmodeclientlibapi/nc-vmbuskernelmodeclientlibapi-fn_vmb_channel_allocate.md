---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_ALLOCATE
title: FN_VMB_CHANNEL_ALLOCATE
author: windows-driver-content
description:  The VmbChannelAllocate function allocates a new VMBus channel that has default parameters and callbacks. 
ms.assetid: b7d23f6f-cc08-4e0b-aca9-9e8234465acb
ms.author: windowsdriverdev
ms.date: 05/17/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
-	FN_VMB_CHANNEL_ALLOCATE
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_ALLOCATE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. 
>
> To access the KMCL, allocate a **KMCL_CLIENT_INTERFACE_V1** structure to receive the interface, then call either [**WdfFdoQueryForInterface**](../wdffdo/nf-wdffdo-wdffdoqueryforinterface.md) or [**WdfIoTargetQueryForInterface**](../wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface.md) with the *InterfaceType* parameter set to **KMCL_CLIENT_INTERFACE_TYPE**, the *Size* parameter set to `sizeof(KMCL_CLIENT_INTERFACE_V1)`, and the *Version* parameter set to **KMCL_CLIENT_INTERFACE_VERSION_LATEST**.
>
> For more information about calling driver-defined interfaces, see [Using Driver-Defined Interfaces](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces).

The <b>VmbChannelAllocate</b> function allocates a new VMBus channel that has default parameters and callbacks. 

## -prototype

```
//Declaration

FN_VMB_CHANNEL_ALLOCATE FnVmbChannelAllocate; 

// Definition

NTSTATUS FnVmbChannelAllocate 
(
	PDEVICE_OBJECT ParentDeviceObject
	BOOLEAN IsServer
	VMBCHANNEL * Channel
)
{...}

```

## -parameters

### -param ParentDeviceObject

A pointer to the parent device.

### -param IsServer
Whether the new channel is a server endpoint.

### -param Channel

A pointer to an allocated channel.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

The
channel may be further initialized using the VMBus channel initialization routines before
it is enabled by using the  <a href="https://msdn.microsoft.com/A0256B3F-C35C-45AB-A825-0A82189F08DC">VmbChannelEnable</a> function. The channel must be freed by using the <a href="https://msdn.microsoft.com/E079527D-1687-4A12-B86E-96C89CE458CE">VmbChannelCleanup</a> function.


## -see-also

<a href="https://msdn.microsoft.com/E079527D-1687-4A12-B86E-96C89CE458CE">VmbChannelCleanup</a>



<a href="https://msdn.microsoft.com/A0256B3F-C35C-45AB-A825-0A82189F08DC">VmbChannelEnable</a>