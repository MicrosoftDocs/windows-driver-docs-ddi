---
UID: NE:dxva._DXVA_DeinterlaceTech
title: _DXVA_DeinterlaceTech (dxva.h)
description: The DXVA_DeinterlaceTech enumeration identifies the underlying technology used to implement a particular deinterlace algorithm.
old-location: display\dxva_deinterlacetech.htm
tech.root: display
ms.assetid: 06d6b4db-293d-409e-a725-bb86bc6b3d11
ms.date: 05/10/2018
keywords: ["DXVA_DeinterlaceTech enumeration"]
ms.keywords: DXVA_DeinterlaceTech, DXVA_DeinterlaceTech enumeration [Display Devices], DXVA_DeinterlaceTech_BOBLineReplicate, DXVA_DeinterlaceTech_BOBVerticalStretch, DXVA_DeinterlaceTech_BOBVerticalStretch4Tap, DXVA_DeinterlaceTech_EdgeFiltering, DXVA_DeinterlaceTech_FieldAdaptive, DXVA_DeinterlaceTech_MedianFiltering, DXVA_DeinterlaceTech_MotionVectorSteered, DXVA_DeinterlaceTech_PixelAdaptive, DXVA_DeinterlaceTech_Unknown, _DXVA_DeinterlaceTech, display.dxva_deinterlacetech, dxva/DXVA_DeinterlaceTech, dxva/DXVA_DeinterlaceTech_BOBLineReplicate, dxva/DXVA_DeinterlaceTech_BOBVerticalStretch, dxva/DXVA_DeinterlaceTech_BOBVerticalStretch4Tap, dxva/DXVA_DeinterlaceTech_EdgeFiltering, dxva/DXVA_DeinterlaceTech_FieldAdaptive, dxva/DXVA_DeinterlaceTech_MedianFiltering, dxva/DXVA_DeinterlaceTech_MotionVectorSteered, dxva/DXVA_DeinterlaceTech_PixelAdaptive, dxva/DXVA_DeinterlaceTech_Unknown, dxvaref_ce829a5b-1e09-43e6-b90c-f7501476f280.xml
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
targetos: Windows
req.typenames: DXVA_DeinterlaceTech
f1_keywords:
 - _DXVA_DeinterlaceTech
 - dxva/_DXVA_DeinterlaceTech
 - DXVA_DeinterlaceTech
 - dxva/DXVA_DeinterlaceTech
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - DXVA_DeinterlaceTech
---

# _DXVA_DeinterlaceTech enumeration


## -description

The DXVA_DeinterlaceTech enumeration identifies the underlying technology used to implement a particular deinterlace algorithm.

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

<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_deinterlacecaps">DXVA_DeinterlaceCaps</a>