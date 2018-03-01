---
UID: NS:hdaudio._HDAUDIO_BUS_INTERFACE
title: "_HDAUDIO_BUS_INTERFACE"
author: windows-driver-content
description: The HDAUDIO_BUS_INTERFACE structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE_BDL structure.
old-location: audio\hdaudio_bus_interface.htm
old-project: audio
ms.assetid: 6b3bc5ce-05d2-45e0-91d8-6bb34e58777f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PHDAUDIO_BUS_INTERFACE, HDAUDIO_BUS_INTERFACE, HDAUDIO_BUS_INTERFACE structure [Audio Devices], PHDAUDIO_BUS_INTERFACE, PHDAUDIO_BUS_INTERFACE structure pointer [Audio Devices], _HDAUDIO_BUS_INTERFACE, aud-prop2_4d39bbd4-8c0b-4f2c-98a7-618d891593c1.xml, audio.hdaudio_bus_interface, hdaudio/HDAUDIO_BUS_INTERFACE, hdaudio/PHDAUDIO_BUS_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	HDAUDIO_BUS_INTERFACE
product: Windows
targetos: Windows
req.typenames: HDAUDIO_BUS_INTERFACE, *PHDAUDIO_BUS_INTERFACE
---

# _HDAUDIO_BUS_INTERFACE structure


## -description


The HDAUDIO_BUS_INTERFACE structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. Another variant of this DDI is specified by the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


## -syntax


````
typedef struct _HDAUDIO_BUS_INTERFACE {
  USHORT                       Size;
  USHORT                       Version;
  PVOID                        Context;
  PINTERFACE_REFERENCE         InterfaceReference;
  PINTERFACE_DEREFERENCE       InterfaceDereference;
  PTRANSFER_CODEC_VERBS        TransferCodecVerbs;
  PALLOCATE_CAPTURE_DMA_ENGINE AllocateCaptureDmaEngine;
  PALLOCATE_RENDER_DMA_ENGINE  AllocateRenderDmaEngine;
  PCHANGE_BANDWIDTH_ALLOCATION ChangeBandwidthAllocation;
  PALLOCATE_DMA_BUFFER         AllocateDmaBuffer;
  PFREE_DMA_BUFFER             FreeDmaBuffer;
  PFREE_DMA_ENGINE             FreeDmaEngine;
  PSET_DMA_ENGINE_STATE        SetDmaEngineState;
  PGET_WALL_CLOCK_REGISTER     GetWallClockRegister;
  PGET_LINK_POSITION_REGISTER  GetLinkPositionRegister;
  PREGISTER_EVENT_CALLBACK     RegisterEventCallback;
  PUNREGISTER_EVENT_CALLBACK   UnregisterEventCallback;
  PGET_DEVICE_INFORMATION      GetDeviceInformation;
  PGET_RESOURCE_INFORMATION    GetResourceInformation;
} HDAUDIO_BUS_INTERFACE, *PHDAUDIO_BUS_INTERFACE;
````


## -struct-fields




### -field Size

Specifies the size in bytes of the HDAUDIO_BUS_INTERFACE structure.


### -field Version

Specifies the version of the baseline HD Audio DDI.


### -field Context

Pointer to interface-specific context information.


### -field InterfaceReference

Pointer to a driver-supplied routine that increments the interface's reference count.


### -field InterfaceDereference

Pointer to a driver-supplied routine that decrements the interface's reference count.


### -field TransferCodecVerbs

Function pointer to the <a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a> routine.


### -field AllocateCaptureDmaEngine

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> routine.


### -field AllocateRenderDmaEngine

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a> routine.


### -field ChangeBandwidthAllocation

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a> routine.


### -field AllocateDmaBuffer

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> routine.


### -field FreeDmaBuffer

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a> routine.


### -field FreeDmaEngine

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pfree_dma_engine.md">FreeDmaEngine</a> routine.


### -field SetDmaEngineState

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a> routine.


### -field GetWallClockRegister

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pget_wall_clock_register.md">GetWallClockRegister</a> routine.


### -field GetLinkPositionRegister

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pget_link_position_register.md">GetLinkPositionRegister</a> routine.


### -field RegisterEventCallback

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a> routine.


### -field UnregisterEventCallback

Function pointer to the <a href="..\hdaudio\nc-hdaudio-punregister_event_callback.md">UnregisterEventCallback</a> routine.


### -field GetDeviceInformation

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pget_device_information.md">GetDeviceInformation</a> routine.


### -field GetResourceInformation

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pget_resource_information.md">GetResourceInformation</a> routine.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IOCTL uses this structure to provide interface information to a client that is querying the HD Audio bus driver for the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE_BDL structure.

The HDAUDIO_BUS_INTERFACE and HDAUDIO_BUS_INTERFACE_BDL structures are similar but have the following differences:

<ul>
<li>
HDAUDIO_BUS_INTERFACE has two members, <b>AllocateDmaBuffer</b> and <b>FreeDmaBuffer</b>, that are not present in HDAUDIO_BUS_INTERFACE_BDL.

</li>
<li>
HDAUDIO_BUS_INTERFACE_BDL has three members, <a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a>, <a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a>, and <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>, that are not present in HDAUDIO_BUS_INTERFACE.

</li>
</ul>
For more information, see <a href="https://msdn.microsoft.com/e24071d3-9021-40c0-907a-91ada8a1306b">Differences Between the HD Audio DDI Versions</a>.

The names and definitions of the first five members (<b>Size</b>, <b>Version</b>, <b>Context</b>, <b>InterfaceReference</b>, and <b>InterfaceDereference</b>) are the same as in the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure. The remaining members are specific to the baseline HD Audio DDI and specify function pointers to the routines in the DDI. For more information, see <a href="https://msdn.microsoft.com/78667254-62a6-41fe-af36-43dbdea63aa8">Obtaining an HDAUDIO_BUS_INTERFACE DDI Object</a>.




## -see-also

<a href="..\hdaudio\nc-hdaudio-pget_link_position_register.md">GetLinkPositionRegister</a>



<a href="..\hdaudio\nc-hdaudio-pget_device_information.md">GetDeviceInformation</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pget_resource_information.md">GetResourceInformation</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a>



<a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>



<a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a>



<a href="..\hdaudio\nc-hdaudio-pfree_dma_engine.md">FreeDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-punregister_event_callback.md">UnregisterEventCallback</a>



<a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>



<a href="..\hdaudio\nc-hdaudio-pget_wall_clock_register.md">GetWallClockRegister</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_BUS_INTERFACE structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

