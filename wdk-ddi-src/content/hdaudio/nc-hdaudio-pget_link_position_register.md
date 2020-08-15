---
UID: NC:hdaudio.PGET_LINK_POSITION_REGISTER
title: PGET_LINK_POSITION_REGISTER (hdaudio.h)
description: The GetLinkPositionRegister routine retrieves a pointer to a DMA engine's link position register.The function pointer type for a GetLinkPositionRegister routine is defined as follows.
old-location: audio\getlinkpositionregister.htm
tech.root: audio
ms.assetid: 8b8c7f61-c22a-421f-999f-291999bb243f
ms.date: 05/08/2018
keywords: ["PGET_LINK_POSITION_REGISTER callback function"]
ms.keywords: GetLinkPositionRegister, GetLinkPositionRegister callback function [Audio Devices], PGET_LINK_POSITION_REGISTER, PGET_LINK_POSITION_REGISTER callback, aud-prop2_715e978e-6396-479a-a953-6d17016306c4.xml, audio.getlinkpositionregister, hdaudio/GetLinkPositionRegister
f1_keywords:
 - "hdaudio/GetLinkPositionRegister"
 - "GetLinkPositionRegister"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- hdaudio.h
api_name:
- GetLinkPositionRegister
targetos: Windows
req.typenames: 
---

# PGET_LINK_POSITION_REGISTER callback function


## -description


The <code>GetLinkPositionRegister</code> routine retrieves a pointer to a DMA engine's link position register.

The function pointer type for a <code>GetLinkPositionRegister</code> routine is defined as follows.


## -parameters




### -param _context 
[in]
Specifies the context value from the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param Handle 
[in]
Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>.


### -param Position 
[out]
Retrieves a pointer to the link position register. This parameter points to a caller-allocated PULONG variable into which the routine writes a pointer to the register. The HD Audio bus driver maps the register to a system virtual address that is accessible to the function driver.


## -returns



<code>GetLinkPositionRegister</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows a possible return status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
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
</table>
 




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/wall-clock-and-link-position-registers">Wall Clock and Link Position Registers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>
 

 

