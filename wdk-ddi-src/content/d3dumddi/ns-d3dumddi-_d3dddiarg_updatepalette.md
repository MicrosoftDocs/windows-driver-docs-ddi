---
UID: NS:d3dumddi._D3DDDIARG_UPDATEPALETTE
title: "_D3DDDIARG_UPDATEPALETTE"
author: windows-driver-content
description: The D3DDDIARG_UPDATEPALETTE structure describes parameters that are used to update a texture palette.
old-location: display\d3dddiarg_updatepalette.htm
old-project: display
ms.assetid: 6637c102-4e77-4030-9bb5-ab9fb4bac2c7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: UMDisplayDriver_param_Structs_abbbfa0f-d2f6-4985-a189-56e4592c1c1e.xml, D3DDDIARG_UPDATEPALETTE structure [Display Devices], display.d3dddiarg_updatepalette, _D3DDDIARG_UPDATEPALETTE, d3dumddi/D3DDDIARG_UPDATEPALETTE, D3DDDIARG_UPDATEPALETTE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_UPDATEPALETTE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_UPDATEPALETTE
---

# _D3DDDIARG_UPDATEPALETTE structure


## -description


The D3DDDIARG_UPDATEPALETTE structure describes parameters that are used to update a texture palette. 


## -syntax


````
typedef struct _D3DDDIARG_UPDATEPALETTE {
  UINT PaletteHandle;
  UINT StartIndex;
  UINT NumEntries;
} D3DDDIARG_UPDATEPALETTE;
````


## -struct-fields




### -field PaletteHandle

[in] A handle to the palette to be altered.


### -field StartIndex

[in] The index in the palette beyond which data is updated. 


### -field NumEntries

[in] The number of PALETTEENTRY structures that are being updated. For more information about PALETTEENTRY, see the Microsoft Windows SDK documentation.


## -remarks



The Microsoft Direct3D runtime passes palette data for updating to the <i>pPaletteData</i> parameter in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updatepalette.md">UpdatePalette</a> function. This palette data is an array of PALETTEENTRY structures.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updatepalette.md">UpdatePalette</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_UPDATEPALETTE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

