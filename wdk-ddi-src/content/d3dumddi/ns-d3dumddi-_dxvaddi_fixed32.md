---
UID: NS:d3dumddi._DXVADDI_FIXED32
title: _DXVADDI_FIXED32 (d3dumddi.h)
description: The DXVADDI_FIXED32 structure describes a floating-point number from a 16.16 fixed-point number.
old-location: display\dxvaddi_fixed32.htm
tech.root: display
ms.assetid: 4188c488-fda4-4596-96f5-f740a5cc9ffc
ms.date: 05/10/2018
keywords: ["_DXVADDI_FIXED32 structure"]
ms.keywords: DXVA2_Structs_3d19835e-9a75-4d5a-bd6b-451a9978eadb.xml, DXVADDI_FIXED32, DXVADDI_FIXED32 structure [Display Devices], _DXVADDI_FIXED32, d3dumddi/DXVADDI_FIXED32, display.dxvaddi_fixed32
f1_keywords:
 - "d3dumddi/DXVADDI_FIXED32"
 - "DXVADDI_FIXED32"
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
- DXVADDI_FIXED32
targetos: Windows
req.typenames: DXVADDI_FIXED32
---

# _DXVADDI_FIXED32 structure


## -description


The DXVADDI_FIXED32 structure describes a floating-point number from a 16.16 fixed-point number. 


## -struct-fields




### -field Fraction

[in] A USHORT value that specifies the 16 bits after the decimal point.


### -field Value

[in] A SHORT value that specifies the 16 bits before the decimal point. 


### -field ll

A 32-bit value that describes the 16.16 fixed-point number.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_procampvalues">DXVADDI_PROCAMPVALUES</a>
 

 

