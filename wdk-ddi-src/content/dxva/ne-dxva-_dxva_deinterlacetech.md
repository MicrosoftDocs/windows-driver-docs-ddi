---
UID: NE:dxva._DXVA_DeinterlaceTech
title: "_DXVA_DeinterlaceTech"
author: windows-driver-content
description: The DXVA_DeinterlaceTech enumeration identifies the underlying technology used to implement a particular deinterlace algorithm.
old-location: display\dxva_deinterlacetech.htm
old-project: display
ms.assetid: 06d6b4db-293d-409e-a725-bb86bc6b3d11
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA_DeinterlaceTech_MotionVectorSteered, DXVA_DeinterlaceTech_Unknown, dxvaref_ce829a5b-1e09-43e6-b90c-f7501476f280.xml, DXVA_DeinterlaceTech, dxva/DXVA_DeinterlaceTech_MedianFiltering, DXVA_DeinterlaceTech_BOBLineReplicate, DXVA_DeinterlaceTech_BOBVerticalStretch4Tap, DXVA_DeinterlaceTech enumeration [Display Devices], DXVA_DeinterlaceTech_FieldAdaptive, dxva/DXVA_DeinterlaceTech_EdgeFiltering, DXVA_DeinterlaceTech_EdgeFiltering, DXVA_DeinterlaceTech_PixelAdaptive, _DXVA_DeinterlaceTech, dxva/DXVA_DeinterlaceTech_PixelAdaptive, dxva/DXVA_DeinterlaceTech_Unknown, dxva/DXVA_DeinterlaceTech_MotionVectorSteered, dxva/DXVA_DeinterlaceTech_BOBLineReplicate, dxva/DXVA_DeinterlaceTech, display.dxva_deinterlacetech, dxva/DXVA_DeinterlaceTech_FieldAdaptive, DXVA_DeinterlaceTech_MedianFiltering, dxva/DXVA_DeinterlaceTech_BOBVerticalStretch, dxva/DXVA_DeinterlaceTech_BOBVerticalStretch4Tap, DXVA_DeinterlaceTech_BOBVerticalStretch
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
-	DXVA_DeinterlaceTech
product: Windows
targetos: Windows
req.typenames: DXVA_DeinterlaceTech
---

# _DXVA_DeinterlaceTech enumeration


## -description


The DXVA_DeinterlaceTech enumeration identifies the underlying technology used to implement a particular deinterlace algorithm.


## -syntax


````
typedef enum _DXVA_DeinterlaceTech { 
  DXVA_DeinterlaceTech_Unknown                 = 0x0000,
  DXVA_DeinterlaceTech_BOBLineReplicate        = 0x0001,
  DXVA_DeinterlaceTech_BOBVerticalStretch      = 0x0002,
  DXVA_DeinterlaceTech_BOBVerticalStretch4Tap  = 0x0100,
  DXVA_DeinterlaceTech_MedianFiltering         = 0x0004,
  DXVA_DeinterlaceTech_EdgeFiltering           = 0x0010,
  DXVA_DeinterlaceTech_FieldAdaptive           = 0x0020,
  DXVA_DeinterlaceTech_PixelAdaptive           = 0x0040,
  DXVA_DeinterlaceTech_MotionVectorSteered     = 0x0080
} DXVA_DeinterlaceTech;
````


## -enum-fields




### -field DXVA_DeinterlaceTech_Unknown

Indicates that the algorithm is unknown or proprietary to the hardware manufacturer. 


### -field DXVA_DeinterlaceTech_BOBLineReplicate

Indicates that the algorithm creates the missing lines by repeating the line either above or below it. This method looks jagged and is not recommended. 


### -field DXVA_DeinterlaceTech_BOBVerticalStretch

Specifies an algorithm that creates the missing lines by vertically stretching each video field by a factor of two. Vertical adjustments are made to ensure that the resulting image does not move up and down. 


### -field DXVA_DeinterlaceTech_BOBVerticalStretch4Tap

Creates the missing lines by vertically stretching each video field by a factor of two, using a 4-tap filter.


### -field DXVA_DeinterlaceTech_MedianFiltering

Specifies that the pixels in the missing line are recreated by a median filtering operation. 


### -field DXVA_DeinterlaceTech_EdgeFiltering

Specifies that pixels in the missing line are recreated by an edge filter. In this process, spatial directional filters are applied to determine the orientation of edges in the picture content, and missing pixels are created by filtering along (rather than across) the detected edges. 


### -field DXVA_DeinterlaceTech_FieldAdaptive

Specifies that pixels in the missing line are recreated by switching on a field-by-field basis between either spatial or temporal interpolation, depending on the amount of motion. 


### -field DXVA_DeinterlaceTech_PixelAdaptive

Specifies that pixels in the missing line are recreated by switching on a pixel-by-pixel basis between either spatial or temporal interpolation, depending on the amount of motion. 


### -field DXVA_DeinterlaceTech_MotionVectorSteered

Identifies objects within a sequence of video fields. The missing pixels are recreated after first aligning the movement axis of the individual objects in the scene to make them parallel with the time axis.


## -see-also

<a href="..\dxva\ns-dxva-_dxva_deinterlacecaps.md">DXVA_DeinterlaceCaps</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_DeinterlaceTech enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

