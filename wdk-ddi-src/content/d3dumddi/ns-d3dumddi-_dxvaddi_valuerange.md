---
UID: NS:d3dumddi._DXVADDI_VALUERANGE
title: _DXVADDI_VALUERANGE (d3dumddi.h)
description: The DXVADDI_VALUERANGE structure describes values of a property (such as, the value spread and default value).
old-location: display\dxvaddi_valuerange.htm
tech.root: display
ms.assetid: c3013da9-8db4-4346-9be8-77b2c6de3f59
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_37c2cd52-30c3-4e99-918f-6a538547bdd2.xml, DXVADDI_VALUERANGE, DXVADDI_VALUERANGE structure [Display Devices], _DXVADDI_VALUERANGE, d3dumddi/DXVADDI_VALUERANGE, display.dxvaddi_valuerange
ms.topic: struct
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
- DXVADDI_VALUERANGE
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_VALUERANGE
---

# _DXVADDI_VALUERANGE structure


## -description


The DXVADDI_VALUERANGE structure describes values of a property (such as, the value spread and default value).


## -struct-fields




### -field MinValue

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the minimum value that is allowed for a given property.


### -field MaxValue

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the maximum value that is allowed for a given property.


### -field DefaultValue

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the default value for a given property.


### -field StepSize

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the step size increment for a given property.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_queryprocampinput">DXVADDI_QUERYPROCAMPINPUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
 

 

