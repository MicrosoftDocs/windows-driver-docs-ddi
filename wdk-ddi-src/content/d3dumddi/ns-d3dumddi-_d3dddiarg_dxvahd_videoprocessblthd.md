---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
title: _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD (d3dumddi.h)
description: The D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure describes a Microsoft DirectX Video Acceleration (VA) video processing high definition operation to perform.
old-location: display\d3dddiarg_dxvahd_videoprocessblthd.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure"]
ms.keywords: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure [Display Devices], UMDisplayDriver_param_Structs_8a72018a-706f-4c26-adca-109365e03ff1.xml, _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, d3dumddi/D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, display.d3dddiarg_dxvahd_videoprocessblthd
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD is supported beginning with the Windows 7 operating system.
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
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
f1_keywords:
 - _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
 - d3dumddi/_D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
 - D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
 - d3dumddi/D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
 - D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
---

# _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure


## -description

The D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure describes a Microsoft DirectX Video Acceleration (VA) video processing high definition operation to perform.

## -struct-fields

### -field hVideoProcessor

[in] A handle to the DirectX VA video processing device. The user-mode display driver returns this handle in a call to its <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor">CreateVideoProcessor</a> function.

### -field OutputSurface

[in] A <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_surface">DXVAHDDDI_SURFACE</a> structure that describes the output surface to which the video processor composes.

### -field OutputFrame

[in] A zero-based frame number of the composed output frames.

### -field StreamCount

[in] The number of streams to process. This number must be less than the number that the driver set in the <b>MaxStreamStates</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure.

### -field pStreams

[in] An array of <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a> structures that describe the input streams to process.

## -remarks

The output surface that the <b>OutputSurface</b> member specifies, which must be one of the following surface types:

<ul>
<li>
A video surface that is created with the DXVAHD_SURFACE_TYPE_VIDEO_OUTPUT type. 

</li>
<li>
A render target surface or a surface that is created with D3DUSAGE_RENDERTARGET usage. 

</li>
<li>
A swap chain. 

</li>
<li>
A swap chain with overlay swap effect. 

</li>
</ul>
If the frame that the <b>OutputFrame</b> member specifies remains unchanged at the next process time, the driver determines that the frame is unchanged (for example, paused) in the entire video processing and composition. Therefore, the driver can use cached data to optimize the frame.

The driver also uses the frame that the <b>OutputFrame</b> member specifies for tagging the command, which the driver submits to the graphics processing unit (GPU).

Input streams are indexed from zero to less than the number that the driver sets in the <b>MaxStreamStates</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure. Each stream has its own stream states associated with the stream index number. The driver processes each stream from zero index and blends on the destination surface one after another. For example, if a video stream is at index zero and a graphics stream is at index one, the driver blends the video stream on the background color and then blends the graphics stream over them.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor">CreateVideoProcessor</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_surface">DXVAHDDDI_SURFACE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>

