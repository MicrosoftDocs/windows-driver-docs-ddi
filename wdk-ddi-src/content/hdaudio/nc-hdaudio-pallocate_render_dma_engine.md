---
UID: NC:hdaudio.PALLOCATE_RENDER_DMA_ENGINE
title: PALLOCATE_RENDER_DMA_ENGINE (hdaudio.h)
description: The AllocateRenderDmaEngine routine allocates a DMA engine for a render stream.The function pointer type for an AllocateRenderDmaEngine routine is defined as follows.
old-location: audio\allocaterenderdmaengine.htm
tech.root: audio
ms.assetid: fb2a64ca-7e8e-4352-86c6-b9500e535c75
ms.date: 05/08/2018
ms.keywords: AllocateRenderDmaEngine, AllocateRenderDmaEngine callback function [Audio Devices], PALLOCATE_RENDER_DMA_ENGINE, PALLOCATE_RENDER_DMA_ENGINE callback, aud-prop2_69a03ff9-5eda-4f39-85cf-e4af523214e1.xml, audio.allocaterenderdmaengine, hdaudio/AllocateRenderDmaEngine
ms.topic: callback
f1_keywords:
 - "hdaudio/AllocateRenderDmaEngine"
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- hdaudio.h
api_name:
- AllocateRenderDmaEngine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PALLOCATE_RENDER_DMA_ENGINE callback function


## -description


The <code>AllocateRenderDmaEngine</code> routine allocates a DMA engine for a render stream.

The function pointer type for an <code>AllocateRenderDmaEngine</code> routine is defined as follows.


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a><u>,</u><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structures.


### -param StreamFormat [in]

Specifies the requested stream format. This parameter points to a caller-allocated structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_stream_format">HDAUDIO_STREAM_FORMAT</a> that specifies a data format for the stream.


### -param Stripe [in]

Specifies whether to enable striping. If <b>TRUE</b>, the routine enables striping in the DMA transfers. If <b>FALSE</b>, striping is disabled.


### -param Handle [out]

Retrieves the handle to the DMA engine. This parameter points to a caller-allocated HANDLE variable into which the routine writes a handle that identifies the DMA engine.


### -param ConverterFormat [out]

Retrieves the converter format. This parameter points to a caller-allocated structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_converter_format">HDAUDIO_CONVERTER_FORMAT</a> into which the routine writes the encoded format.


## -returns



<code>AllocateRenderDmaEngine</code> returns STATUS_SUCCESS if the call succeeds in reserving a DMA engine. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the DMA engine is unable to allocate sufficient internal FIFO storage to support the requested stream format.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that either no DMA engine is available or the request exceeds the available bandwidth resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is incorrect (invalid parameter value or bad pointer).

</td>
</tr>
</table>
 




## -remarks



This routine allocates a render DMA engine and specifies the data format for the stream. If successful, the routine outputs a handle that the caller subsequently uses to identify the DMA engine.

The <code>AllocateRenderDmaEngine</code> routine reserves hardware resources (the DMA engine) but does not configure the DMA hardware. After calling this routine to reserve a DMA engine, a function driver must assign a DMA buffer to the DMA engine and configure the engine to use the buffer:

<ul>
<li>
If using the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI, the function driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a> routine to have the HD Audio bus driver allocate a data buffer for DMA transfers and set up the DMA engine to use the buffer.

</li>
<li>
If using the HDAUDIO_BUS_INTERFACE_BDL version of the DDI, the function driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pallocate_contiguous_dma_buffer">AllocateContiguousDmaBuffer</a> to allocate the DMA buffer and calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a> routine to set up the DMA engine to use the buffer.

</li>
</ul>
The <i>streamFormat</i> parameter specifies the data format for the capture stream. Following the call to <code>AllocateRenderDmaEngine</code>, the stream's format can be changed by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pchange_bandwidth_allocation">ChangeBandwidthAllocation</a>.

The <i>stripe</i> parameter specifies whether the DMA engine is to use striping to speed up data transfers. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/striping">Striping</a>.

Through the handle parameter, the routine outputs a handle that the caller uses to identify the allocated DMA engine in subsequent calls to <b>AllocateDmaBuffer</b>, <b>ChangeBandwidthAllocation</b>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a>, <b>SetupDmaEngineWithBdl</b>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a>. The function driver frees the handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pfree_dma_engine">FreeDmaEngine</a>.

Through the <i>converterFormat</i> parameter, the routine outputs a stream descriptor value that the caller can use to program the output converters. The routine encodes the information from the <i>streamFormat</i> parameter into a 16-bit integer. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_converter_format">HDAUDIO_CONVERTER_FORMAT</a>.

Immediately following a successful call to <code>AllocateRenderDmaEngine</code>, the DMA engine is in the reset stream state. Before calling <b>SetDmaEngineState</b> to change the DMA engine to the running, paused, or stopped state, the client must first allocate a DMA buffer for the engine.

A WDM audio driver calls <code>AllocateRenderDmaEngine</code> at pin-creation time during execution of its <b>NewStream</b> method (for example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportwavepci-newstream">IMiniportWavePci::NewStream</a>).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pchange_bandwidth_allocation">ChangeBandwidthAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pfree_dma_engine">FreeDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_converter_format">HDAUDIO_CONVERTER_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/ns-hdaudio-_hdaudio_stream_format">HDAUDIO_STREAM_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportwavepci-newstream">IMiniportWavePci::NewStream</a>
 

 

