---
UID: NS:d3dkmddi._DXGKARG_SETPOINTERSHAPE
title: "_DXGKARG_SETPOINTERSHAPE"
author: windows-driver-content
description: The DXGKARG_SETPOINTERSHAPE structure describes the appearance of the mouse pointer and the location that it should be displayed in.
old-location: display\dxgkarg_setpointershape.htm
old-project: display
ms.assetid: fcb06620-8a30-4980-8733-35d7aabcc872
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKARG_SETPOINTERSHAPE, DmStructs_9fab674a-0138-4c55-b17e-87cb85110325.xml, d3dkmddi/DXGKARG_SETPOINTERSHAPE, display.dxgkarg_setpointershape, DXGKARG_SETPOINTERSHAPE structure [Display Devices], _DXGKARG_SETPOINTERSHAPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_SETPOINTERSHAPE
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETPOINTERSHAPE
---

# _DXGKARG_SETPOINTERSHAPE structure


## -description


The DXGKARG_SETPOINTERSHAPE structure describes the appearance of the mouse pointer and the location that it should be displayed in. 


## -syntax


````
typedef struct _DXGKARG_SETPOINTERSHAPE {
  DXGK_POINTERFLAGS              Flags;
  UINT                           Width;
  UINT                           Height;
  UINT                           Pitch;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  const VOID                     *pPixels;
  UINT                           XHot;
  UINT                           YHot;
} DXGKARG_SETPOINTERSHAPE;
````


## -struct-fields




### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_pointerflags.md">DXGK_POINTERFLAGS</a> structure that identifies, in bit-field flags, how to display the mouse pointer.


### -field Width

[in] The width of the mouse pointer, in pixels.


### -field Height

[in] The height of the mouse pointer, in scan lines.


### -field Pitch

[in] The width of the mouse pointer, in bytes.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the mouse pointer is located in. 


### -field pPixels

[in] A pointer to the start of the following bitmap depending on the bit-field flag that is set in the <b>Flags</b> member:

<table>
<tr>
<th>Bit-field flag</th>
<th>Bitmap</th>
</tr>
<tr>
<td>
<b>Monochrome</b>

</td>
<td>

<dl>
<dt>For monochrome mouse pointers:</dt>
<dt>A monochrome bitmap whose size is specified by <b>Width</b> and <b>Height</b> in a 1 bits per pixel (bpp) DIB format AND mask that is followed by another 1 bpp DIB format XOR mask of the same size.</dt>
</dl>


</td>
</tr>
<tr>
<td>
<b>Color</b>

</td>
<td>

<dl>
<dt>For color mouse pointers:</dt>
<dt>A color bitmap whose size is specified by <b>Width</b> and <b>Height</b> in a 32 bpp ARGB device independent bitmap (DIB) format.</dt>
</dl>


</td>
</tr>
<tr>
<td>
<b>MaskedColor</b>

</td>
<td>

<dl>
<dt>For masked color mouse pointers:</dt>
<dt>A 32-bpp ARGB format bitmap with the mask value in the alpha bits. The only allowed mask values are 0 and 0xFF. When the mask value is 0, the RGB value should replace the screen pixel. When the mask value is 0xFF, an XOR operation is performed on the RGB value and the screen pixel; the result should replace the screen pixel.</dt>
</dl>


</td>
</tr>
</table>
 


### -field XHot

[in] The column, in pixels, that the mouse pointer is located on from the top left of the bitmap that <b>pPixels</b> points to. 


### -field YHot

[in] The row, in pixels, that the mouse pointer is located on from the top left of the bitmap that <b>pPixels</b> points to.


## -remarks



The <b>XHot</b> and <b>YHot</b> members are used by display miniport drivers that are not associated with hardware, and these members can be ignored by drivers that control hardware. 




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_pointerflags.md">DXGK_POINTERFLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointershape.md">DxgkDdiSetPointerShape</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_SETPOINTERSHAPE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

