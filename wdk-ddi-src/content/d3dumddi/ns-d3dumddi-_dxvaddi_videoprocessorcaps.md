---
UID: NS:d3dumddi._DXVADDI_VIDEOPROCESSORCAPS
title: "_DXVADDI_VIDEOPROCESSORCAPS"
author: windows-driver-content
description: The DXVADDI_VIDEOPROCESSORCAPS structure describes the video processing capabilities of a specific deinterlace mode.
old-location: display\dxvaddi_videoprocessorcaps.htm
old-project: display
ms.assetid: bea6d458-943e-466f-adca-466f26dc3599
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXVA2_Structs_dc28e351-d197-4440-a3fd-dc3a49e35230.xml, DXVADDI_VIDEOPROCESSORCAPS, DXVADDI_VIDEOPROCESSORCAPS structure [Display Devices], _DXVADDI_VIDEOPROCESSORCAPS, d3dumddi/DXVADDI_VIDEOPROCESSORCAPS, display.dxvaddi_videoprocessorcaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVADDI_VIDEOPROCESSORCAPS
product: Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOPROCESSORCAPS
---

# _DXVADDI_VIDEOPROCESSORCAPS structure


## -description


The DXVADDI_VIDEOPROCESSORCAPS structure describes the video processing capabilities of a specific deinterlace mode.


## -syntax


````
typedef struct _DXVADDI_VIDEOPROCESSORCAPS {
  D3DDDI_POOL  InputPool;
  UINT         NumForwardRefSamples;
  UINT         NumBackwardRefSamples;
  D3DDDIFORMAT OutputFormat;
  UINT         DeinterlaceTechnology;
  UINT         ProcAmpControlCaps;
  UINT         VideoProcessorOperations;
  UINT         NoiseFilterTechnology;
  UINT         DetailFilterTechnology;
} DXVADDI_VIDEOPROCESSORCAPS;
````


## -struct-fields




### -field InputPool

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_pool.md">D3DDDI_POOL</a>-typed value that indicates the memory pool from which the interlaced source surfaces should be allocated. 


### -field NumForwardRefSamples

[out] The required number of forward reference samples for the defined deinterlace mode. The samples are in subsequent fields. This value is zero for bob and line blending and can be other values (such as 1, 2, or 3) for adaptive deinterlacing and frame-rate conversion.


### -field NumBackwardRefSamples

[out] The required backward reference samples for the defined deinterlace mode. The samples are in former fields. This value is zero for bob, 1 for line blending and can be other values (such as 1, 2, or 3) for adaptive deinterlacing and frame-rate conversion.


### -field OutputFormat

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the uncompressed output frames. Typically, a deinterlace algorithm outputs frames in a pixel format that matches the input sample format. This member ensures that the Video Mixing Renderer (VMR) or other video renderer is able to supply the correct output frame surfaces to the deinterlacing hardware.

Note that if the DXVADDI_VIDEOPROCESS_YUV2RGB value is returned in the <b>VideoProcessorOperations</b> member, the VMR determines that valid output formats are specified by this member as well as an D3DFMT_X8R8G8B8 format.


### -field DeinterlaceTechnology

[out] A bitwise OR of the following values to indicate the underlying deinterlacing technology that is used to implement the deinterlacing algorithm. The values can be combined as required to most closely match the algorithm's implementation.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_UNKNOWN

</td>
<td>
The deinterlacing technology is unknown.

</td>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_BOBLINEREPLICATE

</td>
<td>
The deinterlace algorithm creates missing lines by repeating the line either above or below a missing line. This method looks jagged and is not recommended.

</td>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_BOBVERTICALSTRETCH

</td>
<td>
A deinterlace algorithm that creates missing lines by vertically stretching each video field by a factor of two by averaging two lines. Slight vertical adjustments are made to ensure that the resulting image does not move up and down.

</td>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_BOBVERTICALSTRETCH4TAP

</td>
<td>
A deinterlace algorithm that creates missing lines by vertically stretching each video field by a factor of two by using a [-1, 9, 9, -1] / 16 filter across four lines. Slight vertical adjustments are made to ensure that the resulting image does not move up and down.

