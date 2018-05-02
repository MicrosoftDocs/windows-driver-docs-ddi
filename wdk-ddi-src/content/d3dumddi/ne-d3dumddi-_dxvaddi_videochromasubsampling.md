---
UID: NE:d3dumddi._DXVADDI_VIDEOCHROMASUBSAMPLING
title: "_DXVADDI_VIDEOCHROMASUBSAMPLING"
author: windows-driver-content
description: The DXVADDI_VIDEOCHROMASUBSAMPLING enumeration type contains values that identify the chroma encoding scheme for Y'Cb'Cr' data.
old-location: display\dxvaddi_videochromasubsampling.htm
old-project: display
ms.assetid: 697b6ac2-9d25-42ad-aac5-44754f19bf2c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXVA2_Structs_19b84102-b287-43e4-87e5-98bcc8b2bec8.xml, DXVADDI_VIDEOCHROMASUBSAMPLING, DXVADDI_VIDEOCHROMASUBSAMPLING enumeration [Display Devices], DXVADDI_VideoChromaSubsamplingMask, DXVADDI_VideoChromaSubsampling_Cosited, DXVADDI_VideoChromaSubsampling_DV_PAL, DXVADDI_VideoChromaSubsampling_Horizontally_Cosited, DXVADDI_VideoChromaSubsampling_MPEG1, DXVADDI_VideoChromaSubsampling_MPEG2, DXVADDI_VideoChromaSubsampling_ProgressiveChroma, DXVADDI_VideoChromaSubsampling_Unknown, DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes, DXVADDI_VideoChromaSubsampling_Vertically_Cosited, _DXVADDI_VIDEOCHROMASUBSAMPLING, d3dumddi/DXVADDI_VIDEOCHROMASUBSAMPLING, d3dumddi/DXVADDI_VideoChromaSubsamplingMask, d3dumddi/DXVADDI_VideoChromaSubsampling_Cosited, d3dumddi/DXVADDI_VideoChromaSubsampling_DV_PAL, d3dumddi/DXVADDI_VideoChromaSubsampling_Horizontally_Cosited, d3dumddi/DXVADDI_VideoChromaSubsampling_MPEG1, d3dumddi/DXVADDI_VideoChromaSubsampling_MPEG2, d3dumddi/DXVADDI_VideoChromaSubsampling_ProgressiveChroma, d3dumddi/DXVADDI_VideoChromaSubsampling_Unknown, d3dumddi/DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes, d3dumddi/DXVADDI_VideoChromaSubsampling_Vertically_Cosited, display.dxvaddi_videochromasubsampling
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	DXVADDI_VIDEOCHROMASUBSAMPLING
product: Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOCHROMASUBSAMPLING
---

# _DXVADDI_VIDEOCHROMASUBSAMPLING enumeration


## -description


The DXVADDI_VIDEOCHROMASUBSAMPLING enumeration type contains values that identify the chroma encoding scheme for Y'Cb'Cr' data. 


## -enum-fields




### -field DXVADDI_VideoChromaSubsamplingMask

The video chroma subsampling mask. The first four (0x0F) bits of a DWORD can be used to specify video chroma subsampling.


### -field DXVADDI_VideoChromaSubsampling_Unknown

The video chroma subsampling is not specified.


### -field DXVADDI_VideoChromaSubsampling_ProgressiveChroma

The video chroma subsampling is progressive.


### -field DXVADDI_VideoChromaSubsampling_Horizontally_Cosited

Chroma samples are aligned on multiples of the luma samples horizontally.


### -field DXVADDI_VideoChromaSubsampling_Vertically_Cosited

Chroma samples are aligned on multiples of the luma samples vertically.


### -field DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes

The Pb and Pr (or Cb and Cr) planes have the same phase alignment. This value can be set only to 0 in the <b>VideoChromaSubsampling</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a> structure if the data is vertically cosited.


### -field DXVADDI_VideoChromaSubsampling_MPEG2

A bitwise OR of the <b>DXVADDI_VideoChromaSubsampling_Horizontally_Cosited</b> and <b>DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes</b> values that are used with 4:2:0 data.


### -field DXVADDI_VideoChromaSubsampling_MPEG1

The <b>DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes</b> value that is used with 4:2:0 data.


### -field DXVADDI_VideoChromaSubsampling_DV_PAL

A bitwise OR of the <b>DXVADDI_VideoChromaSubsampling_Horizontally_Cosited</b> and <b>DXVADDI_VideoChromaSubsampling_Vertically_Cosited</b> values that are used with 4:2:0 data.


### -field DXVADDI_VideoChromaSubsampling_Cosited

A bitwise OR of the <b>DXVADDI_VideoChromaSubsampling_Horizontally_Cosited</b>, and <b>DXVADDI_VideoChromaSubsampling_Vertically_Cosited</b>, and <b>DXVADDI_VideoChromaSubsampling_Vertically_AlignedChromaPlanes</b> values that are used with 4:4:4, 4:2:2, and 4:1:1 data.


## -remarks



A bitwise OR of the values of DXVADDI_VIDEOCHROMASUBSAMPLING can be used to create a value in the <b>VideoChromaSubsampling</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a> structure.

Cosite variations indicate that the chroma samples are aligned with the luma samples. Typically, 4:2:0 data with chroma is aligned in one or more directions with the luma data. Note that 4:4:4, 4:2:2, and 4:1:1 data are always cosited in both directions. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a>
 

 

