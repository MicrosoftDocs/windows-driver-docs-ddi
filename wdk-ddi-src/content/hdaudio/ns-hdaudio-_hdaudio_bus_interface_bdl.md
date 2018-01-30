---
UID: NS:hdaudio._HDAUDIO_BUS_INTERFACE_BDL
title: "_HDAUDIO_BUS_INTERFACE_BDL"
author: windows-driver-content
description: The HDAUDIO_BUS_INTERFACE_BDL structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE structure.
old-location: audio\hdaudio_bus_interface_bdl.htm
old-project: audio
ms.assetid: 64523c09-35dd-45df-beed-ce8afb740f5d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: aud-prop2_f9b041b3-76fd-4176-9fc8-32eeda46cc32.xml, hdaudio/HDAUDIO_BUS_INTERFACE_BDL, HDAUDIO_BUS_INTERFACE_BDL, HDAUDIO_BUS_INTERFACE_BDL structure [Audio Devices], hdaudio/PHDAUDIO_BUS_INTERFACE_BDL, _HDAUDIO_BUS_INTERFACE_BDL, audio.hdaudio_bus_interface_bdl, PHDAUDIO_BUS_INTERFACE_BDL, PHDAUDIO_BUS_INTERFACE_BDL structure pointer [Audio Devices], *PHDAUDIO_BUS_INTERFACE_BDL
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hdaudio.h
apiname:
-	HDAUDIO_BUS_INTERFACE_BDL
product: Windows
targetos: Windows
req.typenames: HDAUDIO_BUS_INTERFACE_BDL, *PHDAUDIO_BUS_INTERFACE_BDL
---

# _HDAUDIO_BUS_INTERFACE_BDL structure


## -description


The HDAUDIO_BUS_INTERFACE_BDL structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. Another variant of this DDI is specified by the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a> structure.


## -syntax


````
typedef struct _HDAUDIO_BUS_INTERFACE_BDL {
  USHORT                          Size;
  USHORT                          Version;
  PVOID                           Context;
  PINTERFACE_REFERENCE            InterfaceReference;
  PINTERFACE_DEREFERENCE          InterfaceDereference;
  PTRANSFER_CODEC_VERBS           TransferCodecVerbs;
  PALLOCATE_CAPTURE_DMA_ENGINE    AllocateCaptureDmaEngine;
  PALLOCATE_RENDER_DMA_ENGINE     AllocateRenderDmaEngine;
  PCHANGE_BANDWIDTH_ALLOCATION    ChangeBandwidthAllocation;
  PALLOCATE_CONTIGUOUS_DMA_BUFFER AllocateContiguousDmaBuffer;
  PSETUP_DMA_ENGINE_WITH_BDL      SetupDmaEngineWithBdl;
  PFREE_CONTIGUOUS_DMA_BUFFER     FreeContiguousDmaBuffer;
  PFREE_DMA_ENGINE                FreeDmaEngine;
  PSET_DMA_ENGINE_STATE           SetDmaEngineState;
  PGET_WALL_CLOCK_REGISTER        GetWallClockRegister;
  PGET_LINK_POSITION_REGISTER     GetLinkPositionRegister;
  PREGISTER_EVENT_CALLBACK        RegisterEventCallback;
  PUNREGISTER_EVENT_CALLBACK      UnregisterEventCallback;
  PGET_DEVICE_INFORMATION         GetDeviceInformation;
  PGET_RESOURCE_INFORMATION       GetResourceInformation;
} HDAUDIO_BUS_INTERFACE_BDL, *PHDAUDIO_BUS_INTERFACE_BDL;
````


## -struct-fields




### -field Size

Specifies the size in bytes of the HDAUDIO_BUS_INTERFACE_BDL structure.


### -field Version

Specifies the version of the extended HD Audio DDI.


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


### -field AllocateContiguousDmaBuffer

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a> routine.


### -field SetupDmaEngineWithBdl

Function pointer to the <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a> routine.


### -field FreeContiguousDmaBuffer

Function pointer to the <a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a> routine.


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


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IOCTL uses this structure to provide interface information to a client that is querying the HD Audio bus driver for the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE structure.

The HDAUDIO_BUS_INTERFACE_BDL and HDAUDIO_BUS_INTERFACE structures are similar but have the following differences:
<ul>
<li>
HDAUDIO_BUS_INTERFACE_BDL has three members, <b>AllocateContiguousDmaBuffer</b>, <b>SetupDmaEngineWithBdl</b>, and <b>FreeContiguousDmaBuffer</b>, that are not present in HDAUDIO_BUS_INTERFACE.

</li>
<li>
HDAUDIO_BUS_INTERFACE has two members, <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> and <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a>, that are not present in HDAUDIO_BUS_INTERFACE_BDL.

</li>
</ul>For more information, see <a href="https://msdn.microsoft.com/e24071d3-9021-40c0-907a-91ada8a1306b">Differences Between the HD Audio DDI Versions</a>.

The names and definitions of the first five members (<b>Size</b>, <b>Version</b>, <b>Context</b>, <b>InterfaceReference</b>, and <b>InterfaceDereference</b>) are the same as in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure. The remaining members are specific to the extended HD Audio DDI and specify function pointers to the routines in the DDI. For more information, see <a href="https://msdn.microsoft.com/142eb2f0-6c6d-4441-8ad7-0875546c1ab2">Obtaining an HDAUDIO_BUS_INTERFACE_BDL DDI Object</a>.



## -see-also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>

<a href="..\hdaudio\nc-hdaudio-pget_wall_clock_register.md">GetWallClockRegister</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>

<a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a>

<a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a>

<a href="..\hdaudio\nc-hdaudio-ptransfer_codec_verbs.md">TransferCodecVerbs</a>

<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>

<a href="..\hdaudio\nc-hdaudio-pget_resource_information.md">GetResourceInformation</a>

<a href="..\hdaudio\nc-hdaudio-pfree_dma_engine.md">FreeDmaEngine</a>

<a href="..\hdaudio\nc-hdaudio-pget_link_position_register.md">GetLinkPositionRegister</a>

<a href="..\hdaudio\nc-hdaudio-punregister_event_callback.md">UnregisterEventCallback</a>

<a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a>

<a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_BUS_INTERFACE_BDL structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

