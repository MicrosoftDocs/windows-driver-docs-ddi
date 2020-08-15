---
UID: NC:hdaudio.PFREE_DMA_BUFFER
title: PFREE_DMA_BUFFER (hdaudio.h)
description: The FreeDmaBuffer routine frees a DMA buffer that was previously allocated by a call to AllocateDmaBuffer.The function pointer type for a FreeDmaBuffer routine is defined as follows.
old-location: audio\freedmabuffer.htm
tech.root: audio
ms.assetid: 658e32d2-40e2-4479-8212-df7140fe6b74
ms.date: 05/08/2018
keywords: ["PFREE_DMA_BUFFER callback function"]
ms.keywords: FreeDmaBuffer, FreeDmaBuffer callback function [Audio Devices], PFREE_DMA_BUFFER, PFREE_DMA_BUFFER callback, aud-prop2_22e95124-bf77-40d9-9ad7-4edc394818df.xml, audio.freedmabuffer, hdaudio/FreeDmaBuffer
f1_keywords:
 - "hdaudio/FreeDmaBuffer"
 - "FreeDmaBuffer"
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
- FreeDmaBuffer
targetos: Windows
req.typenames: 
---

# PFREE_DMA_BUFFER callback function


## -description


The <code>FreeDmaBuffer</code> routine frees a DMA buffer that was previously allocated by a call to <b>AllocateDmaBuffer</b>.

The function pointer type for a <code>FreeDmaBuffer</code> routine is defined as follows.


## -parameters




### -param _context 
[in]
Specifies the context value from the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a> or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> structure.


### -param Handle 
[in]
Handle identifying the DMA engine. This handle value was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>.


## -returns



<code>FreeDmaBuffer</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.

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
Indicates that the handle parameter value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the stream is not in the reset state or that no buffer is currently allocated for the DMA engine.

</td>
</tr>
</table>
 




## -remarks



The <code>FreeDmaBuffer</code> routine is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a> routine. These two routines are available only in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. This DDI does not include the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_contiguous_dma_buffer">AllocateContiguousDmaBuffer</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_contiguous_dma_buffer">FreeContiguousDmaBuffer</a> routines, which are never used in conjunction with <b>AllocateDmaBuffer</b> and <code>FreeDmaBuffer</code>. Unlike <b>SetupDmaEngineWithBdl</b>, which configures the DMA engine to use a previously allocated DMA buffer, <b>AllocateDmaBuffer</b> both allocates a DMA buffer and configures the DMA engine to use the buffer.

The routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:

<ul>
<li>
The client calls <code>FreeDmaBuffer</code> when no buffer is currently allocated for the DMA engine.

</li>
<li>
The stream is in a state other than reset.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a>
 

 