</td>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_MEDIANFILTERING

</td>
<td>
The pixels in the missing line are recreated by a median filtering operation.

</td>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_EDGEFILTERING

</td>
<td>
Pixels in the missing line are recreated by an edge filter. In this process, spatial directional filters are applied to determine the orientation of edges in the picture content, and missing pixels are created by filtering along (rather than across) the detected edges.

</td>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_FIELDADAPTIVE

</td>
<td>
Pixels in the missing line are recreated by switching on a field-by-field basis between either spatial or temporal interpolation, depending on the amount of motion.

</td>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_PIXELADAPTIVE

</td>
<td>
Pixels in the missing line are recreated by switching on a pixel-by-pixel basis between either spatial or temporal interpolation, depending on the amount of motion.

</td>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_MOTIONVECTORSTEERED

</td>
<td>
Objects within a sequence of video fields. The missing pixels are recreated after first aligning the movement axis of the individual objects in the scene to make them parallel with the time axis.

</td>
</tr>
<tr>
<td>
DXVADDI_DEINTERLACETECH_INVERSETELECINE

</td>
<td>
A deinterlace algorithm that can undo the 3:2 pull-down process that is used for displaying 24Hz-content on 60Hz-displays, 25Hz-content on 50Hz-displays, or so on.

</td>
</tr>
</table>
 


### -field ProcAmpControlCaps

[out] A bitwise OR of the following values to indicate the ProcAmp operations that the hardware supports.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXVADDI_PROCAMP_NONE

</td>
<td>
The hardware does not support any ProcAmp operations.

</td>
</tr>
<tr>
<td>
DXVADDI_PROCAMP_BRIGHTNESS

</td>
<td>
Brightness adjustments to the video image are allowed.

</td>
</tr>
<tr>
<td>
DXVADDI_PROCAMP_CONTRAST

</td>
<td>
Contrast adjustments to the video image are allowed.

</td>
</tr>
<tr>
<td>
DXVADDI_PROCAMP_HUE

</td>
<td>
Hue adjustments to the video image are allowed.

</td>
</tr>
<tr>
<td>
DXVADDI_PROCAMP_SATURATION

</td>
<td>
Saturation adjustments to the video image are allowed.

</td>
</tr>
</table>
 


### -field VideoProcessorOperations

[out] A bitwise OR of the following values to indicate which additional video processing operations the hardware can perform concurrently with the requested <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessblt.md">VideoProcessBlt</a> operation.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_NONE

</td>
<td>
The hardware cannot perform any more video processing operations.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_YUV2RGB

</td>
<td>
Video conversion from the YUV color space to the RGB color space is allowed. The RGB format that is used has at least 8 bits of precision for each color component. If this operation is possible, a buffer copy within the VMR can be avoided. Note that conversion from the RGB color space to the YUV color space is not required.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_STRETCHX

</td>
<td>
Aspect ratio correction can be performed at the same time as the video is ProcAmp-adjusted if the hardware is able to stretch or shrink horizontally.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_STRETCHY

</td>
<td>
Aspect ratio adjustment is combined with a general picture resizing operation to scale the video image within an application-defined composition space. This operation is rare and not an essential feature. It is best if the scaling that is required for resizing the video to fit into the application window can be done at the same time as the scaling required for ProcAmp adjustment. This type of operation avoids cumulative artifacts.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_ALPHABLEND

</td>
<td>
The VMR does not perform a buffer copy when an alpha value is changed. Applications rarely alter the constant alpha value that is associated with the video stream, so this operation is a low priority feature.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_SUBRECTS

</td>
<td>
The video processing device can operate on a subrectangle region of the video image. This operation is useful if the video image must be cropped before being processed further as the size of the output frame is reduced.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_SUBSTREAMS

</td>
<td>
The video processing device can combine video substreams with the video stream.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_SUBSTREAMSEXTENDED

</td>
<td>
Necessary color adjustments can be made to the source video streams and substreams. These adjustments are indicated in the extended color data, as the video is deinterlaced, composited with the substreams, and written to the destination surface.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_YUV2RGBEXTENDED

