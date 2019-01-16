---
UID: NC:d3dumddi.PFND3DDDI_SETPALETTE
title: PFND3DDDI_SETPALETTE
description: The SetPalette function associates a palette with a texture.
old-location: display\setpalette.htm
tech.root: display
ms.assetid: 5d1c8c2d-7886-4876-b48e-1e6b252ae8f7
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETPALETTE, PFND3DDDI_SETPALETTE callback, SetPalette, SetPalette callback function [Display Devices], UserModeDisplayDriver_Functions_9366fa90-a9d7-4c03-9c96-a8bc4eba6abb.xml, d3dumddi/SetPalette, display.setpalette
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetPalette
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETPALETTE callback function


## -description


The <i>SetPalette</i> function associates a palette with a texture.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543327">D3DDDIARG_SETPALETTE</a> structure that describes the parameters for the set-palette operation.


## -returns



<i>SetPalette</i> returns S_OK or an appropriate error result if the palette is not successfully associated with the texture.




## -remarks



The user-mode display driver uses the members in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543327">D3DDDIARG_SETPALETTE</a> structure that is pointed to by <i>pData</i> to map an association between a palette handle and a surface handle and to specify the characteristics of the palette.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543327">D3DDDIARG_SETPALETTE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

