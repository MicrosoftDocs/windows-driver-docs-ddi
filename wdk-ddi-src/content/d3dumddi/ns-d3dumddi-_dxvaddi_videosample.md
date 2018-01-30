---
UID: NS:d3dumddi._DXVADDI_VIDEOSAMPLE
title: "_DXVADDI_VIDEOSAMPLE"
author: windows-driver-content
description: The DXVADDI_VIDEOSAMPLE structure describes the format of a video sample that is used in a video processing operation.
old-location: display\dxvaddi_videosample.htm
old-project: display
ms.assetid: 20495325-8ef6-4e6d-8f86-edc12537d46f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVADDI_VIDEOSAMPLE structure [Display Devices], _DXVADDI_VIDEOSAMPLE, DXVA2_Structs_c3a4d002-09dc-4653-a965-9c4f587529d4.xml, DXVADDI_VIDEOSAMPLE, display.dxvaddi_videosample, d3dumddi/DXVADDI_VIDEOSAMPLE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	DXVADDI_VIDEOSAMPLE
product: Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOSAMPLE
---

# _DXVADDI_VIDEOSAMPLE structure


## -description


The DXVADDI_VIDEOSAMPLE structure describes the format of a video sample that is used in a video processing operation.


## -syntax


````
typedef struct _DXVADDI_VIDEOSAMPLE {
  REFERENCE_TIME           Start;
  REFERENCE_TIME           End;
  DXVADDI_EXTENDEDFORMAT   SampleFormat;
  DXVADDI_VIDEOSAMPLEFLAGS SampleFlags;
  HANDLE                   SrcResource;
  UINT                     SrcSubResourceIndex;
  RECT                     SrcRect;
  RECT                     DstRect;
  DXVADDI_AYUVSAMPLE8      Pal[16];
  DXVADDI_FIXED32          PlanarAlpha;
} DXVADDI_VIDEOSAMPLE;
````


## -struct-fields




### -field Start

[in] A REFERENCE_TIME value that identifies the start time of the sample.


### -field End

[in] A REFERENCE_TIME value that identifies the end time of the sample.


### -field SampleFormat

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure that describes the extended format of the video sample.


### -field SampleFlags

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videosampleflags.md">DXVADDI_VIDEOSAMPLEFLAGS</a> structure that identifies changes in the current sample frame from the previous sample frame.


### -field SrcResource

[in] A handle to the resource that contains the source surface.


### -field SrcSubResourceIndex

[in] The index to the source surface within the resource. 


### -field SrcRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the upper-left and lower-right points of a rectangle on the source surface. These points define the area of the source data for the bit-block transfer (bitblt) and its position on the source surface.


### -field DstRect

[in] A RECT structure that describes the upper-left and lower-right points of a rectangle on the destination surface. These points define the area in which the bit-block transfer (bitblt) should occur and its position on the destination surface.


### -field Pal

[in] An array of <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_ayuvsample8.md">DXVADDI_AYUVSAMPLE8</a> structures that represent a complete 16-color palette for palletized video substream pixel formats. The driver uses this palette to composite the substream sample. For nonpalletized pixel formats, the <b>Pal</b> member is <b>NULL</b> and can be ignored.


### -field PlanarAlpha

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a> structure that specifies the transparency value that the driver should apply to the composited background color and video stream and substream image (the entire video plane) as it is written to the destination surface. A value of 0.0 indicates transparent. A value of 1.0 indicates opaque.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_ayuvsample8.md">DXVADDI_AYUVSAMPLE8</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessblt.md">D3DDDIARG_VIDEOPROCESSBLT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOSAMPLE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

