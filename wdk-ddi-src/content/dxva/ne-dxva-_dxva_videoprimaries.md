---
UID: NE:dxva._DXVA_VideoPrimaries
title: _DXVA_VideoPrimaries (dxva.h)
description: The DXVA_VideoPrimaries enumeration type contains enumerators that identify the color primaries, which state which RGB basis functions are used.
old-location: display\dxva_videoprimaries.htm
tech.root: display
ms.assetid: 8aa6ba31-aec0-4a92-ad0e-6c19b796e398
ms.date: 05/10/2018
keywords: ["_DXVA_VideoPrimaries enumeration"]
ms.keywords: DXVA_VideoPrimaries, DXVA_VideoPrimaries enumeration [Display Devices], DXVA_VideoPrimariesMask, DXVA_VideoPrimariesShift, DXVA_VideoPrimaries_BT470_2_SysBG, DXVA_VideoPrimaries_BT470_2_SysM, DXVA_VideoPrimaries_BT709, DXVA_VideoPrimaries_EBU3213, DXVA_VideoPrimaries_SMPTE170M, DXVA_VideoPrimaries_SMPTE240M, DXVA_VideoPrimaries_SMPTE_C, DXVA_VideoPrimaries_Unknown, DXVA_VideoPrimaries_reserved, _DXVA_VideoPrimaries, display.dxva_videoprimaries, dxva/DXVA_VideoPrimaries, dxva/DXVA_VideoPrimariesMask, dxva/DXVA_VideoPrimariesShift, dxva/DXVA_VideoPrimaries_BT470_2_SysBG, dxva/DXVA_VideoPrimaries_BT470_2_SysM, dxva/DXVA_VideoPrimaries_BT709, dxva/DXVA_VideoPrimaries_EBU3213, dxva/DXVA_VideoPrimaries_SMPTE170M, dxva/DXVA_VideoPrimaries_SMPTE240M, dxva/DXVA_VideoPrimaries_SMPTE_C, dxva/DXVA_VideoPrimaries_Unknown, dxva/DXVA_VideoPrimaries_reserved, dxvaref_c0e5c7be-4039-438c-a883-30bb242a5c50.xml
f1_keywords:
 - "dxva/DXVA_VideoPrimaries"
 - "DXVA_VideoPrimaries"
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
- DXVA_VideoPrimaries
product:
- Windows
targetos: Windows
req.typenames: DXVA_VideoPrimaries
---

# _DXVA_VideoPrimaries enumeration


## -description


The DXVA_VideoPrimaries enumeration type contains enumerators that identify the color primaries, which state which RGB basis functions are used.


## -enum-fields




### -field DXVA_VideoPrimariesShift

Specifies to shift bits by 22 positions (DXVA_ExtColorData_ShiftBase + 14, or 8 + 14).


### -field DXVA_VideoPrimariesMask

Specifies the color primaries mask. 5 (0x07C00000) bits of a DWORD can be used to specify color primaries.


### -field DXVA_VideoPrimaries_Unknown

Specifies that color primaries are not specified. The default is BT709.


### -field DXVA_VideoPrimaries_reserved

Reserved.


### -field DXVA_VideoPrimaries_BT709

Specifies BT709 primaries (including sRGB, scRGB).


### -field DXVA_VideoPrimaries_BT470_2_SysM

Specifies BT470-2 SysM primaries, which are the original NTSC primaries. 


### -field DXVA_VideoPrimaries_BT470_2_SysBG

Specifies BT470-2 SysBG primaries. 


### -field DXVA_VideoPrimaries_SMPTE170M

Specifies SMPTE170M primaries, which are rarely used analog NTSC primaries (also known as SMPTE RP 145).


### -field DXVA_VideoPrimaries_SMPTE240M

Specifies SMPTE240M primaries. 


### -field DXVA_VideoPrimaries_EBU3213

Specifies EBU3213 primaries. 


### -field DXVA_VideoPrimaries_SMPTE_C

Specifies SMPTE_C primaries, which are analog '79 NTSC primaries.


## -remarks



One of the enumerators of DXVA_VideoPrimaries can be specified in the <b>VideoPrimaries</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat">DXVA_ExtendedFormat</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat">DXVA_ExtendedFormat</a>
 

 

