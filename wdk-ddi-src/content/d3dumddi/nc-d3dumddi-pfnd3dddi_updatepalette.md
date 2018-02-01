---
UID: NC:d3dumddi.PFND3DDDI_UPDATEPALETTE
title: PFND3DDDI_UPDATEPALETTE
author: windows-driver-content
description: The UpdatePalette function updates a texture palette.
old-location: display\updatepalette.htm
old-project: display
ms.assetid: 7c22e0c9-cc24-4398-88b7-c91855cbc731
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.updatepalette, UpdatePalette callback function [Display Devices], UpdatePalette, PFND3DDDI_UPDATEPALETTE, PFND3DDDI_UPDATEPALETTE, d3dumddi/UpdatePalette, UserModeDisplayDriver_Functions_d3b21e65-68dc-44d9-b5b3-96f37588965e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	UpdatePalette
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_UPDATEPALETTE callback


## -description


The <i>UpdatePalette</i> function updates a texture palette.


## -prototype


````
PFND3DDDI_UPDATEPALETTE UpdatePalette;

__checkReturn HRESULT APIENTRY UpdatePalette(
  _In_       HANDLE                  hDevice,
  _In_ const D3DDDIARG_UPDATEPALETTE *pData,
  _In_ const PALETTEENTRY            *pPaletteData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_updatepalette.md">D3DDDIARG_UPDATEPALETTE</a> structure that describes parameters for the palette-update operation.


#### - pPaletteData [in]

 An array of PALETTEENTRY structures to update. For more information about PALETTEENTRY, see the Microsoft Windows SDK documentation.


## -returns


<i>UpdatePalette</i> returns S_OK or an appropriate error result if the texture palette is not successfully updated.



## -remarks


The palette data in the array that is specified by <i>pPaletteData</i> consists of one UINT value for each palette entry (PALETTEENTRY structure). The palette entry is in ARGB format, with 8 bits for each of the four channels.

The user-mode display driver uses the following members of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_updatepalette.md">D3DDDIARG_UPDATEPALETTE</a> structure that is pointed to by <i>pData</i> to update the texture palette: 
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

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_updatepalette.md">D3DDDIARG_UPDATEPALETTE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UPDATEPALETTE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

