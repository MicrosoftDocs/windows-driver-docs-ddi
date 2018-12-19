---
UID: NS:hdaudio._HDAUDIO_BUS_INTERFACE_V3
title: _HDAUDIO_BUS_INTERFACE_V3
author: windows-driver-content
description: 
tech.root: audio
ms.assetid: a7bcda7e-4e39-4250-9154-6af32cdc1ecf
ms.author: windowsdriverdev
ms.date: 12/19/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _HDAUDIO_BUS_INTERFACE_V3, HDAUDIO_BUS_INTERFACE_V3, *PHDAUDIO_BUS_INTERFACE_V3, 
req.header: hdaudio.h
req.include-header: hdaudio.h 
req.target-type:
req.target-min-winverclnt: 19H1
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: HDAUDIO_BUS_INTERFACE_V3, *PHDAUDIO_BUS_INTERFACE_V3
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	hdaudio.h
api_name: 
-	_HDAUDIO_BUS_INTERFACE_V3
product: Windows
targetos: Windows
---

# _HDAUDIO_BUS_INTERFACE_V3 structure

## -description


## -struct-fields

### -field Size
Specifies the size, in bytes, of the HDAUDIO_BUS_INTERFACE_V3 structure.

### -field Version
Specifies the version of the baseline HD Audio DDI.
 
### -field Context
A pointer to interface-specific context information.

### -field InterfaceReference
A pointer to a driver-supplied routine that increments the reference count for the interface.
 
### -field InterfaceDereference
A pointer to a driver-supplied routine that decrements the reference count for the interface.
 
### -field TransferCodecVerbs
A function pointer to the TransferCodecVerbs routine.
 
### -field AllocateCaptureDmaEngine
A function pointer to the AllocateCaptureDmaEngine routine.
 
### -field AllocateRenderDmaEngine
A function pointer to the AllocateRenderDmaEngine routine.
 
### -field ChangeBandwidthAllocation
A function pointer to the ChangeBandwidthAllocation routine.
 
### -field AllocateDmaBuffer
A function pointer to the AllocateDmaBuffer routine.
### -field FreeDmaBuffer
A function pointer to the FreeDmaBuffer routine.
 
### -field FreeDmaEngine
A function pointer to the FreeDmaEngine routine.
 
### -field SetDmaEngineState
A function pointer to the SetDmaEngineState routine.
 
### -field GetWallClockRegister
A function pointer to the GetWallClockRegister routine.
 
### -field GetLinkPositionRegister
A function pointer to the GetLinkPositionRegister routine.
 
### -field RegisterEventCallback
A function pointer to the RegisterEventCallback routine.
 
### -field UnregisterEventCallback
A function pointer to the UnregisterEventCallback routine.
 
### -field GetDeviceInformation
A function pointer to the GetDeviceInformation routine.
 
### -field GetResourceInformation
A function pointer to the GetResourceInformation routine.
 
### -field AllocateDmaBufferWithNotification
A function pointer to the AllocateDmaBufferWithNotification routine.
 
### -field FreeDmaBufferWithNotification
A function pointer to the FreeDmaBufferWithNotification routine.
 
### -field RegisterNotificationEvent
A function pointer to the RegisterNotificationEvent routine.
 
### -field UnregisterNotificationEvent
A function pointer to the UnregisterNotificationEvent routine.
 
### -field RegisterNotificationCallback
A function pointer to the RegisterNotificationCallback routine.
 
### -field UnregisterNotificationCallback
A function pointer to the UnregisterNotificationCallback routine.
 

## -remarks
The [IRP_MN_QUERY_INTERFACE IOCTL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface) uses this structure to provide interface information to a client that is querying the HD Audio bus driver for the HD Audio DDI.

The names and definitions of the first five members of the HDAUDIO_BUS_INTERFACE_V3 structure (Size, Version, Context, InterfaceReference, and InterfaceDereference) are the same as in the INTERFACE structure. The remaining members are specific to the baseline HD Audio DDI and specify function pointers to the routines in the DDI.

## -see-also

[IRP_MN_QUERY_INTERFACE IOCTL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface)