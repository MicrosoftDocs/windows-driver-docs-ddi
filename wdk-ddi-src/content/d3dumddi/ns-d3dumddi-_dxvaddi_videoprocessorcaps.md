---
UID: NS:d3dumddi._DXVADDI_VIDEOPROCESSORCAPS
title: _DXVADDI_VIDEOPROCESSORCAPS (d3dumddi.h)
description: The DXVADDI_VIDEOPROCESSORCAPS structure describes the video processing capabilities of a specific deinterlace mode.
old-location: display\dxvaddi_videoprocessorcaps.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVADDI_VIDEOPROCESSORCAPS structure"]
ms.keywords: DXVA2_Structs_dc28e351-d197-4440-a3fd-dc3a49e35230.xml, DXVADDI_VIDEOPROCESSORCAPS, DXVADDI_VIDEOPROCESSORCAPS structure [Display Devices], _DXVADDI_VIDEOPROCESSORCAPS, d3dumddi/DXVADDI_VIDEOPROCESSORCAPS, display.dxvaddi_videoprocessorcaps
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXVADDI_VIDEOPROCESSORCAPS
f1_keywords:
 - _DXVADDI_VIDEOPROCESSORCAPS
 - d3dumddi/_DXVADDI_VIDEOPROCESSORCAPS
 - DXVADDI_VIDEOPROCESSORCAPS
 - d3dumddi/DXVADDI_VIDEOPROCESSORCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVADDI_VIDEOPROCESSORCAPS
---

# _DXVADDI_VIDEOPROCESSORCAPS structure


## -description

The DXVADDI_VIDEOPROCESSORCAPS structure describes the video processing capabilities of a specific deinterlace mode.

## -struct-fields

### -field InputPool

[out] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_pool">D3DDDI_POOL</a>-typed value that indicates the memory pool from which the interlaced source surfaces should be allocated.

### -field NumForwardRefSamples

[out] The required number of forward reference samples for the defined deinterlace mode. The samples are in subsequent fields. This value is zero for bob and line blending and can be other values (such as 1, 2, or 3) for adaptive deinterlacing and frame-rate conversion.

### -field NumBackwardRefSamples

[out] The required backward reference samples for the defined deinterlace mode. The samples are in former fields. This value is zero for bob, 1 for line blending and can be other values (such as 1, 2, or 3) for adaptive deinterlacing and frame-rate conversion.

### -field OutputFormat

[out] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the uncompressed output frames. Typically, a deinterlace algorithm outputs frames in a pixel format that matches the input sample format. This member ensures that the Video Mixing Renderer (VMR) or other video renderer is able to supply the correct output frame surfaces to the deinterlacing hardware.

Note that if the DXVADDI_VIDEOPROCESS_YUV2RGB value is returned in the <b>VideoProcessorOperations</b> member, the VMR determines that valid output formats are specified by this member as well as an D3DFMT_X8R8G8B8 format.

### -field DeinterlaceTechnology

[out] A bitwise OR of the following values to indicate the underlying deinterlacing technology that is used to implement the deinterlacing algorithm. The values can be combined as required to most closely match the algorithm's implementation.

