---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_DATA
title: _DXVAHDDDI_STREAM_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_DATA structure describes an input stream that is processed.
old-location: display\dxvahdddi_stream_data.htm
tech.root: display
ms.assetid: 3b8fc849-8794-4dab-af28-a1c0dfd859d3
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_d7fc6fd4-0b17-49b3-bb42-0e0c8f3cc124.xml, DXVAHDDDI_STREAM_DATA, DXVAHDDDI_STREAM_DATA structure [Display Devices], _DXVAHDDDI_STREAM_DATA, d3dumddi/DXVAHDDDI_STREAM_DATA, display.dxvahdddi_stream_data
ms.topic: struct
f1_keywords:
 - "d3dumddi/DXVAHDDDI_STREAM_DATA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_DATA is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- DXVAHDDDI_STREAM_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_DATA
---

# _DXVAHDDDI_STREAM_DATA structure


## -description


The DXVAHDDDI_STREAM_DATA structure describes an input stream that is processed. 


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the input stream is enabled. The number of input streams that the runtime enables must not be more than the number, which the driver sets in the <b>MaxStreamStates</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure.  


### -field OutputIndex

[in] A zero-based cyclic frame index number of the output frames that are composed. 


### -field InputFrameOrField

[in] A zero-based frame number of the input frames or fields that are processed.


### -field PastFrames

[in] The number of past reference frames. This number must not be more than the number that the driver sets in the <b>PastFrames</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_vpcaps">DXVAHDDDI_VPCAPS</a> structure.  


### -field FutureFrames

[in] The number of future reference frames. This number must not be more than the number that the driver sets in the <b>FutureFrames</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_vpcaps">DXVAHDDDI_VPCAPS</a> structure.  


### -field pPastSurfaces

[in] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_surface">DXVAHDDDI_SURFACE</a> structures that describe the past reference surfaces. 


### -field InputSurface

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_surface">DXVAHDDDI_SURFACE</a> structure that describes the input surface. 


### -field pFutureSurfaces

[in] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_surface">DXVAHDDDI_SURFACE</a> structures that describe the future reference surfaces. 


## -remarks



The driver must allocate the surfaces that the <b>pPastSurfaces</b>, <b>InputSurface</b>, and <b>pFutureSurfaces</b> members specify in the pool type, which the driver sets in the <b>InputPool</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure, and with one of the following surface types; otherwise, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_videoprocessblthd">VideoProcessBltHD</a> function returns an error.

<ul>
<li>
A video surface that is created with the DXVAHD_SURFACE_TYPE_VIDEO_INPUT or DXVAHD_SURFACE_TYPE_VIDEO_INPUT_PRIVATE type. 

</li>
<li>
A decode render target surface that is created with the DXVA2_VideoDecodeRenderTarget type. 

</li>
<li>
An off-screen plain surface. 

</li>
</ul>
The <b>OutputIndex</b> member is a zero-based cyclic number that indicates the frame index number of the output. The driver uses this output-index information to perform the video processing in a certain pattern or cycle, especially when the driver performs deinterlacing, frame-rate conversion, and inverse telecine. For example, with the following output-index pattern, the driver performs the indicated video processing:

<ul>
<li>
Progressive format at normal and half rate:  

OutputIndex = 0, 0,...

</li>
<li>
Progressive format at 2/1 custom rate (double frame-rate conversion, OutputFrames=2):  

OutputIndex = 0, 1, 0, 1,...

</li>
<li>
Interlaced format at normal rate:  

OutputIndex = 0, 1, 0, 1,... (0: first field, 1: second field)

</li>
<li>
Interlaced format at half rate:  

OutputIndex = 0, 0,... (for example, first and second fields are blended to one frame)

</li>
<li>
Interlaced at 4/5 custom rate (3:2 inverse telecine, OutputFrames=4):  

OutputIndex = 0, 1, 2, 3, 0, 1, 2, 3,... (0:A, 1:B, 2:C, 3:D film frame) 

</li>
</ul>
The <b>InputFrameOrField</b> member is a zero-based number that indicates the frame or the field number of the input surface. For example, with the following input-frame-or-field number, the driver can perform the indicated video processing: 

