---
UID: NE:dxva._DXVA_VideoProcessCaps
title: "_DXVA_VideoProcessCaps"
author: windows-driver-content
description: The DXVA_VideoProcessCaps enumeration identifies operations that can be performed concurrently with the requested deinterlace.
old-location: display\dxva_videoprocesscaps.htm
old-project: display
ms.assetid: 225da110-cd59-4803-bde8-26e275b3ddbd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA_VideoProcess_SubRects, dxva/DXVA_VideoProcess_YUV2RGBExtended, dxva/DXVA_VideoProcess_StretchY, DXVA_VideoProcess_StretchY, DXVA_VideoProcess_AlphaBlend, dxva/DXVA_VideoProcessCaps, dxva/DXVA_VideoProcess_YUV2RGB, dxva/DXVA_VideoProcess_SubRects, dxva/DXVA_VideoProcess_AlphaBlend, dxva/DXVA_VideoProcess_AlphaBlendExtended, DXVA_VideoProcessCaps, dxva/DXVA_VideoProcess_SubStreamsExtended, display.dxva_videoprocesscaps, DXVA_VideoProcess_YUV2RGB, dxvaref_4298738a-dc13-47b4-bb3d-84e90661542b.xml, _DXVA_VideoProcessCaps, DXVA_VideoProcess_StretchX, DXVA_VideoProcess_AlphaBlendExtended, DXVA_VideoProcess_YUV2RGBExtended, DXVA_VideoProcess_SubStreamsExtended, dxva/DXVA_VideoProcess_None, DXVA_VideoProcessCaps enumeration [Display Devices], DXVA_VideoProcess_None, DXVA_VideoProcess_SubStreams, dxva/DXVA_VideoProcess_StretchX, dxva/DXVA_VideoProcess_SubStreams
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxva.h
apiname:
-	DXVA_VideoProcessCaps
product: Windows
targetos: Windows
req.typenames: DXVA_VideoProcessCaps
---

# _DXVA_VideoProcessCaps enumeration


## -description


The DXVA_VideoProcessCaps enumeration identifies operations that can be performed concurrently with the requested deinterlace. 


## -syntax


````
typedef enum _DXVA_VideoProcessCaps { 
  DXVA_VideoProcess_None                = 0x0000,
  DXVA_VideoProcess_YUV2RGB             = 0x0001,
  DXVA_VideoProcess_StretchX            = 0x0002,
  DXVA_VideoProcess_StretchY            = 0x0004,
  DXVA_VideoProcess_AlphaBlend          = 0x0008,
  DXVA_VideoProcess_SubRects            = 0x0010,
  DXVA_VideoProcess_SubStreams          = 0x0020,
  DXVA_VideoProcess_SubStreamsExtended  = 0x0040,
  DXVA_VideoProcess_YUV2RGBExtended     = 0x0080,
  DXVA_VideoProcess_AlphaBlendExtended  = 0x0100
} DXVA_VideoProcessCaps;
````


## -enum-fields




### -field DXVA_VideoProcess_None

Indicates that the deinterlace hardware can only perform basic deinterlace operations. That is, deinterlace operations that are not combined with other operations, like-color conversion, alpha blend, stretch, subsection, or substream. 


### -field DXVA_VideoProcess_YUV2RGB

Indicates that the deinterlace hardware can convert video from the YUV color space to the RGB color space. The RGB format will have at least 8 bits of precision for each color component. If possible, a buffer copy within the VMR can be avoided. All drivers should be able to support this operation for the bob deinterlace mode. 


Not used with the <a href="https://msdn.microsoft.com/12a0e467-54f8-4cca-8ec0-aa8d04480ab6">DeinterlaceBltEx</a> function.


### -field DXVA_VideoProcess_StretchX

Indicates that aspect ratio correction can be performed simultaneously as the video is being deinterlaced if the deinterlacer is able to stretch or shrink horizontally. The enumerator should be supported for the bob deinterlace mode.

Must use with the <a href="https://msdn.microsoft.com/12a0e467-54f8-4cca-8ec0-aa8d04480ab6">DeinterlaceBltEx</a> function.