| **Value** | **Meaning** | 
|:--|:--|
| DXVADDI_DEINTERLACETECH_UNKNOWN | The deinterlacing technology is unknown. | 
| DXVADDI_DEINTERLACETECH_BOBLINEREPLICATE | The deinterlace algorithm creates missing lines by repeating the line either above or below a missing line. This method looks jagged and is not recommended. | 
| DXVADDI_DEINTERLACETECH_BOBVERTICALSTRETCH | A deinterlace algorithm that creates missing lines by vertically stretching each video field by a factor of two by averaging two lines. Slight vertical adjustments are made to ensure that the resulting image does not move up and down. | 
| DXVADDI_DEINTERLACETECH_BOBVERTICALSTRETCH4TAP | A deinterlace algorithm that creates missing lines by vertically stretching each video field by a factor of two by using a [-1, 9, 9, -1] / 16 filter across four lines. Slight vertical adjustments are made to ensure that the resulting image does not move up and down. | 
| DXVADDI_DEINTERLACETECH_MEDIANFILTERING | The pixels in the missing line are recreated by a median filtering operation. | 
| DXVADDI_DEINTERLACETECH_EDGEFILTERING | Pixels in the missing line are recreated by an edge filter. In this process, spatial directional filters are applied to determine the orientation of edges in the picture content, and missing pixels are created by filtering along (rather than across) the detected edges. | 
| DXVADDI_DEINTERLACETECH_FIELDADAPTIVE | Pixels in the missing line are recreated by switching on a field-by-field basis between either spatial or temporal interpolation, depending on the amount of motion. | 
| DXVADDI_DEINTERLACETECH_PIXELADAPTIVE | Pixels in the missing line are recreated by switching on a pixel-by-pixel basis between either spatial or temporal interpolation, depending on the amount of motion. | 
| DXVADDI_DEINTERLACETECH_MOTIONVECTORSTEERED | Objects within a sequence of video fields. The missing pixels are recreated after first aligning the movement axis of the individual objects in the scene to make them parallel with the time axis. | 
| DXVADDI_DEINTERLACETECH_INVERSETELECINE | A deinterlace algorithm that can undo the 3:2 pull-down process that is used for displaying 24Hz-content on 60Hz-displays, 25Hz-content on 50Hz-displays, or so on. |

### -field ProcAmpControlCaps

[out] A bitwise OR of the following values to indicate the ProcAmp operations that the hardware supports.

| **Value** | **Meaning** | 
|:--|:--|
| DXVADDI_PROCAMP_NONE | The hardware does not support any ProcAmp operations. | 
| DXVADDI_PROCAMP_BRIGHTNESS | Brightness adjustments to the video image are allowed. | 
| DXVADDI_PROCAMP_CONTRAST | Contrast adjustments to the video image are allowed. | 
| DXVADDI_PROCAMP_HUE | Hue adjustments to the video image are allowed. | 
| DXVADDI_PROCAMP_SATURATION | Saturation adjustments to the video image are allowed. |

### -field VideoProcessorOperations

[out] A bitwise OR of the following values to indicate which additional video processing operations the hardware can perform concurrently with the requested <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_videoprocessblt">VideoProcessBlt</a> operation.

