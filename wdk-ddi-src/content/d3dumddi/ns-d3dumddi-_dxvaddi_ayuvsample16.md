---
UID: NS:d3dumddi._DXVADDI_AYUVSAMPLE16
title: "_DXVADDI_AYUVSAMPLE16"
author: windows-driver-content
description: The DXVADDI_AYUVSAMPLE16 structure describes 16-bit Cr, Cb, and Y color values and an associated opacity.
old-location: display\dxvaddi_ayuvsample16.htm
old-project: display
ms.assetid: 9cd2e943-dc20-4c5c-ab5c-090463e0a88c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVADDI_AYUVSAMPLE16, display.dxvaddi_ayuvsample16, d3dumddi/DXVADDI_AYUVSAMPLE16, DXVA2_Structs_9e7fc230-f50c-4a07-b1cb-358694dc207d.xml, DXVADDI_AYUVSAMPLE16 structure [Display Devices], _DXVADDI_AYUVSAMPLE16
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
-	DXVADDI_AYUVSAMPLE16
product: Windows
targetos: Windows
req.typenames: DXVADDI_AYUVSAMPLE16
---

# _DXVADDI_AYUVSAMPLE16 structure


## -description


The DXVADDI_AYUVSAMPLE16 structure describes 16-bit Cr, Cb, and Y color values and an associated opacity.


## -syntax


````
typedef struct _DXVADDI_AYUVSAMPLE16 {
  USHORT Cr;
  USHORT Cb;
  USHORT Y;
  USHORT Alpha;
} DXVADDI_AYUVSAMPLE16;
````


## -struct-fields




### -field Cr

[in] A 16-bit chrominance (V) sample value.


### -field Cb

[in] A 16-bit chrominance (U) sample value.


### -field Y

[in] A 16-bit luminance (Y) sample value.


### -field Alpha

[in] The 16-bit opacity of the pixel when it is used as a source graphic for blending with another picture. 


## -remarks



A value of 0 in the <b>Alpha</b> member indicates that the pixel is transparent (so that the other entries have no effect on the resulting blended picture), and a value of 255 indicates that the pixel is opaque (so that the other entries completely determine the value of the resulting blended picture sample). 

For nonzero values of <b>Alpha</b>, the blend to use is calculated by the following expression:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>( ( ( (Alpha + 1) x (graphic value) ) + ( (255 - Alpha) x (picture value) ) )  + 128 ) &gt;&gt; 8</pre>
</td>
</tr>
</table></span></div>
If <b>Alpha</b> is 0, the specified blend to use is the picture value without alteration. 

The color value is scaled according to ITU-R Rec. BT.601, which you can learn about from the <a href="http://go.microsoft.com/fwlink/p/?linkid=8741">International Telecommunication Union</a> website. Therefore, the color black is nominally specified by Y=16, Cb=Cr=128, and the color white is nominally specified by Y=235, Cb=Cr=128.

<div class="alert"><b>Note</b>    If the alpha-blending surface originates as a DVD video subpicture, the preferred method for converting from the 4-bit alpha that is used by DVD video to the 8-bit alpha that is specified by <b>Alpha</b> is to map a 4-bit alpha value of zero to an 8-bit alpha value of zero and to convert all of the nonzero 4-bit alphas to 8-bit alphas by performing a left shift of four places and adding the constant 15.</div>
<div> </div>
The width and height of the AYUV alpha-blending surface are specified in the associated <a href="https://msdn.microsoft.com/7d820491-2df2-4036-8f3d-e6bcff4cd1f6">buffer description list</a> that is defined by the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodebufferdesc.md">DXVADDI_DECODEBUFFERDESC</a> structure.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videodesc.md">DXVADDI_VIDEODESC</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodebufferdesc.md">DXVADDI_DECODEBUFFERDESC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_AYUVSAMPLE16 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

