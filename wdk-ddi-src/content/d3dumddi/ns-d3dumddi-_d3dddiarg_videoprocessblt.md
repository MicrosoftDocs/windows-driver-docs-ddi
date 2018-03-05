---
UID: NS:d3dumddi._D3DDDIARG_VIDEOPROCESSBLT
title: "_D3DDDIARG_VIDEOPROCESSBLT"
author: windows-driver-content
description: The D3DDDIARG_VIDEOPROCESSBLT structure describes a Microsoft DirectX Video Acceleration (VA) video processing operation to perform.
old-location: display\d3dddiarg_videoprocessblt.htm
old-project: display
ms.assetid: 24e4115f-cd21-46e7-aacc-9b66e7513b9e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_VIDEOPROCESSBLT, D3DDDIARG_VIDEOPROCESSBLT structure [Display Devices], UMDisplayDriver_param_Structs_feb8d240-92ee-45b9-a07e-50b89f906fbe.xml, _D3DDDIARG_VIDEOPROCESSBLT, d3dumddi/D3DDDIARG_VIDEOPROCESSBLT, display.d3dddiarg_videoprocessblt
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
-	D3DDDIARG_VIDEOPROCESSBLT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_VIDEOPROCESSBLT
---

# _D3DDDIARG_VIDEOPROCESSBLT structure


## -description


The D3DDDIARG_VIDEOPROCESSBLT structure describes a Microsoft DirectX Video Acceleration (VA) video processing operation to perform.


## -syntax


````
typedef struct _D3DDDIARG_VIDEOPROCESSBLT {
  REFERENCE_TIME               TargetFrame;
  HANDLE                       hVideoProcess;
  RECT                         TargetRect;
  SIZE                         ConstrictionSize;
  UINT                         StreamingFlags;
  DXVADDI_AYUVSAMPLE16         BackgroundColor;
  DXVADDI_EXTENDEDFORMAT       DestFormat;
  DXVADDI_VIDEOPROCESSBLTFLAGS DestFlags;
  DXVADDI_PROCAMPVALUES        ProcAmpValues;
  DXVADDI_FIXED32              Alpha;
  DXVADDI_FILTERVALUES         NoiseFilterLuma;
  DXVADDI_FILTERVALUES         NoiseFilterChroma;
  DXVADDI_FILTERVALUES         DetailFilterLuma;
  DXVADDI_FILTERVALUES         DetailFilterChroma;
  DXVADDI_VIDEOSAMPLE          *pSrcSurfaces;
  UINT                         NumSrcSurfaces;
} D3DDDIARG_VIDEOPROCESSBLT;
````


## -struct-fields




### -field TargetFrame

[in] A REFERENCE_TIME value that identifies the location of the output frame within the sequence of input frames. If only deinterlacing is performed, the target time should coincide with either the starting display time of a sample, as defined by the <b>Start</b> member in the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videosample.md">DXVADDI_VIDEOSAMPLE</a> structure, or the midpoint between the starting display time and the ending display time. 

If a frame rate conversion is requested, the time in <b>TargetFrame</b> can be different from any of the times in the <b>Start</b> members of the samples.


### -field hVideoProcess

[in] A handle to the DirectX VA video processing device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a> function.


### -field TargetRect

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the location within the destination surface to which the output image is written. Note that the output image is restricted to the pixels within the rectangle that is pointed to by <b>TargetRect</b>. That is, every pixel within this rectangle must be written to; pixels outside this rectangle must not be modified. 


### -field ConstrictionSize

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/dn915850">SIZE</a> structure that specifies, for protected content, the size to reduce the output image to. <b>ConstrictionSize</b> should be from (1, 1) to (width, height) of the target rectangle that is specified in the <b>TargetRect</b> member. <b>ConstrictionSize</b> should be (0, 0) to represent no constriction.

For example, consider video that natively has 1920 x 1080 pixels and that is displayed full screen on a 1920 x 1080-resolution monitor for which output protection is unsupported. If the video content specifies a rule that only 854 x 480 pixels of original information can be displayed, the driver must reduce the original image from 1920 x 1080 to 854 x 480 and then stretch the image again to 1920 x 1080. In this example, the SIZE structure in the <b>ConstrictionSize</b> member would specify a size of 854 x 480 pixels.


### -field StreamingFlags

[in] A UINT value that identifies streaming flags. Currently, no streaming flags are defined.


### -field BackgroundColor

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_ayuvsample16.md">DXVADDI_AYUVSAMPLE16</a> structure that identifies background color. 


### -field DestFormat

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure that identifies extended format information for the destination surface. 


### -field DestFlags

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videoprocessbltflags.md">DXVADDI_VIDEOPROCESSBLTFLAGS</a> structure that identifies changes in the current destination surface from the previous destination surface.


### -field ProcAmpValues

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_procampvalues.md">DXVADDI_PROCAMPVALUES</a> structure that specifies ProcAmp adjustment data that is output to the destination surface.


### -field Alpha

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a> structure that specifies the planar-transparency value of the output image as it is written to the destination surface. When the alpha value is 1.0, the background color is drawn opaque (without transparency and alpha blending). When the alpha value is 0.0, the background should not be drawn (transparent).


### -field NoiseFilterLuma

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_filtervalues.md">DXVADDI_FILTERVALUES</a> structure that specifies the luma noise filter.


### -field NoiseFilterChroma

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_filtervalues.md">DXVADDI_FILTERVALUES</a> structure that specifies the chroma noise filter.


### -field DetailFilterLuma

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_filtervalues.md">DXVADDI_FILTERVALUES</a> structure that specifies the luma detail filter.


### -field DetailFilterChroma

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_filtervalues.md">DXVADDI_FILTERVALUES</a> structure that specifies the chroma detail filter.


### -field pSrcSurfaces

[in] An array of <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videosample.md">DXVADDI_VIDEOSAMPLE</a> structures that describe the input samples that are required for the deinterlacing, frame-rate conversion, and substream compositing operations. For more information about how input samples are arranged in this array, see <a href="https://msdn.microsoft.com/99110b1a-1511-44f5-a4bb-a5e38fd41fff">Input Buffer Order</a>.


### -field NumSrcSurfaces

[in] The number of input samples in the array at <b>pSrcSurfaces</b>.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videosample.md">DXVADDI_VIDEOSAMPLE</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_procampvalues.md">DXVADDI_PROCAMPVALUES</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videoprocessbltflags.md">DXVADDI_VIDEOPROCESSBLTFLAGS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessblt.md">VideoProcessBlt</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_ayuvsample8.md">DXVADDI_AYUVSAMPLE8</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_VIDEOPROCESSBLT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

