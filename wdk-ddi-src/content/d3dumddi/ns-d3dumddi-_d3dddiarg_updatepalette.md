---
UID: NS:d3dumddi._D3DDDIARG_UPDATEPALETTE
title: "_D3DDDIARG_UPDATEPALETTE"
author: windows-driver-content
description: The D3DDDIARG_UPDATEPALETTE structure describes parameters that are used to update a texture palette.
old-location: display\d3dddiarg_updatepalette.htm
old-project: display
ms.assetid: 6637c102-4e77-4030-9bb5-ab9fb4bac2c7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_UPDATEPALETTE, D3DDDIARG_UPDATEPALETTE structure [Display Devices], UMDisplayDriver_param_Structs_abbbfa0f-d2f6-4985-a189-56e4592c1c1e.xml, _D3DDDIARG_UPDATEPALETTE, d3dumddi/D3DDDIARG_UPDATEPALETTE, display.d3dddiarg_updatepalette
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
-	D3DDDIARG_UPDATEPALETTE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_UPDATEPALETTE
---

# _D3DDDIARG_UPDATEPALETTE structure


## -description


The D3DDDIARG_UPDATEPALETTE structure describes parameters that are used to update a texture palette. 


## -struct-fields




### -field PaletteHandle

[in] A handle to the palette to be altered.


### -field StartIndex

[in] The index in the palette beyond which data is updated. 


### -field NumEntries

[in] The number of PALETTEENTRY structures that are being updated. For more information about PALETTEENTRY, see the Microsoft Windows SDK documentation.


## -remarks



The Microsoft Direct3D runtime passes palette data for updating to the <i>pPaletteData</i> parameter in a call to the user-mode display driver's <a href="https://msdn.microsoft.com/7c22e0c9-cc24-4398-88b7-c91855cbc731">UpdatePalette</a> function. This palette data is an array of PALETTEENTRY structures.




## -see-also




<a href="https://msdn.microsoft.com/7c22e0c9-cc24-4398-88b7-c91855cbc731">UpdatePalette</a>
 

 

