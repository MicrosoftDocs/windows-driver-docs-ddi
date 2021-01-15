---
UID: NC:hdaudio.PCHANGE_BANDWIDTH_ALLOCATION
title: PCHANGE_BANDWIDTH_ALLOCATION (hdaudio.h)
description: The ChangeBandwidthAllocation routine changes a DMA engine's bandwidth allocation on the HD Audio Link.The function pointer type for a ChangeBandwidthAllocation routine is defined as follows.
old-location: audio\changebandwidthallocation.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PCHANGE_BANDWIDTH_ALLOCATION callback function"]
ms.keywords: ChangeBandwidthAllocation, ChangeBandwidthAllocation callback function [Audio Devices], PCHANGE_BANDWIDTH_ALLOCATION, PCHANGE_BANDWIDTH_ALLOCATION callback, aud-prop2_3d85fecb-4617-404b-951b-7457f9e650cc.xml, audio.changebandwidthallocation, hdaudio/ChangeBandwidthAllocation
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PCHANGE_BANDWIDTH_ALLOCATION
 - hdaudio/PCHANGE_BANDWIDTH_ALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - hdaudio.h
api_name:
 - PCHANGE_BANDWIDTH_ALLOCATION
---

# PCHANGE_BANDWIDTH_ALLOCATION callback function


## -description

The <code>ChangeBandwidthAllocation</code> routine changes a DMA engine's bandwidth allocation on the HD Audio Link.

The function pointer type for a <code>ChangeBandwidthAllocation</code> routine is defined as follows.

## -parameters

### -param _context 

[in]
Specifies the context value from the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

### -param Handle 

[in]
Handle identifying the DMA engine. This handle value was obtained from a previous call to <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>.

### -param StreamFormat 

[in]
Specifies the requested stream format. This parameter points to a caller-allocated structure of type <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_stream_format">HDAUDIO_STREAM_FORMAT</a> that specifies a data format for the stream.

### -param ConverterFormat 

[out]
Retrieves the converter format. This parameter points to a caller-allocated structure of type <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_converter_format">HDAUDIO_CONVERTER_FORMAT</a> into which the routine writes the encoded format. For more information, see the following Remarks section.

## -returns

<code>ChangeBandwidthAllocation</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the caller is running at an IRQL that is too high.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the <i>handle</i> parameter value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is not correct (bad pointer or invalid stream format).

</td>
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
Indicates that insufficient bandwidth is available to satisfy the request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the stream is not in the reset state or that a buffer is still allocated for the DMA engine.

</td>
</tr>
</table>

## -remarks

The caller obtains an initial bandwidth allocation for a DMA engine by calling <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>. Thereafter, the caller can change the bandwidth allocation by calling <code>ChangeBandwidthAllocation</code>.

Through the <i>converterFormat</i> parameter, the routine outputs a stream descriptor value that the caller can use to program the input or output converters. The routine encodes the information from the <i>streamFormat</i> parameter into a 16-bit integer. For more information, see <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_converter_format">HDAUDIO_CONVERTER_FORMAT</a>.

This routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:

<ul>
<li>
Any previously allocated DMA buffer has not been freed (by calling <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a> or <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_contiguous_dma_buffer">FreeContiguousDmaBuffer</a>).

</li>
<li>
The stream is in a state other than reset.

</li>
</ul>
If the <code>ChangeBandwidthAllocation</code> call fails, the existing bandwidth reservation remains in effect. The bandwidth allocation changes only if the call succeeds.

In Windows Vista and later, a wave miniport driver calls this routine during execution of its <b>SetFormat</b> method (after calling one of the Allocate<i>Xxx</i>DmaEngine routines in the HD Audio DDI). For more information, see <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepcistream-setformat">IMiniportWavePciStream::SetFormat</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_contiguous_dma_buffer">FreeContiguousDmaBuffer</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_converter_format">HDAUDIO_CONVERTER_FORMAT</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_stream_format">HDAUDIO_STREAM_FORMAT</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepcistream-setformat">IMiniportWavePciStream::SetFormat</a>

