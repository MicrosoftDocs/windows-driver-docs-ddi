---
UID: NS:d3dumddi._D3DDDIARG_SETPALETTE
title: "_D3DDDIARG_SETPALETTE"
author: windows-driver-content
description: The D3DDDIARG_SETPALETTE structure describes how to associate a palette with a texture.
old-location: display\d3dddiarg_setpalette.htm
old-project: display
ms.assetid: 265912e2-2076-4435-811f-70a3dd1a0bd7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddiarg_setpalette, D3DDDIARG_SETPALETTE structure [Display Devices], d3dumddi/D3DDDIARG_SETPALETTE, UMDisplayDriver_param_Structs_6fb950bf-0a0f-4d87-950d-7030251ed074.xml, _D3DDDIARG_SETPALETTE, D3DDDIARG_SETPALETTE
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
-	D3DDDIARG_SETPALETTE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETPALETTE
---

# _D3DDDIARG_SETPALETTE structure


## -description


The D3DDDIARG_SETPALETTE structure describes how to associate a palette with a texture. 


## -syntax


````
typedef struct _D3DDDIARG_SETPALETTE {
  UINT   PaletteHandle;
  UINT   PaletteFlags;
  HANDLE hResource;
} D3DDDIARG_SETPALETTE;
````


## -struct-fields




### -field PaletteHandle

[in] A handle to the palette to be set up. If the value of <b>PaletteHandle</b> is zero, the surface that is specified by <b>hResource</b> should be uncoupled from any palette that it might have been associated with previously.


### -field PaletteFlags

[in] A valid bitwise OR of the following flags that specify the attributes of the palette.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DDDISETPALETTE_256 (0x00000001)

</td>
<td>
The palette has 256 entries.

</td>
</tr>
<tr>
<td>
D3DDDISETPALETTE_ALLOW256 (0x00000200)

</td>
<td>
The palette can be fully updated.

</td>
</tr>
<tr>
<td>
D3DDDISETPALETTE_ALPHA (0x00002000)

</td>
<td>
The palette's alpha data channel is valid and should be used.

</td>
</tr>
</table> 


### -field hResource

[in] A handle to the surface (texture) with which the palette that is identified by <b>PaletteHandle</b> is associated.


## -remarks


The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpalette.md">SetPalette</a> function associates the palette that is specified by the <b>PaletteHandle</b> member with the surface that is specified by the <b>hResource</b> member and uses the <b>PaletteFlags</b> member to specify the characteristics of the palette.



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpalette.md">SetPalette</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETPALETTE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

