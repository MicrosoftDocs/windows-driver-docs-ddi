---
UID: NS:dxva._DXVA_ConfigAlphaCombine
title: _DXVA_ConfigAlphaCombine (dxva.h)
description: The DXVA_ConfigAlphaCombine structure is sent by the host decoder to the accelerator to set the configuration for alpha-blending combination operations.
old-location: display\dxva_configalphacombine.htm
tech.root: display
ms.assetid: 588d5e73-4ec2-486b-914f-7076949653ad
ms.date: 05/10/2018
keywords: ["DXVA_ConfigAlphaCombine structure"]
ms.keywords: "*LPDXVA_ConfigAlphaCombine, DXVA_ConfigAlphaCombine, DXVA_ConfigAlphaCombine structure [Display Devices], LPDXVA_ConfigAlphaCombine, LPDXVA_ConfigAlphaCombine structure pointer [Display Devices], _DXVA_ConfigAlphaCombine, display.dxva_configalphacombine, dxva/DXVA_ConfigAlphaCombine, dxva/LPDXVA_ConfigAlphaCombine, dxvaref_3bd67a73-c786-412c-90ad-c546ae2e4645.xml"
f1_keywords:
 - "dxva/DXVA_ConfigAlphaCombine"
 - "DXVA_ConfigAlphaCombine"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_ConfigAlphaCombine
targetos: Windows
req.typenames: DXVA_ConfigAlphaCombine, *LPDXVA_ConfigAlphaCombine
---

# _DXVA_ConfigAlphaCombine structure


## -description


The DXVA_ConfigAlphaCombine structure is sent by the host decoder to the accelerator to set the configuration for alpha-blending combination operations.


## -struct-fields




### -field dwFunction

Indicates the type of query or response when using probing and locking commands. The most significant 24 bits of <b>dwFunction</b> is the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-configqueryorreplyflag-and-dxva-configqueryorreplyfunc-variables">DXVA_ConfigQueryOrReplyFlag</a> variable.

The least significant 4 bits of the <i>DXVA_ConfigQueryOrReplyFlag</i> variable contain status indicators for the query or response being performed.

The least significant 8 bits of <b>dwFunction</b> is the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/bdxva-func-variable">bDXVA_Func variable</a> that, in this case, is equal to 3.


### -field dwReservedBits

Specifies the reserved bits used for packing and alignment. This member must be zero.


### -field bConfigBlendType

Specifies the type of alpha-blend combinations to be performed. Zero indicates front-end buffer-to-buffer blend, and 1 indicates back-end hardware blend.

The preferred value for an accelerator to support is zero.


### -field bConfigPictureResizing

Specifies whether the <b>PictureSourceRect16thPel</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_blendcombination">DXVA_BlendCombination</a> for graphic blending may differ in width and height from the <b>PictureDestinationRect</b> member of DXVA_BlendCombination (adjusted for the one-sixteenth sample scaling of <b>PictureSourceRect16thPel</b>). This member also specifies whether the values in <b>PictureSourceRect16thPel</b> are multiples of 16, thus requiring the source picture to be resampled by the accelerator. A value of 1 indicates that resampling (whether for resizing or for subpixel accuracy) is supported; a value of zero indicates that it is not.


### -field bConfigOnlyUsePicDestRectArea

Specifies whether the decoder can perform operations that use values for areas of a destination picture outside the area defined by the <b>PictureDestinationRect</b> member of the DXVA_BlendCombination structure. The value zero indicates that areas outside of <b>PictureDestinationRect</b> can be specified and displayed by the blend combination commands. The value 1 indicates that the decoder cannot rely on the values of, or display, any region of the blended surface outside of the area specified by <b>PictureDestinationRect</b>.


### -field bConfigGraphicResizing

Indicates whether alpha blending is supported in graphic image resizing. A value of 1 indicates that it is; a value of zero indicates that it is not. <b>bConfigGraphicResizing</b> specifies whether the <b>GraphicSourceRect</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_blendcombination">DXVA_BlendCombination</a> (for subpicture blending) may differ in size from the <b>GraphicDestinationRect</b> member of DXVA_BlendCombination. If these values are different, the alpha-blending graphic must be resampled by the accelerator.


### -field bConfigWholePlaneAlpha

Specifies whether a whole-plane alpha opacity value can be applied to the graphic image. A value of 1 indicates that a whole-plane alpha can be applied; a value of zero indicates that it cannot.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_blendcombination">DXVA_BlendCombination</a>
 

 

