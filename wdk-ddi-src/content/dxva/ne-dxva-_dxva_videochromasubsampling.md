---
UID: NE:dxva._DXVA_VideoChromaSubsampling
title: _DXVA_VideoChromaSubsampling (dxva.h)
description: The DXVA_VideoChromaSubsampling enumeration type contains enumerators that identify the chroma encoding scheme for Y'Cb'Cr' data.
old-location: display\dxva_videochromasubsampling.htm
tech.root: display
ms.assetid: aa8f736f-1311-4217-8750-cdd134c6945c
ms.date: 05/10/2018
keywords: ["DXVA_VideoChromaSubsampling enumeration"]
ms.keywords: DXVA_VideoChromaSubsampling, DXVA_VideoChromaSubsampling enumeration [Display Devices], DXVA_VideoChromaSubsamplingMask, DXVA_VideoChromaSubsamplingShift, DXVA_VideoChromaSubsampling_Cosited, DXVA_VideoChromaSubsampling_DV_PAL, DXVA_VideoChromaSubsampling_Horizontally_Cosited, DXVA_VideoChromaSubsampling_MPEG1, DXVA_VideoChromaSubsampling_MPEG2, DXVA_VideoChromaSubsampling_ProgressiveChroma, DXVA_VideoChromaSubsampling_Unknown, DXVA_VideoChromaSubsampling_Vertically_AlignedChromaPlanes, DXVA_VideoChromaSubsampling_Vertically_Cosited, _DXVA_VideoChromaSubsampling, display.dxva_videochromasubsampling, dxva/DXVA_VideoChromaSubsampling, dxva/DXVA_VideoChromaSubsamplingMask, dxva/DXVA_VideoChromaSubsamplingShift, dxva/DXVA_VideoChromaSubsampling_Cosited, dxva/DXVA_VideoChromaSubsampling_DV_PAL, dxva/DXVA_VideoChromaSubsampling_Horizontally_Cosited, dxva/DXVA_VideoChromaSubsampling_MPEG1, dxva/DXVA_VideoChromaSubsampling_MPEG2, dxva/DXVA_VideoChromaSubsampling_ProgressiveChroma, dxva/DXVA_VideoChromaSubsampling_Unknown, dxva/DXVA_VideoChromaSubsampling_Vertically_AlignedChromaPlanes, dxva/DXVA_VideoChromaSubsampling_Vertically_Cosited, dxvaref_2939ec96-fb1f-4911-916e-40d043bb58d5.xml
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
req.typenames: DXVA_VideoChromaSubsampling
f1_keywords:
 - _DXVA_VideoChromaSubsampling
 - dxva/_DXVA_VideoChromaSubsampling
 - DXVA_VideoChromaSubsampling
 - dxva/DXVA_VideoChromaSubsampling
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - DXVA_VideoChromaSubsampling
---

# _DXVA_VideoChromaSubsampling enumeration


## -description

The DXVA_VideoChromaSubsampling enumeration type contains enumerators that identify the chroma encoding scheme for Y'Cb'Cr' data.

## -enum-fields

### -field DXVA_VideoChromaSubsamplingShift

Specifies to shift bits by 8 positions (DXVA_ExtColorData_ShiftBase + 0, or 8 + 0).

### -field DXVA_VideoChromaSubsamplingMask

Specifies the video chroma subsampling mask. 4 (0x00000F00) bits of a DWORD can be used to specify video chroma subsampling.

### -field DXVA_VideoChromaSubsampling_Unknown

Specifies that the video chroma subsampling is not specified.

### -field DXVA_VideoChromaSubsampling_ProgressiveChroma

Specifies that the video chroma subsampling is progressive chroma.

### -field DXVA_VideoChromaSubsampling_Horizontally_Cosited

Specifies that chroma samples are aligned on multiples of the luma samples horizontally.

### -field DXVA_VideoChromaSubsampling_Vertically_Cosited

Specifies that chroma samples are aligned on multiples of the luma samples vertically.

### -field DXVA_VideoChromaSubsampling_Vertically_AlignedChromaPlanes

Specifies that the Pb and Pr (or Cb and Cr) planes have the same phase alignment. This enumerator can only be set to 0 in the <b>VideoChromaSubsampling</b> member of the <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat">DXVA_ExtendedFormat</a> structure if the data is vertically cosited.

### -field DXVA_VideoChromaSubsampling_MPEG2

A bitwise OR of the DXVA_VideoChromaSubsampling_Horizontally_Cosited and DXVA_VideoChromaSubsampling_Vertically_AlignedChromaPlanes values that are used with 4:2:0 data.

### -field DXVA_VideoChromaSubsampling_MPEG1

The DXVA_VideoChromaSubsampling_Vertically_AlignedChromaPlanes value that is used with 4:2:0 data.

### -field DXVA_VideoChromaSubsampling_DV_PAL

A bitwise OR of the DXVA_VideoChromaSubsampling_Horizontally_Cosited and DXVA_VideoChromaSubsampling_Vertically_Cosited values that are used with 4:2:0 data.

### -field DXVA_VideoChromaSubsampling_Cosited

A bitwise OR of the DXVA_VideoChromaSubsampling_Horizontally_Cosited, and DXVA_VideoChromaSubsampling_Vertically_Cosited, and DXVA_VideoChromaSubsampling_Vertically_AlignedChromaPlanes values that are used with 4:4:4, 4:2:2, and 4:1:1 data.

## -remarks

The enumerators of DXVA_VideoChromaSubsampling can be ORed together to create a value in the <b>VideoChromaSubsampling</b> member of the <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat">DXVA_ExtendedFormat</a> structure.

Cosite variations indicate that the chroma samples are aligned with the luma samples. Typically, 4:2:0 data with chroma is aligned in one or more directions with the luma data. Note that 4:4:4, 4:2:2 and 4:1:1 data are always cosited in both directions.

## -see-also

<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat">DXVA_ExtendedFormat</a>