</td>
<td>
A color-space-conversion operation can be performed as the deinterlaced and composited pixels are written to the destination surface by using the extended color information that is specified for the source and destination surfaces.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_ALPHABLENDEXTENDED

</td>
<td>
An alpha-blend operation can be performed with the destination surface when the deinterlaced and composited pixels are written to the destination surface. The driver must handle background color based on the alpha value of the <b>Alpha</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessblt.md">D3DDDIARG_VIDEOPROCESSBLT</a> structure. When the alpha value is 1.0, the background color is drawn opaque (without transparency). When the alpha value is 0.0, the background should not be drawn (transparent).

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_CONSTRICTION

</td>
<td>
The video processing device can temporarily reduce the output frame to a size that the <b>ConstrictionSize</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessblt.md">D3DDDIARG_VIDEOPROCESSBLT</a> structure specifies.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_NOISEFILTER

</td>
<td>
The video processing device can perform noise filtering operations on the video stream.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_DETAILFILTER

</td>
<td>
The video processing device can perform detail filtering operations on the video stream.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_PLANARALPHA

</td>
<td>
The video processing device can apply a constant alpha blend to the entire video stream (plane) while it mixes the video stream and substreams together. The <b>Alpha</b> member of D3DDDIARG_VIDEOPROCESSBLT specifies the alpha value.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_LINEARSCALING

</td>
<td>
The video processing device can linearly scale the video stream.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_GAMMACOMPENSATED

</td>
<td>
The video processing device can perform gamma conversion on the video stream.

</td>
</tr>
<tr>
<td>
DXVADDI_VIDEOPROCESS_MAINTAINSORIGINALFIELDDATA

</td>
<td>
The video processing device can maintain the original field data.

</td>
</tr>
</table>
 


### -field NoiseFilterTechnology

[out] A bitwise OR of the following values to indicate the underlying technology that is used to implement noise filtering. The values can be combined as required to most closely match the noise-filter implementation. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXVADDI_NOISEFILTERTECH_UNSUPPORTED

</td>
<td>
No noise-filter technology is supported.

</td>
</tr>
<tr>
<td>
DXVADDI_NOISEFILTERTECH_UNKNOWN

</td>
<td>
The noise-filter technology is unknown.

</td>
</tr>
<tr>
<td>
DXVADDI_NOISEFILTERTECH_MEDIAN

</td>
<td>
The video processing device uses median noise filtering.

</td>
</tr>
<tr>
<td>
DXVADDI_NOISEFILTERTECH_TEMPORAL

</td>
<td>
The video processing device uses temporal noise filtering.

</td>
</tr>
<tr>
<td>
DXVADDI_NOISEFILTERTECH_BLOCKNOISE

</td>
<td>
The video processing device uses block noise filtering.

</td>
</tr>
<tr>
<td>
DXVADDI_NOISEFILTERTECH_MOSQUITONOISE

</td>
<td>
The video processing device uses mosquito noise filtering.

</td>
</tr>
</table>
 


### -field DetailFilterTechnology

[out] A bitwise OR of the following values to indicate the underlying technology that is used to implement detail filtering. The values can be combined as required to most closely match the detail-filter implementation.  

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXVADDI_DETAILFILTERTECH_UNSUPPORTED

</td>
<td>
No detail-filter technology is supported.

</td>
</tr>
<tr>
<td>
DXVADDI_DETAILFILTERTECH_UNKNOWN

</td>
<td>
The detail-filter technology is unknown.

</td>
</tr>
<tr>
<td>
DXVADDI_DETAILFILTERTECH_EDGE

</td>
<td>
The video processing device uses edge detail filtering.

</td>
</tr>
<tr>
<td>
DXVADDI_DETAILFILTERTECH_SHARPENING

</td>
<td>
The video processing device uses sharpening detail filtering.

</td>
</tr>
</table>
 


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_pool.md">D3DDDI_POOL</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>



<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessblt.md">D3DDDIARG_VIDEOPROCESSBLT</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videoprocessorinput.md">DXVADDI_VIDEOPROCESSORINPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOPROCESSORCAPS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

