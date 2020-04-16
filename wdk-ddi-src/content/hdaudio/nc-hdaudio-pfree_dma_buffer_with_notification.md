---
UID: NC:hdaudio.PFREE_DMA_BUFFER_WITH_NOTIFICATION
title: PFREE_DMA_BUFFER_WITH_NOTIFICATION (hdaudio.h)
description: The FreeDmaBufferWithNotification routine frees a DMA buffer that was previously allocated by a call to AllocateDmaBufferWithNotification.The function pointer type for a FreeDmaBufferWithNotification routine is defined as follows.
old-location: audio\freedmabufferwithnotification.htm
tech.root: audio
ms.assetid: 98fc6201-d9b4-4c85-b624-011f360df068
ms.date: 05/08/2018
keywords: ["PFREE_DMA_BUFFER_WITH_NOTIFICATION callback function"]
ms.keywords: FreeDmaBufferWithNotification, FreeDmaBufferWithNotification callback function [Audio Devices], PFREE_DMA_BUFFER_WITH_NOTIFICATION, PFREE_DMA_BUFFER_WITH_NOTIFICATION callback, aud-prop2_065b7aad-f695-4076-9450-3311083ac17b.xml, audio.freedmabufferwithnotification, hdaudio/FreeDmaBufferWithNotification
f1_keywords:
 - "hdaudio/FreeDmaBufferWithNotification"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Hdaudio.h
api_name:
- FreeDmaBufferWithNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFREE_DMA_BUFFER_WITH_NOTIFICATION callback function


## -description


The <code>FreeDmaBufferWithNotification</code> routine frees a DMA buffer that was previously allocated by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer_with_notification">AllocateDmaBufferWithNotification</a>.

The function pointer type for a FreeDmaBufferWithNotification routine is defined as follows.


## -parameters




### -param _context [in]

Specifies the context value from the Context member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> structure.


### -param Handle [in]

Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>.


### -param BufferMdl [in]

A pointer to the buffer MDL. This value was obtained from a previous call to AllocateDmaBufferWithNotification.


### -param BufferSize [in]

The size of the buffer to be freed. This value was obtained from a previous call to AllocateDmaBufferWithNotification.


## -returns



<code>FreeDmaBufferWithNotification</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, <code>FreeDmaBufferWithNotification</code> returns an appropriate error code. The following table shows some of the possible return error codes.

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
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the stream is not in the reset state or that no buffer is currently allocated for the DMA engine.

</td>
</tr>
</table>
 




## -remarks



The <code>FreeDmaBufferWithNotification</code> routine is used together with the AllocateDmaBufferWithNotification routine. These two routines are available only in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI.

Callers of FreeDmaBufferWithNotification must be running at IRQL PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer_with_notification">AllocateDmaBufferWithNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>
 

 

