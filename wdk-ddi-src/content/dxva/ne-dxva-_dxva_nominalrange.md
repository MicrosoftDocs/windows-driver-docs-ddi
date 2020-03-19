---
UID: NE:dxva._DXVA_NominalRange
title: _DXVA_NominalRange (dxva.h)
description: The DXVA_NominalRange enumeration type contains enumerators that identify whether sample data includes headroom (values beyond 1.0 white) and toeroom (superblacks below the reference 0.0 black).
old-location: display\dxva_nominalrange.htm
tech.root: display
ms.assetid: 9e319f9d-4c24-4dd3-b5a1-b244714c06dc
ms.date: 05/10/2018
keywords: ["_DXVA_NominalRange enumeration"]
ms.keywords: DXVA_NominalRange, DXVA_NominalRange enumeration [Display Devices], DXVA_NominalRangeMask, DXVA_NominalRangeShift, DXVA_NominalRange_0_255, DXVA_NominalRange_16_235, DXVA_NominalRange_48_208, DXVA_NominalRange_Normal, DXVA_NominalRange_Unknown, DXVA_NominalRange_Wide, _DXVA_NominalRange, display.dxva_nominalrange, dxva/DXVA_NominalRange, dxva/DXVA_NominalRangeMask, dxva/DXVA_NominalRangeShift, dxva/DXVA_NominalRange_0_255, dxva/DXVA_NominalRange_16_235, dxva/DXVA_NominalRange_48_208, dxva/DXVA_NominalRange_Normal, dxva/DXVA_NominalRange_Unknown, dxva/DXVA_NominalRange_Wide, dxvaref_5931dd2e-baac-48a6-931a-b7f3fc965b4d.xml
f1_keywords:
 - "dxva/DXVA_NominalRange"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_NominalRange
product:
- Windows
targetos: Windows
req.typenames: DXVA_NominalRange
---

# _DXVA_NominalRange enumeration


## -description


The DXVA_NominalRange enumeration type contains enumerators that identify whether sample data includes headroom (values beyond 1.0 white) and toeroom (superblacks below the reference 0.0 black). 


## -enum-fields




### -field DXVA_NominalRangeShift

Specifies to shift bits by 12 positions (DXVA_ExtColorData_ShiftBase + 4, or 8 + 4).


### -field DXVA_NominalRangeMask

Specifies the nominal range mask. 3 (0x00007000) bits of a DWORD can be used to specify nominal range.


### -field DXVA_NominalRange_Unknown

Specifies that the nominal range is not specified.


### -field DXVA_NominalRange_Normal

Specifies that normalized chroma [0..1] maps to [0..255] for 8-bit or [0..1023] for 10-bit.


### -field DXVA_NominalRange_Wide

Specifies that normalized chroma [0..1] maps to [16..235] for 8-bit or [64..940] for 10-bit.


### -field DXVA_NominalRange_0_255

Specifies that normalized chroma [0..1] maps to [0..255] for 8-bit or [0..1023] for 10-bit.


### -field DXVA_NominalRange_16_235

Specifies that normalized chroma [0..1] maps to [16..235] for 8-bit or [64..940] for 10-bit.


### -field DXVA_NominalRange_48_208

Specifies that normalized chroma [0..1] maps to [48..208] for 8-bit or [192..832] for 10-bit.


## -remarks



One of the enumerators of DXVA_NominalRange can be specified in the <b>NominalRange</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat">DXVA_ExtendedFormat</a> structure.

Wide gamut R'G'B' (that is, blackpoint at 16,16,16 and whitepoint at 235,235,235) must be differentiated from normal <a href="https://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat">DXVA_ExtendedFormat</a>
 

 

