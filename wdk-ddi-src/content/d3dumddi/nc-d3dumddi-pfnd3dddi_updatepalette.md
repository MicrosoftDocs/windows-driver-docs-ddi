---
UID: NC:d3dumddi.PFND3DDDI_UPDATEPALETTE
title: PFND3DDDI_UPDATEPALETTE (d3dumddi.h)
description: The UpdatePalette function updates a texture palette.
old-location: display\updatepalette.htm
tech.root: display
ms.assetid: 7c22e0c9-cc24-4398-88b7-c91855cbc731
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_UPDATEPALETTE, PFND3DDDI_UPDATEPALETTE callback, UpdatePalette, UpdatePalette callback function [Display Devices], UserModeDisplayDriver_Functions_d3b21e65-68dc-44d9-b5b3-96f37588965e.xml, d3dumddi/UpdatePalette, display.updatepalette
f1_keywords:
 - "d3dumddi/UpdatePalette"
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
- UpdatePalette
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_UPDATEPALETTE callback function


## -description


The <i>UpdatePalette</i> function updates a texture palette.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param Arg2


*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_updatepalette">D3DDDIARG_UPDATEPALETTE</a> structure that describes parameters for the palette-update operation.

### -param Arg3

*pPaletteData* [in]

An array of PALETTEENTRY structures to update. For more information about PALETTEENTRY, see the Microsoft Windows SDK documentation.


## -returns



<i>UpdatePalette</i> returns S_OK or an appropriate error result if the texture palette is not successfully updated.




## -remarks



The palette data in the array that is specified by <i>pPaletteData</i> consists of one UINT value for each palette entry (PALETTEENTRY structure). The palette entry is in ARGB format, with 8 bits for each of the four channels.

The user-mode display driver uses the following members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_updatepalette">D3DDDIARG_UPDATEPALETTE</a> structure that is pointed to by <i>pData</i> to update the texture palette: 

<ul>
<li>
The <b>PaletteHandle</b> member specifies the handle to the palette that is associated with the surface.

</li>
<li>
The <b>StartIndex</b> member specifies the index of the entry in the array at <i>pPaletteData</i> where the update should start.

</li>
<li>
The <b>NumEntries</b> member specifies the number of entries in the array at <i>pPaletteData</i> to update.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_updatepalette">D3DDDIARG_UPDATEPALETTE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

