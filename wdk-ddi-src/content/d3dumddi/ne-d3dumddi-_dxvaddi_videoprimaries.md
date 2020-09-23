---
UID: NE:d3dumddi._DXVADDI_VIDEOPRIMARIES
title: _DXVADDI_VIDEOPRIMARIES (d3dumddi.h)
description: The DXVADDI_VIDEOPRIMARIES enumeration type contains values that identify the color primaries, which state which RGB basis functions are used.
old-location: display\dxvaddi_videoprimaries.htm
tech.root: display
ms.assetid: d7049f38-78a7-42bf-a1a5-5d35fe70ae15
ms.date: 05/10/2018
keywords: ["DXVADDI_VIDEOPRIMARIES enumeration"]
ms.keywords: DXVA2_Structs_f49dc977-3cb9-41b6-bb0c-a2de5e6a60c3.xml, DXVADDI_VIDEOPRIMARIES, DXVADDI_VIDEOPRIMARIES enumeration [Display Devices], DXVADDI_VideoPrimariesMask, DXVADDI_VideoPrimaries_BT470_2_SysBG, DXVADDI_VideoPrimaries_BT470_2_SysM, DXVADDI_VideoPrimaries_BT709, DXVADDI_VideoPrimaries_EBU3213, DXVADDI_VideoPrimaries_SMPTE170M, DXVADDI_VideoPrimaries_SMPTE240M, DXVADDI_VideoPrimaries_SMPTE_C, DXVADDI_VideoPrimaries_Unknown, DXVADDI_VideoPrimaries_reserved, _DXVADDI_VIDEOPRIMARIES, d3dumddi/DXVADDI_VIDEOPRIMARIES, d3dumddi/DXVADDI_VideoPrimariesMask, d3dumddi/DXVADDI_VideoPrimaries_BT470_2_SysBG, d3dumddi/DXVADDI_VideoPrimaries_BT470_2_SysM, d3dumddi/DXVADDI_VideoPrimaries_BT709, d3dumddi/DXVADDI_VideoPrimaries_EBU3213, d3dumddi/DXVADDI_VideoPrimaries_SMPTE170M, d3dumddi/DXVADDI_VideoPrimaries_SMPTE240M, d3dumddi/DXVADDI_VideoPrimaries_SMPTE_C, d3dumddi/DXVADDI_VideoPrimaries_Unknown, d3dumddi/DXVADDI_VideoPrimaries_reserved, display.dxvaddi_videoprimaries
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
targetos: Windows
req.typenames: DXVADDI_VIDEOPRIMARIES
f1_keywords:
 - _DXVADDI_VIDEOPRIMARIES
 - d3dumddi/_DXVADDI_VIDEOPRIMARIES
 - DXVADDI_VIDEOPRIMARIES
 - d3dumddi/DXVADDI_VIDEOPRIMARIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVADDI_VIDEOPRIMARIES
---

# _DXVADDI_VIDEOPRIMARIES enumeration


## -description

The DXVADDI_VIDEOPRIMARIES enumeration type contains values that identify the color primaries, which state which RGB basis functions are used.

## -enum-fields

### -field DXVADDI_VideoPrimariesMask

Specifies the color primaries mask. The first 5 (0x001F) bits of a DWORD can be used to specify color primaries.

### -field DXVADDI_VideoPrimaries_Unknown

Specifies that color primaries are not specified. The default is BT709.

### -field DXVADDI_VideoPrimaries_reserved

[in] Reserved. Do not use this value.

### -field DXVADDI_VideoPrimaries_BT709

Specifies BT709 primaries (including sRGB and scRGB).

### -field DXVADDI_VideoPrimaries_BT470_2_SysM

Specifies BT470-2 SysM primaries, which are the original NTSC primaries.

### -field DXVADDI_VideoPrimaries_BT470_2_SysBG

Specifies BT470-2 SysBG primaries.

### -field DXVADDI_VideoPrimaries_SMPTE170M

Specifies SMPTE170M primaries, which are rarely used analog NTSC primaries (also known as SMPTE RP 145).

### -field DXVADDI_VideoPrimaries_SMPTE240M

Specifies SMPTE240M primaries.

### -field DXVADDI_VideoPrimaries_EBU3213

Specifies EBU3213 primaries.

### -field DXVADDI_VideoPrimaries_SMPTE_C

Specifies SMPTE_C primaries, which are analog '79 NTSC primaries.

## -remarks

One of the values of DXVADDI_VIDEOPRIMARIES can be specified in the <b>VideoPrimaries</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a>