---
UID: NE:dxva._DXVA_DestinationFlags
title: _DXVA_DestinationFlags (dxva.h)
description: The DXVA_DestinationFlags enumeration type contains a collection of flags that identify changes in the current destination surface from the previous destination surface.
old-location: display\dxva_destinationflags.htm
tech.root: display
ms.assetid: 842c6ece-5304-428c-afbe-2990d239f38a
ms.date: 05/10/2018
keywords: ["_DXVA_DestinationFlags enumeration"]
ms.keywords: DXVA_DestinationFlagMask, DXVA_DestinationFlag_Alpha_Changed, DXVA_DestinationFlag_Background_Changed, DXVA_DestinationFlag_ColorData_Changed, DXVA_DestinationFlag_TargetRect_Changed, DXVA_DestinationFlags, DXVA_DestinationFlags enumeration [Display Devices], _DXVA_DestinationFlags, display.dxva_destinationflags, dxva/DXVA_DestinationFlagMask, dxva/DXVA_DestinationFlag_Alpha_Changed, dxva/DXVA_DestinationFlag_Background_Changed, dxva/DXVA_DestinationFlag_ColorData_Changed, dxva/DXVA_DestinationFlag_TargetRect_Changed, dxva/DXVA_DestinationFlags, dxvaref_f18a38b4-531e-4c7c-bd77-e4c0d581f86d.xml
f1_keywords:
 - "dxva/DXVA_DestinationFlags"
 - "DXVA_DestinationFlags"
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
- DXVA_DestinationFlags
product:
- Windows
targetos: Windows
req.typenames: DXVA_DestinationFlags
---

# _DXVA_DestinationFlags enumeration


## -description


The DXVA_DestinationFlags enumeration type contains a collection of flags that identify changes in the current destination surface from the previous destination surface.


## -enum-fields




### -field DXVA_DestinationFlagMask

Specifies the destination-flag mask, which consists of the first 4 bits of a DWORD.


### -field DXVA_DestinationFlag_Background_Changed

Indicates that the background color of the destination surface changed. 


### -field DXVA_DestinationFlag_TargetRect_Changed

Indicates that the target rectangle of the destination surface changed. 


### -field DXVA_DestinationFlag_ColorData_Changed

Indicates that format information for the destination surface changed. 



### -field DXVA_DestinationFlag_Alpha_Changed

Indicates that the planar alpha value for the destination surface changed.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_deinterlacebltex">DXVA_DeinterlaceBltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a>
 

 

