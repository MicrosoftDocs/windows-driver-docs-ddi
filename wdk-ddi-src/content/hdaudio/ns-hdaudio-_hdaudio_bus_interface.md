---
UID: NS:hdaudio._HDAUDIO_BUS_INTERFACE
title: _HDAUDIO_BUS_INTERFACE (hdaudio.h)
description: The HDAUDIO_BUS_INTERFACE structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE_BDL structure.
old-location: audio\hdaudio_bus_interface.htm
tech.root: audio
ms.assetid: 6b3bc5ce-05d2-45e0-91d8-6bb34e58777f
ms.date: 05/08/2018
ms.keywords: "*PHDAUDIO_BUS_INTERFACE, HDAUDIO_BUS_INTERFACE, HDAUDIO_BUS_INTERFACE structure [Audio Devices], PHDAUDIO_BUS_INTERFACE, PHDAUDIO_BUS_INTERFACE structure pointer [Audio Devices], _HDAUDIO_BUS_INTERFACE, aud-prop2_4d39bbd4-8c0b-4f2c-98a7-618d891593c1.xml, audio.hdaudio_bus_interface, hdaudio/HDAUDIO_BUS_INTERFACE, hdaudio/PHDAUDIO_BUS_INTERFACE"
ms.topic: struct
f1_keywords:
 - "hdaudio/HDAUDIO_BUS_INTERFACE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hdaudio.h
api_name:
- HDAUDIO_BUS_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: HDAUDIO_BUS_INTERFACE, *PHDAUDIO_BUS_INTERFACE
---

# _HDAUDIO_BUS_INTERFACE structure


## -description


The HDAUDIO_BUS_INTERFACE structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. Another variant of this DDI is specified by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


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

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">TransferCodecVerbs</a> routine.


### -field AllocateCaptureDmaEngine

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> routine.


### -field AllocateRenderDmaEngine

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a> routine.


### -field ChangeBandwidthAllocation

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pchange_bandwidth_allocation">ChangeBandwidthAllocation</a> routine.


### -field AllocateDmaBuffer

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a> routine.


### -field FreeDmaBuffer

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a> routine.


### -field FreeDmaEngine

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_engine">FreeDmaEngine</a> routine.


### -field SetDmaEngineState

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a> routine.


### -field GetWallClockRegister

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_wall_clock_register">GetWallClockRegister</a> routine.


### -field GetLinkPositionRegister

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_link_position_register">GetLinkPositionRegister</a> routine.


### -field RegisterEventCallback

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_event_callback">RegisterEventCallback</a> routine.


### -field UnregisterEventCallback

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_event_callback">UnregisterEventCallback</a> routine.


### -field GetDeviceInformation

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_device_information">GetDeviceInformation</a> routine.


### -field GetResourceInformation

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_resource_information">GetResourceInformation</a> routine.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> IOCTL uses this structure to provide interface information to a client that is querying the HD Audio bus driver for the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE_BDL structure.

The HDAUDIO_BUS_INTERFACE and HDAUDIO_BUS_INTERFACE_BDL structures are similar but have the following differences:

<ul>
<li>
HDAUDIO_BUS_INTERFACE has two members, <b>AllocateDmaBuffer</b> and <b>FreeDmaBuffer</b>, that are not present in HDAUDIO_BUS_INTERFACE_BDL.

</li>
<li>
HDAUDIO_BUS_INTERFACE_BDL has three members, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_contiguous_dma_buffer">AllocateContiguousDmaBuffer</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_contiguous_dma_buffer">FreeContiguousDmaBuffer</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a>, that are not present in HDAUDIO_BUS_INTERFACE.

</li>
</ul>
For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/differences-between-the-hd-audio-ddi-versions">Differences Between the HD Audio DDI Versions</a>.

The names and definitions of the first five members (<b>Size</b>, <b>Version</b>, <b>Context</b>, <b>InterfaceReference</b>, and <b>InterfaceDereference</b>) are the same as in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure. The remaining members are specific to the baseline HD Audio DDI and specify function pointers to the routines in the DDI. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/obtaining-an-hdaudio-bus-interface-ddi-object">Obtaining an HDAUDIO_BUS_INTERFACE DDI Object</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pchange_bandwidth_allocation">ChangeBandwidthAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_engine">FreeDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_device_information">GetDeviceInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_link_position_register">GetLinkPositionRegister</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_resource_information">GetResourceInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_wall_clock_register">GetWallClockRegister</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_event_callback">RegisterEventCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">TransferCodecVerbs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_event_callback">UnregisterEventCallback</a>
 

 

