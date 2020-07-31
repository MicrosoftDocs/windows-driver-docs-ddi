---
UID: NE:d3dumddi._DXVADDI_NOMINALRANGE
title: _DXVADDI_NOMINALRANGE (d3dumddi.h)
description: The DXVADDI_NOMINALRANGE enumeration type contains values that identify whether sample data includes headroom (that is, values beyond 1.0 white) and toeroom (that is, superblacks below the reference 0.0 black).
old-location: display\dxvaddi_nominalrange.htm
tech.root: display
ms.assetid: f3f5fac9-013c-4739-a29e-c781b34e5289
ms.date: 05/10/2018
keywords: ["_DXVADDI_NOMINALRANGE enumeration"]
ms.keywords: DXVA2_Structs_fee8e221-64df-474a-a178-439365c683fd.xml, DXVADDI_NOMINALRANGE, DXVADDI_NOMINALRANGE enumeration [Display Devices], DXVADDI_NominalRangeMask, DXVADDI_NominalRange_0_255, DXVADDI_NominalRange_16_235, DXVADDI_NominalRange_48_208, DXVADDI_NominalRange_Normal, DXVADDI_NominalRange_Unknown, DXVADDI_NominalRange_Wide, _DXVADDI_NOMINALRANGE, d3dumddi/DXVADDI_NOMINALRANGE, d3dumddi/DXVADDI_NominalRangeMask, d3dumddi/DXVADDI_NominalRange_0_255, d3dumddi/DXVADDI_NominalRange_16_235, d3dumddi/DXVADDI_NominalRange_48_208, d3dumddi/DXVADDI_NominalRange_Normal, d3dumddi/DXVADDI_NominalRange_Unknown, d3dumddi/DXVADDI_NominalRange_Wide, display.dxvaddi_nominalrange
f1_keywords:
 - "d3dumddi/DXVADDI_NOMINALRANGE"
 - "DXVADDI_NOMINALRANGE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- DXVADDI_NOMINALRANGE
targetos: Windows
req.typenames: DXVADDI_NOMINALRANGE
---

# _DXVADDI_NOMINALRANGE enumeration


## -description


The DXVADDI_NOMINALRANGE enumeration type contains values that identify whether sample data includes headroom (that is, values beyond 1.0 white) and toeroom (that is, superblacks below the reference 0.0 black). 


## -enum-fields




### -field DXVADDI_NominalRangeMask

The nominal range mask. The first 3 (0x07) bits of a DWORD can be used to specify nominal range.


### -field DXVADDI_NominalRange_Unknown

The nominal range is not specified.


### -field DXVADDI_NominalRange_Normal

Normalized chroma [0..1] maps to [0..255] for 8-bit or [0..1023] for 10-bit.


### -field DXVADDI_NominalRange_Wide

Normalized chroma [0..1] maps to [16..235] for 8-bit or [64..940] for 10-bit.


### -field DXVADDI_NominalRange_0_255

Normalized chroma [0..1] maps explicitly to [0..255] for 8-bit.


### -field DXVADDI_NominalRange_16_235

Normalized chroma [0..1] maps explicitly to [16..235] for 8-bit.


### -field DXVADDI_NominalRange_48_208

Normalized chroma [0..1] maps explicitly to [48..208] for 8-bit.


## -remarks



One of the values of DXVADDI_NOMINALRANGE can be specified in the <b>NominalRange</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a> structure.

Wide gamut R'G'B' (that is, blackpoint at 16,16,16 and whitepoint at 235,235,235) must be differentiated from normal <a href="https://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a>
 

 

