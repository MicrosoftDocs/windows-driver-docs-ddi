---
UID: NS:dxva._DXVA_ConfigAlphaCombine
title: "_DXVA_ConfigAlphaCombine"
author: windows-driver-content
description: The DXVA_ConfigAlphaCombine structure is sent by the host decoder to the accelerator to set the configuration for alpha-blending combination operations.
old-location: display\dxva_configalphacombine.htm
old-project: display
ms.assetid: 588d5e73-4ec2-486b-914f-7076949653ad
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*LPDXVA_ConfigAlphaCombine, DXVA_ConfigAlphaCombine, DXVA_ConfigAlphaCombine structure [Display Devices], LPDXVA_ConfigAlphaCombine, LPDXVA_ConfigAlphaCombine structure pointer [Display Devices], _DXVA_ConfigAlphaCombine, display.dxva_configalphacombine, dxva/DXVA_ConfigAlphaCombine, dxva/LPDXVA_ConfigAlphaCombine, dxvaref_3bd67a73-c786-412c-90ad-c546ae2e4645.xml"
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
-	DXVA_ConfigAlphaCombine
product: Windows
targetos: Windows
req.typenames: DXVA_ConfigAlphaCombine, *LPDXVA_ConfigAlphaCombine
---

# _DXVA_ConfigAlphaCombine structure


## -description


The DXVA_ConfigAlphaCombine structure is sent by the host decoder to the accelerator to set the configuration for alpha-blending combination operations.


## -syntax


````
typedef struct _DXVA_ConfigAlphaCombine {
  DXVA_ConfigQueryOrReplyFunc dwFunction;
  DWORD                       dwReservedBits[3];
  BYTE                        bConfigBlendType;
  BYTE                        bConfigPictureResizing;
  BYTE                        bConfigOnlyUsePicDestRectArea;
  BYTE                        bConfigGraphicResizing;
  BYTE                        bConfigWholePlaneAlpha;
} DXVA_ConfigAlphaCombine, *LPDXVA_ConfigAlphaCombine;
````


## -struct-fields




### -field dwFunction

Indicates the type of query or response when using probing and locking commands. The most significant 24 bits of <b>dwFunction</b> is the <a href="https://msdn.microsoft.com/bfb1a98e-b9f0-4baa-b486-b2ff33a8bac5">DXVA_ConfigQueryOrReplyFlag</a> variable.

The least significant 4 bits of the <i>DXVA_ConfigQueryOrReplyFlag</i> variable contain status indicators for the query or response being performed.

The least significant 8 bits of <b>dwFunction</b> is the <a href="https://msdn.microsoft.com/6db9fa71-7bc2-4eb6-afcb-b16df48f7e8b">bDXVA_Func variable</a> that, in this case, is equal to 3.


### -field dwReservedBits

Specifies the reserved bits used for packing and alignment. This member must be zero.


### -field bConfigBlendType

Specifies the type of alpha-blend combinations to be performed. Zero indicates front-end buffer-to-buffer blend, and 1 indicates back-end hardware blend.

The preferred value for an accelerator to support is zero.


### -field bConfigPictureResizing

Specifies whether the <b>PictureSourceRect16thPel</b> member of <a href="..\dxva\ns-dxva-_dxva_blendcombination.md">DXVA_BlendCombination</a> for graphic blending may differ in width and height from the <b>PictureDestinationRect</b> member of DXVA_BlendCombination (adjusted for the one-sixteenth sample scaling of <b>PictureSourceRect16thPel</b>). This member also specifies whether the values in <b>PictureSourceRect16thPel</b> are multiples of 16, thus requiring the source picture to be resampled by the accelerator. A value of 1 indicates that resampling (whether for resizing or for subpixel accuracy) is supported; a value of zero indicates that it is not.


### -field bConfigOnlyUsePicDestRectArea

Specifies whether the decoder can perform operations that use values for areas of a destination picture outside the area defined by the <b>PictureDestinationRect</b> member of the DXVA_BlendCombination structure. The value zero indicates that areas outside of <b>PictureDestinationRect</b> can be specified and displayed by the blend combination commands. The value 1 indicates that the decoder cannot rely on the values of, or display, any region of the blended surface outside of the area specified by <b>PictureDestinationRect</b>.


### -field bConfigGraphicResizing

Indicates whether alpha blending is supported in graphic image resizing. A value of 1 indicates that it is; a value of zero indicates that it is not. <b>bConfigGraphicResizing</b> specifies whether the <b>GraphicSourceRect</b> member of <a href="..\dxva\ns-dxva-_dxva_blendcombination.md">DXVA_BlendCombination</a> (for subpicture blending) may differ in size from the <b>GraphicDestinationRect</b> member of DXVA_BlendCombination. If these values are different, the alpha-blending graphic must be resampled by the accelerator.


### -field bConfigWholePlaneAlpha

Specifies whether a whole-plane alpha opacity value can be applied to the graphic image. A value of 1 indicates that a whole-plane alpha can be applied; a value of zero indicates that it cannot.


## -see-also

<a href="..\dxva\ns-dxva-_dxva_blendcombination.md">DXVA_BlendCombination</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_ConfigAlphaCombine structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

