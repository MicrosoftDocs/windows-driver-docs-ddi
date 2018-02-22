---
UID: NE:dxva._DXVA_VideoLighting
title: "_DXVA_VideoLighting"
author: windows-driver-content
description: The DXVA_VideoLighting enumeration type contains enumerators that identify lighting conditions for viewing video.
old-location: display\dxva_videolighting.htm
old-project: display
ms.assetid: 09adfa3f-443b-4500-bb08-27f91da20778
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DXVA_VideoLighting_bright, dxva/DXVA_VideoLighting_dim, DXVA_VideoLightingMask, dxva/DXVA_VideoLightingMask, DXVA_VideoLighting_Unknown, dxva/DXVA_VideoLightingShift, dxva/DXVA_VideoLighting_Unknown, dxva/DXVA_VideoLighting_office, DXVA_VideoLighting_office, DXVA_VideoLighting_dim, DXVA_VideoLighting_dark, DXVA_VideoLightingShift, DXVA_VideoLighting, _DXVA_VideoLighting, display.dxva_videolighting, DXVA_VideoLighting enumeration [Display Devices], dxva/DXVA_VideoLighting_dark, dxva/DXVA_VideoLighting, dxvaref_c223ad8d-6e70-4672-b286-292a7e36d6f7.xml, dxva/DXVA_VideoLighting_bright
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
-	DXVA_VideoLighting
product: Windows
targetos: Windows
req.typenames: DXVA_VideoLighting
---

# _DXVA_VideoLighting enumeration


## -description


The DXVA_VideoLighting enumeration type contains enumerators that identify lighting conditions for viewing video.


## -syntax


````
typedef enum _DXVA_VideoLighting { 
  DXVA_VideoLightingShift     = (DXVA_ExtColorData_ShiftBase + 10),
  DXVA_VideoLightingMask      = DXVAColorMask(4, DXVA_VideoLightingShift),
  DXVA_VideoLighting_Unknown  = 0,
  DXVA_VideoLighting_bright   = 1,
  DXVA_VideoLighting_office   = 2,
  DXVA_VideoLighting_dim      = 3,
  DXVA_VideoLighting_dark     = 4
} DXVA_VideoLighting;
````


## -enum-fields




### -field DXVA_VideoLightingShift

Specifies to shift bits by 18 positions (DXVA_ExtColorData_ShiftBase + 10, or 8 + 10).


### -field DXVA_VideoLightingMask

Specifies the video lighting mask. 4 (0x003C0000) bits of a DWORD can be used to specify video lighting.


### -field DXVA_VideoLighting_Unknown

Specifies that the video lighting condition is not specified. The default is dim.


### -field DXVA_VideoLighting_bright

Specifies bright light for viewing video (for example, outside lighting conditions).


### -field DXVA_VideoLighting_office

Specifies a medium brightness light for viewing video (for example, lighting conditions in home offices).


### -field DXVA_VideoLighting_dim

Specifies a dim light for viewing video (for example, low-level lighting in a living room while watching television). 


### -field DXVA_VideoLighting_dark

Specifies near darkness for viewing video (for example, movie-theatre lighting).


## -remarks



One of the enumerators of DXVA_VideoLighting can be specified in the <b>VideoLighting</b> member of the <a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a> structure.

The video lighting enumerators can be used to alter the gamma to generate a comparable experience in a different lighting condition. 




## -see-also

<a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoLighting enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