### -field DXVA_VideoProcess_StretchY

Indicates that aspect ratio adjustment is combined with a general picture resizing operation to scale the video image.

Must use with the <a href="https://msdn.microsoft.com/12a0e467-54f8-4cca-8ec0-aa8d04480ab6">DeinterlaceBltEx</a> function.



### -field DXVA_VideoProcess_AlphaBlend

Indicates that the VMR will not perform a buffer copy when an alpha value is changed. It is rare that applications alter the constant alpha value associated with the video stream, so this is a low priority feature. The enumerator should be supported for the bob deinterlace mode.


Not used with the <a href="https://msdn.microsoft.com/12a0e467-54f8-4cca-8ec0-aa8d04480ab6">DeinterlaceBltEx</a> function.



### -field DXVA_VideoProcess_SubRects

Indicates that the deinterlace hardware can deinterlace just a subrectangle region of the video image to the specified destination position. This is useful if the video image must be cropped before being processed further as the size of the output frame is reduced. 


### -field DXVA_VideoProcess_SubStreams

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.


Indicates that the deinterlace hardware can combine video substreams with the video stream.


Must use with the <a href="https://msdn.microsoft.com/12a0e467-54f8-4cca-8ec0-aa8d04480ab6">DeinterlaceBltEx</a> function.


### -field DXVA_VideoProcess_SubStreamsExtended

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.


Indicates that necessary color adjustments can be made to the source video streams and substreams. These adjustments are indicated in the extended color data, as the video is deinterlaced, composited with the substreams, and written to the destination surface.

Must use with the <a href="https://msdn.microsoft.com/12a0e467-54f8-4cca-8ec0-aa8d04480ab6">DeinterlaceBltEx</a> function.


### -field DXVA_VideoProcess_YUV2RGBExtended

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.


Indicates a color-space-conversion operation can be performed as the deinterlaced and composited pixels are written to the destination surface using the extended color information that is specified for the source and destination surfaces.


Must use with the <a href="https://msdn.microsoft.com/12a0e467-54f8-4cca-8ec0-aa8d04480ab6">DeinterlaceBltEx</a> function.


### -field DXVA_VideoProcess_AlphaBlendExtended

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.


Indicates that an alpha-blend operation can be performed with the destination surface when the deinterlaced and composited pixels are written to the destination surface. The driver must handle background color based on the alpha value of the <b>Alpha</b> member of the <a href="..\dxva\ns-dxva-_dxva_deinterlacebltex.md">DXVA_DeinterlaceBltEx</a> structure. When the alpha value is 1.0f, the background color is drawn opaque (without transparency). When the alpha value is 0.0f, the background should not be drawn (transparent).

Must use with the <a href="https://msdn.microsoft.com/12a0e467-54f8-4cca-8ec0-aa8d04480ab6">DeinterlaceBltEx</a> function.



## -remarks


Occasionally, the aspect ratio adjustment performed by <b>DXVA_VideoProcess_AlphaBlend</b> is combined with a general picture resizing operation to scale the video image within an application-defined composition space, which is rare and not an essential feature. It is best if the scaling needed for resizing the video to fit into the application window can be done simultaneously to the scaling needed for deinterlacing, which avoids cumulative artifacts. 

Color space conversion performed by <b>DXVA_VideoProcess_YUV2RGB</b> is particularly useful within the VMR if it is combined with any (and ideally, all) of the following enumerators: <b>DXVA_VideoProcess_StretchX</b>, <b>DXVA_VideoProcess_StretchY</b>, and <b>DXVA_VideoProcess_AlphaBlend</b>. There is no requirement to convert from the RGB color space to the YUV color space.



## -see-also

<a href="..\dxva\ns-dxva-_dxva_deinterlacecaps.md">DXVA_DeinterlaceCaps</a>

<a href="https://msdn.microsoft.com/12a0e467-54f8-4cca-8ec0-aa8d04480ab6">DeinterlaceBltEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoProcessCaps enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