<ul>
<li>
Progressive format and interlaced format at normal rate:  

InputFrameOrField = 0, 1, 2,...

</li>
<li>
Progressive format and interlaced format at half rate:  

InputFrameOrField = 0, 2, 4,...

</li>
<li>
Interlaced format at 4/5 custom rate (3:2 inverse telecine, OutputFrames=4 and InputFrameOrField=10):  

InputFrameOrField = 0, 0, 0, 0, 10, 10, 10, 10, 20, 20, 20, 20,...

</li>
<li>
Interlaced format at 4/15 custom rate (8:7 inverse telecine, OutputFrames=2 and InputFrameOrField=15):  

InputFrameOrField = 0, 0, 15, 15, 30, 30,...

</li>
</ul>
The application should cause both the <b>OutputIndex</b> and <b>InputFrameOrField</b> members to reset when either the frame format or the output rate is changed so that the driver can reset its internal processing state. For more information about changing frame format or output rate, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_frame_format_data">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a>.

However, if the driver switches between normal and half rate (values from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-_dxvahdddi_output_rate">DXVAHDDDI_OUTPUT_RATE</a> enumeration), the driver should not require the reset. 

If both the <b>OutputIndex</b> and <b>InputFrameOrField</b> members remain unchanged at the next process time, the driver determines that the frame is unchanged (for example, paused) in the stream processing. Therefore, the driver can optimize the frame by using cached data.

The driver should fallback to a less intensive video processing method as less reference frames are provided. The driver should fallback to Bob de-interlacing when no reference samples are provided.

An application can provide less past and future reference frames than the reference frames that the driver requests. For example, an application can provide less reference frames in the following conditions:

<ul>
<li>
At the beginning or at the end of the frame sequence. 

</li>
<li>
Transition between progressive and interlaced. 

</li>
<li>
Normal or half rate progressive stream. 

</li>
<li>
Sub-video streams that do not require high quality de-interlacing. 

</li>
<li>
While throttling the reference frames to recover from frame drops and to keep up the frame rate. 

</li>
<li>
Frame dropping from the input (for example, frame drops in the decoder). 

</li>
</ul>
Both the past and the future reference frames are provided in the  <b>pPastSurfaces</b> and <b>pFutureSurfaces</b> array members in temporal order from older to newer frames continuously. For example, the order of the elements in the arrays are as shown in the following example:

<b>pPastSurfaces</b> [] = {..., T-3, T-2, T-1}

<b>InputSurface</b> = T

<b>pFutureSurfaces</b> [] = {T+1, T+2, T+3,...}

The input and reference frames change location from the future location to the past location through the current location as the <b>OutputIndex</b> and <b>InputFrameOrField</b> members increment. For example, the input surface changes as the <b>OutputIndex</b> and <b>InputFrameOrField</b> increment when the driver performs the following video processing:

<ul>
<li>
Progressive format at normal rate:  

OutputIndex = 0, 0, 0,... 

InputFrameOrField = 0, 1, 2,...

InputSurface = T, T+1, T+2,...

</li>
<li>
Interlaced format at normal rate:  

OutputIndex = 0, 1, 0, 1, 0, 1,... 

InputFrameOrField = 0, 1, 2, 3, 4, 5,...

InputSurface = T, T, T+1, T+1, T+2, T+2,...

</li>
<li>
Interlaced format at half rate:  

OutputIndex = 0, 0, 0,... 

InputFrameOrField = 0, 2, 4,...

InputSurface = T, T+1, T+2,...

</li>
<li>
Interlaced format at 4/5 custom rate (3:2 inverse telecine, OutputFrames=4 and InputFrameOrField=10):  

OutputIndex = 0, 1, 2, 3, 0, 1, 2, 3, 0, 1, 2, 3,... 

InputFrameOrField = 0, 0, 0, 0, 10, 10, 10, 10, 20, 20, 20, 20,...

InputSurface = T, T, T, T, T+5, T+5, T+5, T+5, T+10, T+10, T+10, T+10,... 

</li>
<li>
Interlaced format at 4/15 custom rate (8:7 inverse telecine, OutputFrames=2 and InputFrameOrField=15):  

OutputIndex = 0, 1, 0, 1, 0, 1,... 

InputFrameOrField = 0, 0, 15, 15, 30, 30,...

InputSurface = T, T, T+7, T+7, T+15, T+15,...  (note that T+7 frame contains 15th field) 

</li>
</ul>
The following pseudo-code example shows the interaction between the application (APP) and the driver (DRV) while performing Inverse Telecine (IVTC) on 3:2 pull-down, 30 frames (60 fields) per second interlaced content:

```cpp
-[60i -> 60p]
DRV: VPGuid[0] requests 1 past and 2 future reference frames.
APP: Creates VPGuid[0] video processor and set output rate to normal.
APP: Decodes frame 0(A0:A1), 1(A0:B1), 2(B0:C1), 3(C0:C1), 4(D0:D1), ...
    :
-APP: VPBltHD(frame x, 0, 1, 2), InputFrameOrField=0, OutputIndex=0
DRV: Bob [0(A0)+0(A1)] = A'
-APP: VPBltHD(frame x, 0, 1, 2), InputFrameOrField=1, OutputIndex=1
DRV: Weave [0(A1)+1(A0)] = A
-APP: VPBltHD(frame 0, 1, 2, 3), InputFrameOrField=2, OutputIndex=0
DRV: Weave [1(A0)+0(A1)] = A
-APP: VPBltHD(frame 0, 1, 2, 3), InputFrameOrField=3, OutputIndex=1
DRV: Weave [1(B1)+2(B0)] = B
-APP: VPBltHD(frame 1, 2, 3, 4), InputFrameOrField=4, OutputIndex=0
DRV: Weave [2(B0)+1(B1)] = B
-APP: VPBltHD(frame 1, 2, 3, 4), InputFrameOrField=5, OutputIndex=1
DRV: Weave [2(C1)+3(C0)] = C
-APP: VPBltHD(frame 2, 3, 4, 5), InputFrameOrField=6, OutputIndex=0
DRV: Weave [3(C0)+3(C1)] = C
-APP: VPBltHD(frame 2, 3, 4, 5), InputFrameOrField=7, OutputIndex=1
DRV: Weave [3(C1)+3(C0)] = C
-APP: VPBltHD(frame 3, 4, 5, 6), InputFrameOrField=8, OutputIndex=0
DRV: Weave [4(D0)+4(D1)] = D
-APP: VPBltHD(frame 3, 4, 5, 6), InputFrameOrField=9, OutputIndex=1
DRV: Weave [4(D1)+4(D0)] = D
    :
-[60i -> 24p]
DRV: VPGuid[1] requests 4 future reference frames.
DRV: Exports CustomRate=4/5, OutputFrames=4, InputInterlaced=TRUE, InputFramesOrFields=10.
APP: Creates VPGuid[1] video processor and set output rate to 4/5 custom rate.
-APP: VPBltHD(frame 0, 1, 2, 3, 4), InputFrameOrField=0, OutputIndex=0
DRV: Bob [0(A0)+0(A1)] = A' (playback or speed mode) or Weave [0(A0)+0(A1)] = A (quality mode)
-APP: VPBltHD(frame 0, 1, 2, 3, 4), InputFrameOrField=0, OutputIndex=1
DRV: Weave [1(B1)+2(B0)] = B
-APP: VPBltHD(frame 0, 1, 2, 3, 4), InputFrameOrField=0, OutputIndex=2
DRV: Weave [3(C0)+3(C1)] = C
-APP: VPBltHD(frame 0, 1, 2, 3, 4), InputFrameOrField=0, OutputIndex=3
DRV: Weave [4(D0)+4(D1)] = D
-APP: VPBltHD(frame 5, 6, 7, 8, 9), InputFrameOrField=10, OutputIndex=0
DRV: Weave [0(A0)+0(A1)] = A
    :
```


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-_dxvahdddi_output_rate">DXVAHDDDI_OUTPUT_RATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_frame_format_data">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_surface">DXVAHDDDI_SURFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_vpcaps">DXVAHDDDI_VPCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_videoprocessblthd">VideoProcessBltHD</a>
 

 

