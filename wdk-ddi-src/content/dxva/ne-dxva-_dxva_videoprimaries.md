---
UID: NE:dxva._DXVA_VideoPrimaries
title: "_DXVA_VideoPrimaries"
author: windows-driver-content
description: The DXVA_VideoPrimaries enumeration type contains enumerators that identify the color primaries, which state which RGB basis functions are used.
old-location: display\dxva_videoprimaries.htm
old-project: display
ms.assetid: 8aa6ba31-aec0-4a92-ad0e-6c19b796e398
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dxva/DXVA_VideoPrimariesShift, _DXVA_VideoPrimaries, DXVA_VideoPrimaries_Unknown, dxva/DXVA_VideoPrimaries_Unknown, dxva/DXVA_VideoPrimaries_BT470_2_SysBG, DXVA_VideoPrimaries_BT709, DXVA_VideoPrimaries_BT470_2_SysBG, dxva/DXVA_VideoPrimaries_BT709, DXVA_VideoPrimaries_SMPTE240M, dxva/DXVA_VideoPrimaries, DXVA_VideoPrimariesShift, DXVA_VideoPrimaries_SMPTE170M, dxva/DXVA_VideoPrimariesMask, dxva/DXVA_VideoPrimaries_reserved, dxva/DXVA_VideoPrimaries_SMPTE240M, DXVA_VideoPrimaries_BT470_2_SysM, display.dxva_videoprimaries, DXVA_VideoPrimaries enumeration [Display Devices], dxva/DXVA_VideoPrimaries_EBU3213, dxva/DXVA_VideoPrimaries_SMPTE_C, DXVA_VideoPrimaries, dxvaref_c0e5c7be-4039-438c-a883-30bb242a5c50.xml, DXVA_VideoPrimariesMask, dxva/DXVA_VideoPrimaries_BT470_2_SysM, DXVA_VideoPrimaries_SMPTE_C, dxva/DXVA_VideoPrimaries_SMPTE170M, DXVA_VideoPrimaries_EBU3213, DXVA_VideoPrimaries_reserved
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxva.h
apiname:
-	DXVA_VideoPrimaries
product: Windows
targetos: Windows
req.typenames: DXVA_VideoPrimaries
---

# _DXVA_VideoPrimaries enumeration


## -description


The DXVA_VideoPrimaries enumeration type contains enumerators that identify the color primaries, which state which RGB basis functions are used.


## -syntax


````
typedef enum _DXVA_VideoPrimaries { 
  DXVA_VideoPrimariesShift           = (DXVA_ExtColorData_ShiftBase + 14),
  DXVA_VideoPrimariesMask            = DXVAColorMask(5, DXVA_VideoPrimariesShift),
  DXVA_VideoPrimaries_Unknown        = 0,
  DXVA_VideoPrimaries_reserved       = 1,
  DXVA_VideoPrimaries_BT709          = 2,
  DXVA_VideoPrimaries_BT470_2_SysM   = 3,
  DXVA_VideoPrimaries_BT470_2_SysBG  = 4,
  DXVA_VideoPrimaries_SMPTE170M      = 5,
  DXVA_VideoPrimaries_SMPTE240M      = 6,
  DXVA_VideoPrimaries_EBU3213        = 7,
  DXVA_VideoPrimaries_SMPTE_C        = 8
} DXVA_VideoPrimaries;
````


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



One of the enumerators of DXVA_VideoPrimaries can be specified in the <b>VideoPrimaries</b> member of the <a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a> structure.




## -see-also

<a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoPrimaries enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

