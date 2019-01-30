---
UID: NS:dxva._DXVA_PicResample
title: "_DXVA_PicResample" (dxva.h)
description: The DXVA_PicResample structure is sent by the host decoder to the accelerator to control the resampling process. This process is invoked when the bDXVA_Func variable is equal to 4.
old-location: display\dxva_picresample.htm
tech.root: display
ms.assetid: 29b26400-9b27-4bff-9c7e-d612d250da30
ms.date: 05/10/2018
ms.keywords: "*LPDXVA_PicResample, DXVA_PicResample, DXVA_PicResample structure [Display Devices], LPDXVA_PicResample, LPDXVA_PicResample structure pointer [Display Devices], _DXVA_PicResample, display.dxva_picresample, dxva/DXVA_PicResample, dxva/LPDXVA_PicResample, dxvaref_523256d7-10ef-4750-a065-bd4bb02c1fbe.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_PicResample
product:
- Windows
targetos: Windows
req.typenames: DXVA_PicResample, *LPDXVA_PicResample
---

# _DXVA_PicResample structure


## -description


The DXVA_PicResample structure is sent by the host decoder to the accelerator to control the resampling process. This process is invoked when the <a href="https://msdn.microsoft.com/6db9fa71-7bc2-4eb6-afcb-b16df48f7e8b">bDXVA_Func variable</a> is equal to 4.


## -struct-fields




### -field wPicResampleSourcePicIndex

Specifies the reference buffer to be resampled. 


### -field wPicResampleDestPicIndex

Specifies the buffer to be used for the output of the reference picture resampling operation.


### -field wPicResampleRcontrol

Specifies the rounding mode for averaging in the resampling operation. In the case of H.263 Annex O Spatial Scalability, this member is 1. (This corresponds to the value of <i>RCRPR</i> in H.263 Annex P that is equivalent to the upsampling needed for H.263 Annex O spatial scalability.) In the case of H.263 Annex P Reference Picture Resampling, this value is equal to the H.263 variable <i>RCRPR</i>


### -field bPicResampleExtrapWidth

Indicates if horizontal resampling must include padding of the resampled picture. If nonzero and the padding method of using motion vectors over picture boundaries is used on the accelerator, any resampling must include padding of the resampled picture. This padding must cover at least the specified width around each edge of the resampled picture regardless of the resampling operation that is performed.


### -field bPicResampleExtrapHeight

Indicates if vertical resampling must include padding of the resampled picture. If nonzero and the padding method of using motion vectors over picture boundaries is used on the accelerator, any resampling must include padding of the resampled picture. This padding must cover at least the specified height around each edge of the resampled picture regardless of the resampling operation that is performed.


### -field dwPicResampleSourceWidth

Specifies the width in units of luminance samples of the area of the source picture to be resampled to the destination picture.


### -field dwPicResampleSourceHeight

Specifies the height of the area of the source picture, in units of luminance samples to be resampled to the destination picture.


### -field dwPicResampleDestWidth

Specifies the width of the area of the destination picture, in units of luminance samples to contain the resampled data from the source picture. 


### -field dwPicResampleDestHeight

Specifies the height of the area of the destination picture in units of luminance samples to contain the resampled data from the source picture. 


### -field dwPicResampleFullDestWidth

Specifies the full width of the area of the destination picture in units of luminance samples to contain the resampled data from the source picture. 


### -field dwPicResampleFullDestHeight

Specifies the full height of the area of the destination picture in units of luminance samples to contain the resampled data from the source picture.


## -remarks



The clipping performed by <b>dwPicResampleFullDestHeight</b> is used to generate any samples outside the source resampling area. (This value is necessary for H.263 Annex P support of custom source formats in which the luminance width or height is not divisible by 16.)

In the case of H.263 Annex O Spatial Scalability, the value of <b>wPicResampleRcontrol </b>is 1. This value corresponds to the value of <i>RCRPR</i> in H.263 Annex P that is equivalent to the upsampling needed for H.263 Annex O spatial scalability. In the case of H.263 Annex P Reference Picture Resampling, <b>wPicResampleRcontrol</b> is equal to the H.263 variable <i>RCRPR</i>.



