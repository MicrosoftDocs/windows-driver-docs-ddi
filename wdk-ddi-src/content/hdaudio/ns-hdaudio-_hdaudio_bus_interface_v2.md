---
UID: NS:hdaudio._HDAUDIO_BUS_INTERFACE_V2
title: _HDAUDIO_BUS_INTERFACE_V2 (hdaudio.h)
description: The HDAUDIO_BUS_INTERFACE_V2 structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI.
old-location: audio\hdaudio_bus_interface_v2.htm
tech.root: audio
ms.assetid: 7d639909-dc56-4ec5-b596-bfbbf262a3d9
ms.date: 05/08/2018
keywords: ["HDAUDIO_BUS_INTERFACE_V2 structure"]
ms.keywords: "*PHDAUDIO_BUS_INTERFACE_V2, HDAUDIO_BUS_INTERFACE_V2, HDAUDIO_BUS_INTERFACE_V2 structure [Audio Devices], PHDAUDIO_BUS_INTERFACE_V2, PHDAUDIO_BUS_INTERFACE_V2 structure pointer [Audio Devices], _HDAUDIO_BUS_INTERFACE_V2, aud-prop2_42a4681c-608a-479b-a33d-725f9625d64b.xml, audio.hdaudio_bus_interface_v2, hdaudio/HDAUDIO_BUS_INTERFACE_V2, hdaudio/PHDAUDIO_BUS_INTERFACE_V2"
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: HDAUDIO_BUS_INTERFACE_V2, *PHDAUDIO_BUS_INTERFACE_V2
f1_keywords:
 - _HDAUDIO_BUS_INTERFACE_V2
 - hdaudio/_HDAUDIO_BUS_INTERFACE_V2
 - PHDAUDIO_BUS_INTERFACE_V2
 - hdaudio/PHDAUDIO_BUS_INTERFACE_V2
 - HDAUDIO_BUS_INTERFACE_V2
 - hdaudio/HDAUDIO_BUS_INTERFACE_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hdaudio.h
api_name:
 - HDAUDIO_BUS_INTERFACE_V2
---

# _HDAUDIO_BUS_INTERFACE_V2 structure


## -description

The HDAUDIO_BUS_INTERFACE_V2 structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI. The interface represented by this structure provides all the functionality of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a> and can also support flexible DMA-driven event notification.

## -struct-fields

### -field Size

Specifies the size, in bytes, of the HDAUDIO_BUS_INTERFACE_V2 structure.

### -field Version

Specifies the version of the baseline HD Audio DDI.

### -field Context

A pointer to interface-specific context information.

### -field InterfaceReference

A pointer to a driver-supplied routine that increments the reference count for the interface.

### -field InterfaceDereference

A pointer to a driver-supplied routine that decrements the reference count for the interface.

### -field TransferCodecVerbs

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">TransferCodecVerbs</a> routine.

### -field AllocateCaptureDmaEngine

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> routine.

### -field AllocateRenderDmaEngine

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a> routine.

### -field ChangeBandwidthAllocation

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pchange_bandwidth_allocation">ChangeBandwidthAllocation</a> routine.

### -field AllocateDmaBuffer

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a> routine.

### -field FreeDmaBuffer

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a> routine.

### -field FreeDmaEngine

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_engine">FreeDmaEngine</a> routine.

### -field SetDmaEngineState

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a> routine.

### -field GetWallClockRegister

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_wall_clock_register">GetWallClockRegister</a> routine.

### -field GetLinkPositionRegister

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_link_position_register">GetLinkPositionRegister</a> routine.

### -field RegisterEventCallback

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_event_callback">RegisterEventCallback</a> routine.

### -field UnregisterEventCallback

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_event_callback">UnregisterEventCallback</a> routine.

### -field GetDeviceInformation

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_device_information">GetDeviceInformation</a> routine.

### -field GetResourceInformation

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_resource_information">GetResourceInformation</a> routine.

### -field AllocateDmaBufferWithNotification

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer_with_notification">AllocateDmaBufferWithNotification</a> routine.

### -field FreeDmaBufferWithNotification

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer_with_notification">FreeDmaBufferWithNotification</a> routine.

### -field RegisterNotificationEvent

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_notification_event">RegisterNotificationEvent</a> routine.

### -field UnregisterNotificationEvent

A function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_notification_event">UnregisterNotificationEvent</a> routine.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> IOCTL uses this structure to provide interface information to a client that is querying the HD Audio bus driver for the HD Audio DDI.

The names and definitions of the first five members of the <b>HDAUDIO_BUS_INTERFACE_V2</b> structure (Size, Version, Context, InterfaceReference, and InterfaceDereference) are the same as in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure. The remaining members are specific to the baseline HD Audio DDI and specify function pointers to the routines in the DDI.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer_with_notification">AllocateDmaBufferWithNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pchange_bandwidth_allocation">ChangeBandwidthAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer_with_notification">FreeDmaBufferWithNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_engine">FreeDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_device_information">GetDeviceInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_link_position_register">GetLinkPositionRegister</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_resource_information">GetResourceInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_wall_clock_register">GetWallClockRegister</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_event_callback">RegisterEventCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_notification_event">RegisterNotificationEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">TransferCodecVerbs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_event_callback">UnregisterEventCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_notification_event">UnregisterNotificationEvent</a>

