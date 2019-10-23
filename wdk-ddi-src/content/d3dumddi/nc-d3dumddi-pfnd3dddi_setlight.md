---
UID: NC:d3dumddi.PFND3DDDI_SETLIGHT
title: PFND3DDDI_SETLIGHT (d3dumddi.h)
description: The SetLight function sets properties for a light source.
old-location: display\setlight.htm
tech.root: display
ms.assetid: 28e3992e-a636-47e2-a5a6-5da06d276b5c
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETLIGHT, PFND3DDDI_SETLIGHT callback, SetLight, SetLight callback function [Display Devices], UserModeDisplayDriver_Functions_82c42629-2344-4778-aaf4-e41acac4cfce.xml, d3dumddi/SetLight, display.setlight
ms.topic: callback
f1_keywords:
 - "d3dumddi/SetLight"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
- UserDefined
api_location:
- d3dumddi.h
api_name:
- SetLight
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETLIGHT callback function


## -description


The <i>SetLight</i> function sets properties for a light source.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param Arg2


*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setlight">D3DDDIARG_SETLIGHT</a> structure that describes how to set the light source.

### -param Arg3

*pLightProperties* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_light">D3DDDI_LIGHT</a> structure that describes the light properties to set.


## -returns



<i>SetLight</i> returns S_OK or an appropriate error result if the light properties are not successfully set.




## -remarks



Light properties describe the type and color of a light source. Depending on the type of light that is being used, a light can have properties for attenuation and range or for spotlight effects. However, not all types of lights will use all of the properties. For more information about light properties, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setlight">D3DDDIARG_SETLIGHT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_light">D3DDDI_LIGHT</a>
 

 

