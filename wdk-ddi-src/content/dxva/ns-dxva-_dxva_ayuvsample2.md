---
UID: NS:dxva._DXVA_AYUVsample2
title: "_DXVA_AYUVsample2"
author: windows-driver-content
description: The DXVA_AYUVsample2 structure is sent by the host decoder to the accelerator to specify Y, Cb, Cr color values, and an associated opacity.
old-location: display\dxva_ayuvsample2.htm
old-project: display
ms.assetid: 33e92f7d-2a01-4be2-a6b3-d0bd63db1eeb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: LPDXVA_AYUVsample2, DXVA_AYUVsample2 structure [Display Devices], dxvaref_15019e0c-708c-4d68-972b-d47b7e2b6514.xml, display.dxva_ayuvsample2, DXVA_AYUVsample2, _DXVA_AYUVsample2, dxva/LPDXVA_AYUVsample2, LPDXVA_AYUVsample2 structure pointer [Display Devices], dxva/DXVA_AYUVsample2, *LPDXVA_AYUVsample2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	dxva.h
apiname:
-	DXVA_AYUVsample2
product: Windows
targetos: Windows
req.typenames: "*LPDXVA_AYUVsample2, DXVA_AYUVsample2"
---

# _DXVA_AYUVsample2 structure


## -description


The DXVA_AYUVsample2 structure is sent by the host decoder to the accelerator to specify Y, Cb, Cr color values, and an associated opacity.


## -syntax


````
typedef struct _DXVA_AYUVsample2 {
  BYTE bCrValue;
  BYTE bCbValue;
  BYTE bY_Value;
  BYTE bSampleAlpha8;
} DXVA_AYUVsample2, *LPDXVA_AYUVsample2;
````


## -struct-fields




### -field bCrValue

Specifies a chrominance (Cr) sample value (scaled per ITU-R Rec. BT.601) as an unsigned value. Thus, the color black is nominally specified by Y=16, Cb=Cr=128, and the color white is nominally specified by Y=235, Cb=Cr=128.


### -field bCbValue

Specifies a chrominance (Cb) sample value (scaled per ITU-R Rec. BT.601) as an unsigned value. Thus, the color black is nominally specified by Y=16, Cb=Cr=128, and the color white is nominally specified by Y=235, Cb=Cr=128.


### -field bY_Value

Specifies a luminance (Y) sample value (scaled per ITU-R Rec. BT.601) as an unsigned value. Thus, the color black is nominally specified by Y=16, Cb=Cr=128, and the color white is nominally specified by Y=235, Cb=Cr=128.


### -field bSampleAlpha8

Specifies the opacity of the pixel when used as a source graphic for blending with another picture. For Windows Server 2003 SP1 and Windows XP SP2, the opacity level is not used and should be ignored by the driver.


## -remarks



A value of zero for <b>bSampleAlpha8</b> indicates that the pixel is transparent (so that the other entries have no effect on the resulting blended picture), and a value of 255 indicates that the pixel is opaque (so that the other entries completely determine the value of the resulting blended picture sample). 

For nonzero values of <b>bSampleAlpha8</b>, the blend to use is calculated by the following expression:

( ( ( (<b>bSampleAlpha8</b>+1) x (graphic value) ) + ( (255 - <b>bSampleAlpha8</b>) x (picture value) ) )  + 128 ) &gt;&gt; 8

For a zero value of <b>bSampleAlpha8</b>, the specified blend to use is the picture value without alteration. 

<div class="alert"><b>Note</b>    If the alpha-blending surface originates as a DVD video subpicture, the preferred method for converting from the 4-bit alpha used by DVD video to the 8-bit alpha specified by <b>bSampleAlpha8</b> is to map a 4-bit alpha value of zero to an 8-bit alpha value of zero and to convert all nonzero 4-bit alphas to 8-bit alphas by performing a left shift of four places and adding the constant 15.</div>
<div> </div>
The width and height of the AYUV alpha-blending surface are specified in the associated <a href="https://msdn.microsoft.com/7d820491-2df2-4036-8f3d-e6bcff4cd1f6">buffer description list</a> defined by the <a href="..\dxva\ns-dxva-_dxva_bufferdescription.md">DXVA_BufferDescription</a> structure.

The <b>DXVA_AYUVsample2</b> structure is used for each sample in a DirectX VA AYUV blending surface, for <b>OutsideYUVcolor</b> in a <a href="..\dxva\ns-dxva-_dxva_blendcombination.md">DXVA_BlendCombination</a> structure, and for each of the entries in a 16-entry AYUV alpha-blending palette.




## -see-also

<a href="..\dxva\ns-dxva-_dxva_blendcombination.md">DXVA_BlendCombination</a>



<a href="..\dxva\ns-dxva-_dxva_bufferdescription.md">DXVA_BufferDescription</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_AYUVsample2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

