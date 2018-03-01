---
UID: NS:hdaudio._HDAUDIO_BUS_INTERFACE_V2
title: "_HDAUDIO_BUS_INTERFACE_V2"
author: windows-driver-content
description: The HDAUDIO_BUS_INTERFACE_V2 structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI.
old-location: audio\hdaudio_bus_interface_v2.htm
old-project: audio
ms.assetid: 7d639909-dc56-4ec5-b596-bfbbf262a3d9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PHDAUDIO_BUS_INTERFACE_V2, HDAUDIO_BUS_INTERFACE_V2, HDAUDIO_BUS_INTERFACE_V2 structure [Audio Devices], PHDAUDIO_BUS_INTERFACE_V2, PHDAUDIO_BUS_INTERFACE_V2 structure pointer [Audio Devices], _HDAUDIO_BUS_INTERFACE_V2, aud-prop2_42a4681c-608a-479b-a33d-725f9625d64b.xml, audio.hdaudio_bus_interface_v2, hdaudio/HDAUDIO_BUS_INTERFACE_V2, hdaudio/PHDAUDIO_BUS_INTERFACE_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hdaudio.h
api_name:
-	HDAUDIO_BUS_INTERFACE_V2
product: Windows
targetos: Windows
req.typenames: HDAUDIO_BUS_INTERFACE_V2, *PHDAUDIO_BUS_INTERFACE_V2
---

# _HDAUDIO_BUS_INTERFACE_V2 structure


## -description


The HDAUDIO_BUS_INTERFACE_V2 structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI. The interface represented by this structure provides all the functionality of <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a> and can also support flexible DMA-driven event notification.


## -syntax


````
typedef struct _HDAUDIO_BUS_INTERFACE_V2 {
  USHORT                                 Size;
  USHORT                                 Version;
  PVOID                                  Context;
  PINTERFACE_REFERENCE                   InterfaceReference;
  PINTERFACE_DEREFERENCE                 InterfaceDereference;
  PTRANSFER_CODEC_VERBS                  TransferCodecVerbs;
  PALLOCATE_CAPTURE_DMA_ENGINE           AllocateCaptureDmaEngine;
  PALLOCATE_RENDER_DMA_ENGINE            AllocateRenderDmaEngine;
  PCHANGE_BANDWIDTH_ALLOCATION           ChangeBandwidthAllocation;
  PALLOCATE_DMA_BUFFER                   AllocateDmaBuffer;
  PFREE_DMA_BUFFER                       FreeDmaBuffer;
  PFREE_DMA_ENGINE                       FreeDmaEngine;
  PSET_DMA_ENGINE_STATE                  SetDmaEngineState;
  PGET_WALL_CLOCK_REGISTER               GetWallClockRegister;
  PGET_LINK_POSITION_REGISTER            GetLinkPositionRegister;
  PREGISTER_EVENT_CALLBACK               RegisterEventCallback;
  PUNREGISTER_EVENT_CALLBACK             UnregisterEventCallback;
  PGET_DEVICE_INFORMATION                GetDeviceInformation;
  PGET_RESOURCE_INFORMATION              GetResourceInformation;
  PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION AllocateDmaBufferWithNotification;
  PFREE_DMA_BUFFER_WITH_NOTIFICATION     FreeDmaBufferWithNotification;
  PREGISTER_NOTIFICATION_EVENT           RegisterNotificationEvent;
  PUNREGISTER_NOTIFICATION_EVENT         UnregisterNotificationEvent;
} HDAUDIO_BUS_INTERFACE_V2, *PHDAUDIO_BUS_INTERFACE_V2;
````


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

A function pointer to the <a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a> routine.


### -field AllocateCaptureDmaEngine

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> routine.


### -field AllocateRenderDmaEngine

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a> routine.


### -field ChangeBandwidthAllocation

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a> routine.


### -field AllocateDmaBuffer

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> routine.


### -field FreeDmaBuffer

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a> routine.


### -field FreeDmaEngine

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pfree_dma_engine.md">FreeDmaEngine</a> routine.


### -field SetDmaEngineState

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a> routine.


### -field GetWallClockRegister

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pget_wall_clock_register.md">GetWallClockRegister</a> routine.


### -field GetLinkPositionRegister

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pget_link_position_register.md">GetLinkPositionRegister</a> routine.


### -field RegisterEventCallback

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a> routine.


### -field UnregisterEventCallback

A function pointer to the <a href="..\hdaudio\nc-hdaudio-punregister_event_callback.md">UnregisterEventCallback</a> routine.


### -field GetDeviceInformation

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pget_device_information.md">GetDeviceInformation</a> routine.


### -field GetResourceInformation

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pget_resource_information.md">GetResourceInformation</a> routine.


### -field AllocateDmaBufferWithNotification

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer_with_notification.md">AllocateDmaBufferWithNotification</a> routine.


### -field FreeDmaBufferWithNotification

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer_with_notification.md">FreeDmaBufferWithNotification</a> routine.


### -field RegisterNotificationEvent

A function pointer to the <a href="..\hdaudio\nc-hdaudio-pregister_notification_event.md">RegisterNotificationEvent</a> routine.


### -field UnregisterNotificationEvent

A function pointer to the <a href="..\hdaudio\nc-hdaudio-punregister_notification_event.md">UnregisterNotificationEvent</a> routine.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IOCTL uses this structure to provide interface information to a client that is querying the HD Audio bus driver for the HD Audio DDI.

The names and definitions of the first five members of the <b>HDAUDIO_BUS_INTERFACE_V2</b> structure (Size, Version, Context, InterfaceReference, and InterfaceDereference) are the same as in the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure. The remaining members are specific to the baseline HD Audio DDI and specify function pointers to the routines in the DDI. 




## -see-also

<a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pget_link_position_register.md">GetLinkPositionRegister</a>



<a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a>



<a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a>



<a href="..\hdaudio\nc-hdaudio-pget_device_information.md">GetDeviceInformation</a>



<a href="..\hdaudio\nc-hdaudio-pget_resource_information.md">GetResourceInformation</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer_with_notification.md">AllocateDmaBufferWithNotification</a>



<a href="..\hdaudio\nc-hdaudio-pget_wall_clock_register.md">GetWallClockRegister</a>



<a href="..\hdaudio\nc-hdaudio-pfree_dma_engine.md">FreeDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer_with_notification.md">FreeDmaBufferWithNotification</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>



<a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a>



<a href="..\hdaudio\nc-hdaudio-punregister_notification_event.md">UnregisterNotificationEvent</a>



<a href="..\hdaudio\nc-hdaudio-pregister_notification_event.md">RegisterNotificationEvent</a>



<a href="..\hdaudio\nc-hdaudio-punregister_event_callback.md">UnregisterEventCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_BUS_INTERFACE_V2 structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

