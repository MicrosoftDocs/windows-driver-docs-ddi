---
UID: NC:hdaudio.PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION
title: PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION (hdaudio.h)
description: The AllocateDmaBufferWithNotification routine allocates a data buffer in system memory for a DMA engine.The function pointer type for an AllocateDmaBufferWithNotification routine is defined as follows.
old-location: audio\allocatedmabufferwithnotification.htm
tech.root: audio
ms.assetid: c74b5969-35d4-45db-b631-31e00572107d
ms.date: 05/08/2018
keywords: ["PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION callback function"]
ms.keywords: AllocateDmaBufferWithNotification, AllocateDmaBufferWithNotification callback function [Audio Devices], PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION, PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION callback, aud-prop2_37aa129c-f389-402a-ba68-8dedb9ce6b6b.xml, audio.allocatedmabufferwithnotification, hdaudio/AllocateDmaBufferWithNotification
f1_keywords:
 - "hdaudio/AllocateDmaBufferWithNotification"
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Hdaudio.h
api_name:
- AllocateDmaBufferWithNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION callback function


## -description


The <code>AllocateDmaBufferWithNotification</code> routine allocates a data buffer in system memory for a DMA engine.

The function pointer type for an <code>AllocateDmaBufferWithNotification</code> routine is defined as follows.


## -parameters




### -param _context [in]

Specifies the context value from the Context member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> structure.


### -param Handle [in]

A handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>.


### -param NotificationCount [in]

Specifies the number of notifications that are needed, based on DMA progression through the audio buffer.  Currently, a value of 1 or 2 is supported.  When the value is 1, any registered notification events are signaled each time the cyclic audio buffer is completed and DMA wraps back to the beginning.  When the value is 2, any registered notification events are notified as DMA passes the midpoint of the audio buffer as well as at the end (or the wraparound point).


### -param RequestedBufferSize [in]

Specifies the requested buffer size, in bytes.


### -param *BufferMdl [out]

Retrieves the physical memory pages that contain the allocated buffer. This parameter points to a caller-allocated variable that is a pointer to a memory descriptor list (PMDL). This routine writes a pointer that describes the memory descriptor list buffer, to the PMDL variable.


### -param AllocatedBufferSize [out]

Retrieves the allocated buffer size, in bytes. This parameter points to a caller-allocated SIZE_T variable into which the routine writes the size of the allocated buffer.


### -param OffsetFromFirstPage


### -param StreamId [out]

Retrieves the stream identifier. This parameter points to a caller-allocated UCHAR variable into which the routine writes the stream identifier that the routine assigns to the stream.


### -param FifoSize [out]

Retrieves the DMA engine's FIFO size, in bytes. This parameter points to a caller-allocated ULONG variable into which the routine writes the FIFO size.


## -returns



The <code>AllocateDmaBufferWithNotification</code> routine returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return error codes.

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
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the buffer allocation has failed.

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is incorrect (bad pointer).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the hardware programming timed out. If this occurs, the hardware might be in a compromised state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the stream is not in the reset state or that a buffer is already allocated for the DMA engine and has not yet been freed.

</td>
</tr>
</table>
 




## -remarks



The <code>AllocateDmaBufferWithNotification</code> routine is used together with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer_with_notification">FreeDmaBufferWithNotification</a> routine. These two routines are available only in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI. Unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a>, which configures the DMA engine to use a previously allocated DMA buffer, <code>AllocateDmaBufferWithNotification</code> allocates a DMA buffer and also configures the DMA engine to use the buffer.

If the DMA engine cannot use a buffer of the size that is requested in parameter <i>requestedBufferSize</i>, the routine allocates a buffer that is as close as possible to the requested size.

The function driver for an audio or modem codec is responsible for programming the codec to manage the data transfers and to recognize the stream identifier.

<code>AllocateDmaBufferWithNotification</code> outputs an MDL that lists the physical memory pages that contain the buffer. The buffer base address coincides with the start of the first physical page in the list.

During the lifetime of a DMA engine handle, <code>AllocateDmaBufferWithNotification</code> can be called successively to allocate new DMA buffers. However, before calling <code>AllocateDmaBufferWithNotification</code>, any previously allocated DMA buffer must first be freed by calling FreeDmaBufferWithNotification.

During calls to <code>AllocateDmaBufferWithNotification</code> and <b>FreeDmaBufferWithNotification</b>, the DMA engine must be in the reset stream state. The DMA engine is in the reset stream state immediately following the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>. To change the DMA engine to the run state, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a>.

The FIFO size is the maximum number of bytes that the DMA engine can hold in its internal buffer. Depending on the hardware implementation, a DMA engine's FIFO size can either be static or vary dynamically with changes in the stream format. For more information about the FIFO size, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=42508">Intel High Definition Audio Specification</a>.

In Windows Vista and later versions of Windows, a WaveRT miniport driver calls this routine when it receives the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer-with-notification">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a> property request. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer-with-notification">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a>
 

 

