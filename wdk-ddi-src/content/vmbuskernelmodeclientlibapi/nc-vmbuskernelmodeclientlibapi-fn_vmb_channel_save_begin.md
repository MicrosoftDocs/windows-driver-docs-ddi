---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SAVE_BEGIN
title: FN_VMB_CHANNEL_SAVE_BEGIN
author: windows-driver-content
description: The VmbChannelSaveBegin function initializes the context for saving the state of a channel. The driver must check the return value of the function.
ms.assetid: 986669ad-e997-4850-a9b1-b45d6f1497cd
ms.author: windowsdriverdev
ms.date: 05/21/2018
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
-	FN_VMB_CHANNEL_SAVE_BEGIN
product: Windows
targetos: Windows
---

# FN_VMB_CHANNEL_SAVE_BEGIN callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSaveBegin</b> function initializes the context for saving the state of a channel. The driver must check the return value of the function.

## -prototype

```
//Declaration

FN_VMB_CHANNEL_SAVE_BEGIN FnVmbChannelSaveBegin; 

// Definition

NTSTATUS FnVmbChannelSaveBegin 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel 

A handle for the channel to save.

## -returns

Returns STATUS_SUCCESS if the operation succeeded, or an appropriate NTSTATUS error code otherwise.

## -remarks

The
caller next calls the <a href="https://msdn.microsoft.com/57266CAE-C069-4379-92FD-0F93FECC6EB5"> VmbChannelSaveContinue</a> function multiple times until
all the state is saved, and then calls the <a href="https://msdn.microsoft.com/0E61AF98-DC71-4234-B337-71B2AF65D858">VmbChannelSaveEnd</a> function.

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

<a href="https://msdn.microsoft.com/57266CAE-C069-4379-92FD-0F93FECC6EB5"> VmbChannelSaveContinue</a>



<a href="https://msdn.microsoft.com/0E61AF98-DC71-4234-B337-71B2AF65D858">VmbChannelSaveEnd</a>