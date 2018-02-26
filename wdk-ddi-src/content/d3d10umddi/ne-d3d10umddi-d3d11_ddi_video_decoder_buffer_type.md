---
UID: NE:d3d10umddi.D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE
title: D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE
author: windows-driver-content
description: Contains values that indicate the buffer type used by the video decoder.
old-location: display\d3d11_ddi_video_decoder_buffer_type.htm
old-project: display
ms.assetid: 71d624ba-bac6-4055-a772-fe2280a9ee16
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 1, 3, B, C, D, D3D11_1DDI_VIDEO_DECODER_BUFFER_BITSTREAM, D3D11_1DDI_VIDEO_DECODER_BUFFER_DEBLOCKING_CONTROL, D3D11_1DDI_VIDEO_DECODER_BUFFER_FILM_GRAIN, D3D11_1DDI_VIDEO_DECODER_BUFFER_INVERSE_QUANTIZATION_MATRIX, D3D11_1DDI_VIDEO_DECODER_BUFFER_MACROBLOCK_CONTROL, D3D11_1DDI_VIDEO_DECODER_BUFFER_MOTION_VECTOR, D3D11_1DDI_VIDEO_DECODER_BUFFER_PICTURE_PARAMETERS, D3D11_1DDI_VIDEO_DECODER_BUFFER_RESIDUAL_DIFFERENCE, D3D11_1DDI_VIDEO_DECODER_BUFFER_SLICE_CONTROL, D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE, D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE enumeration [Display Devices], D3D11_1DDI_VIDEO_DECODER_BUFFER_UNKNOWN, D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE, D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE enumeration [Display Devices], E, F, I, O, P, R, T, U, V, Y, _, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_BITSTREAM, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_DEBLOCKING_CONTROL, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_FILM_GRAIN, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_INVERSE_QUANTIZATION_MATRIX, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_MACROBLOCK_CONTROL, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_MOTION_VECTOR, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_PICTURE_PARAMETERS, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_RESIDUAL_DIFFERENCE, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_SLICE_CONTROL, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_UNKNOWN, d3d10umddi/D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE, display.d3d11_ddi_video_decoder_buffer_type"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	d3d10umddi.h
apiname:
-	D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE
---

# D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE enumeration


## -description


Contains values that indicate the  buffer type used by the video decoder.


## -syntax


````
typedef enum D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE { 
  D3D11_1DDI_VIDEO_DECODER_BUFFER_UNKNOWN                      = 0,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_PICTURE_PARAMETERS           = 1,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_MACROBLOCK_CONTROL           = 2,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_RESIDUAL_DIFFERENCE          = 3,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_DEBLOCKING_CONTROL           = 4,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_INVERSE_QUANTIZATION_MATRIX  = 5,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_SLICE_CONTROL                = 6,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_BITSTREAM                    = 7,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_MOTION_VECTOR                = 8,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_FILM_GRAIN                   = 9
} D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE;
````


## -enum-fields




### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_UNKNOWN

An unknown buffer format.


### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_PICTURE_PARAMETERS

Picture parameters decode compressed buffer format.


### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_MACROBLOCK_CONTROL

Macroblock control command decode compressed buffer format.


### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_RESIDUAL_DIFFERENCE

Residual block difference decode compressed buffer format.


### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_DEBLOCKING_CONTROL

Deblocking filter control command decode compressed buffer format.


### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_INVERSE_QUANTIZATION_MATRIX

Inverse-quantization matrix decode compressed buffer format.


### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_SLICE_CONTROL

Slice-control decode compressed buffer format.


### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_BITSTREAM

Bitstream data decode compressed buffer format.


### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_MOTION_VECTOR

Motion-vector decode compressed buffer format.


### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_FILM_GRAIN

Film-grain decode compressed buffer format.


## -remarks



Note that the <b>D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</b> and <b>D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE</b> enumerations are defined as the same type.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createresource.md">D3D11DDIARG_CREATERESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

