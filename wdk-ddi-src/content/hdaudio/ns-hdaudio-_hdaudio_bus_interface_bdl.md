---
UID: NS:hdaudio._HDAUDIO_BUS_INTERFACE_BDL
title: _HDAUDIO_BUS_INTERFACE_BDL (hdaudio.h)
description: The HDAUDIO_BUS_INTERFACE_BDL structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE structure.
old-location: audio\hdaudio_bus_interface_bdl.htm
tech.root: audio
ms.assetid: 64523c09-35dd-45df-beed-ce8afb740f5d
ms.date: 05/08/2018
keywords: ["_HDAUDIO_BUS_INTERFACE_BDL structure"]
ms.keywords: "*PHDAUDIO_BUS_INTERFACE_BDL, HDAUDIO_BUS_INTERFACE_BDL, HDAUDIO_BUS_INTERFACE_BDL structure [Audio Devices], PHDAUDIO_BUS_INTERFACE_BDL, PHDAUDIO_BUS_INTERFACE_BDL structure pointer [Audio Devices], _HDAUDIO_BUS_INTERFACE_BDL, aud-prop2_f9b041b3-76fd-4176-9fc8-32eeda46cc32.xml, audio.hdaudio_bus_interface_bdl, hdaudio/HDAUDIO_BUS_INTERFACE_BDL, hdaudio/PHDAUDIO_BUS_INTERFACE_BDL"
f1_keywords:
 - "hdaudio/HDAUDIO_BUS_INTERFACE_BDL"
 - "HDAUDIO_BUS_INTERFACE_BDL"
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
- HDAUDIO_BUS_INTERFACE_BDL
targetos: Windows
req.typenames: HDAUDIO_BUS_INTERFACE_BDL, *PHDAUDIO_BUS_INTERFACE_BDL
---

# _HDAUDIO_BUS_INTERFACE_BDL structure


## -description


The HDAUDIO_BUS_INTERFACE_BDL structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. Another variant of this DDI is specified by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a> structure.


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

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">TransferCodecVerbs</a> routine.


### -field AllocateCaptureDmaEngine

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> routine.


### -field AllocateRenderDmaEngine

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a> routine.


### -field ChangeBandwidthAllocation

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pchange_bandwidth_allocation">ChangeBandwidthAllocation</a> routine.


### -field AllocateContiguousDmaBuffer

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_contiguous_dma_buffer">AllocateContiguousDmaBuffer</a> routine.


### -field SetupDmaEngineWithBdl

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a> routine.


### -field FreeContiguousDmaBuffer

Function pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_contiguous_dma_buffer">FreeContiguousDmaBuffer</a> routine.


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



The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> IOCTL uses this structure to provide interface information to a client that is querying the HD Audio bus driver for the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE structure.

The HDAUDIO_BUS_INTERFACE_BDL and HDAUDIO_BUS_INTERFACE structures are similar but have the following differences:

<ul>
<li>
HDAUDIO_BUS_INTERFACE_BDL has three members, <b>AllocateContiguousDmaBuffer</b>, <b>SetupDmaEngineWithBdl</b>, and <b>FreeContiguousDmaBuffer</b>, that are not present in HDAUDIO_BUS_INTERFACE.

</li>
<li>
HDAUDIO_BUS_INTERFACE has two members, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a>, that are not present in HDAUDIO_BUS_INTERFACE_BDL.

</li>
</ul>
For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/differences-between-the-hd-audio-ddi-versions">Differences Between the HD Audio DDI Versions</a>.

The names and definitions of the first five members (<b>Size</b>, <b>Version</b>, <b>Context</b>, <b>InterfaceReference</b>, and <b>InterfaceDereference</b>) are the same as in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure. The remaining members are specific to the extended HD Audio DDI and specify function pointers to the routines in the DDI. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/obtaining-an-hdaudio-bus-interface-bdl-ddi-object">Obtaining an HDAUDIO_BUS_INTERFACE_BDL DDI Object</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_contiguous_dma_buffer">AllocateContiguousDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pchange_bandwidth_allocation">ChangeBandwidthAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_contiguous_dma_buffer">FreeContiguousDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_engine">FreeDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_link_position_register">GetLinkPositionRegister</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_resource_information">GetResourceInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_wall_clock_register">GetWallClockRegister</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_event_callback">RegisterEventCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">TransferCodecVerbs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_event_callback">UnregisterEventCallback</a>
 

 