| **Value** | **Meaning** | 
|:--|:--|
| DXVADDI_VIDEOPROCESS_NONE | The hardware cannot perform any more video processing operations. | 
| DXVADDI_VIDEOPROCESS_YUV2RGB | Video conversion from the YUV color space to the RGB color space is allowed. The RGB format that is used has at least 8 bits of precision for each color component. If this operation is possible, a buffer copy within the VMR can be avoided. Note that conversion from the RGB color space to the YUV color space is not required. | 
| DXVADDI_VIDEOPROCESS_STRETCHX | Aspect ratio correction can be performed at the same time as the video is ProcAmp-adjusted if the hardware is able to stretch or shrink horizontally. | 
| DXVADDI_VIDEOPROCESS_STRETCHY | Aspect ratio adjustment is combined with a general picture resizing operation to scale the video image within an application-defined composition space. This operation is rare and not an essential feature. It is best if the scaling that is required for resizing the video to fit into the application window can be done at the same time as the scaling required for ProcAmp adjustment. This type of operation avoids cumulative artifacts. | 
| DXVADDI_VIDEOPROCESS_ALPHABLEND | The VMR does not perform a buffer copy when an alpha value is changed. Applications rarely alter the constant alpha value that is associated with the video stream, so this operation is a low priority feature. | 
| DXVADDI_VIDEOPROCESS_SUBRECTS | The video processing device can operate on a subrectangle region of the video image. This operation is useful if the video image must be cropped before being processed further as the size of the output frame is reduced. | 
| DXVADDI_VIDEOPROCESS_SUBSTREAMS | The video processing device can combine video substreams with the video stream. | 
| DXVADDI_VIDEOPROCESS_SUBSTREAMSEXTENDED | Necessary color adjustments can be made to the source video streams and substreams. These adjustments are indicated in the extended color data, as the video is deinterlaced, composited with the substreams, and written to the destination surface. | 
| DXVADDI_VIDEOPROCESS_YUV2RGBEXTENDED | A color-space-conversion operation can be performed as the deinterlaced and composited pixels are written to the destination surface by using the extended color information that is specified for the source and destination surfaces. | 
| DXVADDI_VIDEOPROCESS_ALPHABLENDEXTENDED | An alpha-blend operation can be performed with the destination surface when the deinterlaced and composited pixels are written to the destination surface. The driver must handle background color based on the alpha value of the Alpha member of the [D3DDDIARG_VIDEOPROCESSBLT](./ns-d3dumddi-_d3dddiarg_videoprocessblt.md) structure. When the alpha value is 1.0, the background color is drawn opaque (without transparency). When the alpha value is 0.0, the background should not be drawn (transparent). | 
| DXVADDI_VIDEOPROCESS_CONSTRICTION | The video processing device can temporarily reduce the output frame to a size that the ConstrictionSize member of the [D3DDDIARG_VIDEOPROCESSBLT](./ns-d3dumddi-_d3dddiarg_videoprocessblt.md) structure specifies. | 
| DXVADDI_VIDEOPROCESS_NOISEFILTER | The video processing device can perform noise filtering operations on the video stream. | 
| DXVADDI_VIDEOPROCESS_DETAILFILTER | The video processing device can perform detail filtering operations on the video stream. | 
| DXVADDI_VIDEOPROCESS_PLANARALPHA | The video processing device can apply a constant alpha blend to the entire video stream (plane) while it mixes the video stream and substreams together. The Alpha member of D3DDDIARG_VIDEOPROCESSBLT specifies the alpha value. | 
| DXVADDI_VIDEOPROCESS_LINEARSCALING | The video processing device can linearly scale the video stream. | 
| DXVADDI_VIDEOPROCESS_GAMMACOMPENSATED | The video processing device can perform gamma conversion on the video stream. | 
| DXVADDI_VIDEOPROCESS_MAINTAINSORIGINALFIELDDATA | The video processing device can maintain the original field data. |

### -field NoiseFilterTechnology

[out] A bitwise OR of the following values to indicate the underlying technology that is used to implement noise filtering. The values can be combined as required to most closely match the noise-filter implementation. 

| **Value** | **Meaning** | 
|:--|:--|
| DXVADDI_NOISEFILTERTECH_UNSUPPORTED | No noise-filter technology is supported. | 
| DXVADDI_NOISEFILTERTECH_UNKNOWN | The noise-filter technology is unknown. | 
| DXVADDI_NOISEFILTERTECH_MEDIAN | The video processing device uses median noise filtering. | 
| DXVADDI_NOISEFILTERTECH_TEMPORAL | The video processing device uses temporal noise filtering. | 
| DXVADDI_NOISEFILTERTECH_BLOCKNOISE | The video processing device uses block noise filtering. | 
| DXVADDI_NOISEFILTERTECH_MOSQUITONOISE | The video processing device uses mosquito noise filtering. |

### -field DetailFilterTechnology

[out] A bitwise OR of the following values to indicate the underlying technology that is used to implement detail filtering. The values can be combined as required to most closely match the detail-filter implementation.  

| **Value** | **Meaning** | 
|:--|:--|
| DXVADDI_DETAILFILTERTECH_UNSUPPORTED | No detail-filter technology is supported. | 
| DXVADDI_DETAILFILTERTECH_UNKNOWN | The detail-filter technology is unknown. | 
| DXVADDI_DETAILFILTERTECH_EDGE | The video processing device uses edge detail filtering. | 
| DXVADDI_DETAILFILTERTECH_SHARPENING | The video processing device uses sharpening detail filtering. |

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_videoprocessblt">D3DDDIARG_VIDEOPROCESSBLT</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_pool">D3DDDI_POOL</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videoprocessorinput">DXVADDI_VIDEOPROCESSORINPUT</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
