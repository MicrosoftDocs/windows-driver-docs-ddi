---
UID: NS:d3dumddi._DXVADDI_VALUERANGE
title: "_DXVADDI_VALUERANGE"
author: windows-driver-content
description: The DXVADDI_VALUERANGE structure describes values of a property (such as, the value spread and default value).
old-location: display\dxvaddi_valuerange.htm
old-project: display
ms.assetid: c3013da9-8db4-4346-9be8-77b2c6de3f59
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXVA2_Structs_37c2cd52-30c3-4e99-918f-6a538547bdd2.xml, DXVADDI_VALUERANGE, DXVADDI_VALUERANGE structure [Display Devices], _DXVADDI_VALUERANGE, d3dumddi/DXVADDI_VALUERANGE, display.dxvaddi_valuerange
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVADDI_VALUERANGE
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

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562909">DXVADDI_FIXED32</a> structure that specifies the minimum value that is allowed for a given property.


### -field MaxValue

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562909">DXVADDI_FIXED32</a> structure that specifies the maximum value that is allowed for a given property.


### -field DefaultValue

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562909">DXVADDI_FIXED32</a> structure that specifies the default value for a given property.


### -field StepSize

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562909">DXVADDI_FIXED32</a> structure that specifies the step size increment for a given property.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562935">DXVADDI_QUERYPROCAMPINPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

