---
UID: NS:d3dumddi._DXVADDI_DECODEBUFFERDESC
title: _DXVADDI_DECODEBUFFERDESC (d3dumddi.h)
description: The DXVADDI_DECODEBUFFERDESC structure describes a buffer that is currently passed from the host decoder to the accelerator.
old-location: display\dxvaddi_decodebufferdesc.htm
tech.root: display
ms.assetid: 809b4cf8-e4c5-4cb6-b58f-8b6b98111361
ms.date: 05/10/2018
keywords: ["DXVADDI_DECODEBUFFERDESC structure"]
ms.keywords: DXVA2_Structs_0946584e-3d1f-4bb4-95d5-7ae2c669814a.xml, DXVADDI_DECODEBUFFERDESC, DXVADDI_DECODEBUFFERDESC structure [Display Devices], _DXVADDI_DECODEBUFFERDESC, d3dumddi/DXVADDI_DECODEBUFFERDESC, display.dxvaddi_decodebufferdesc
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
targetos: Windows
req.typenames: DXVADDI_DECODEBUFFERDESC
f1_keywords:
 - _DXVADDI_DECODEBUFFERDESC
 - d3dumddi/_DXVADDI_DECODEBUFFERDESC
 - DXVADDI_DECODEBUFFERDESC
 - d3dumddi/DXVADDI_DECODEBUFFERDESC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVADDI_DECODEBUFFERDESC
---

# _DXVADDI_DECODEBUFFERDESC structure


## -description

The DXVADDI_DECODEBUFFERDESC structure describes a buffer that is currently passed from the host decoder to the accelerator.

## -struct-fields

### -field hBuffer

[in] A handle to the buffer.

### -field CompressedBufferType

[in] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the buffer.

### -field BufferIndex

[in] Reserved. Do not use this member. For more information, see the Remarks section.

### -field DataOffset

[in] The offset of the relevant data from the beginning of the buffer, in bytes. The use of this member is currently restricted to the value zero.

### -field DataSize

[in] The amount of relevant data in the buffer, in bytes. The location of the last byte of content in the buffer is the value of <b>DataOffset</b> plus the value of <b>DataSize</b> minus 1.

### -field FirstMBaddress

[in] The macroblock address of the first macroblock in the buffer that is passed to the accelerator. The macroblock address is given in raster scan order. The address is determined by the members of the <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a> structure. The following table shows examples of macroblock addresses.

| **Macroblock** | **Address** | 
|:--|:--|
| Top-left | Zero | 
| Top-right | wPicWidthInMBminus1 of DXVA_PictureParameters. | 
| Bottom-left | wPicHeightInMBminus1 x (wPicWidthInMBminus1+1). Members of DXVA_PictureParameters. | 
| Bottom-right | (wPicHeightInMBminus1+1) x (wPicWidthInMBminus1+1)-1. Members of DXVA_PictureParame | 


The <b>FirstMBaddress</b> member must be zero if the data buffer is one of the following types: picture decoding parameters, inverse-quantization matrix, slice control, bitstream data, AYUV, IA44/AI44, DPXD, Highlight, and DCCMD.

If the data buffer is a residual difference block data buffer, <b>FirstMBaddress</b> must have the same value as for the corresponding macroblock control command buffer.

### -field NumMBsInBuffer

[in] The number of macroblocks of data in the buffer, including skipped macroblocks. This member must be zero if the data buffer is one of the following types: picture decoding parameters, inverse-quantization matrix, AYUV, IA44/AI44, DPXD, Highlight, or DCCMD.

The value for <b>NumMBsInBuffer</b> depends on the type of data buffer that is being used, as shown in the following table.

| **Buffer type** | **Value of NumMBsInBuffer** | 
|:--|:--|
| Macroblock control command | The sum of all of the values for MBskipsFollowing, added to the number of macroblock control commands in the macroblock control command buffer. | 
| Residual difference block | The same value as for the corresponding macroblock control command buffer. | 
| Slice-control command | The value of the wNumberMBsInSlice member of the [DXVA_SliceInfo](../dxva/ns-dxva-_dxva_sliceinfo.md)  structure in the slice-control buffer. | 
| Bitstream | The same value as for the corresponding slice-control command buffer. |

### -field Width

[in] Reserved. Do not use this member. For more information, see the Remarks section.

### -field Height

[in] Reserved. Do not use this member. For more information, see the Remarks section.

### -field Stride

[in] Reserved. Do not use this member. For more information, see the Remarks section.

### -field ReservedBits

[in] Reserved bits that are used for packing and alignment. This member must be zero.

### -field pCipherCounter

[in] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_pvp_hw_iv">DXVADDI_PVP_HW_IV</a> structure that contains a 128-bit protected video path (PVP) value.

## -remarks

An array of DXVADDI_DECODEBUFFERDESC structures is referred to as a <i>buffer description list</i>. When a set of buffers is sent from the host decoder to the hardware accelerator, a buffer description list is sent to describe the buffers. The buffer description list contains one DXVADDI_DECODEBUFFERDESC structure for each buffer in this set. The buffer description list starts with a DXVADDI_DECODEBUFFERDESC structure for the first buffer of the first type, followed by a DXVADDI_DECODEBUFFERDESC structure for the next buffer of the same type, and so on. The buffer description list then continues with a DXVADDI_DECODEBUFFERDESC structure for the first buffer of the next type, and so on. This entire list is contained in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decodeexecute">D3DDDIARG_DECODEEXECUTE</a> structure.

Because Microsoft DirectX Video Acceleration (VA) version 2.0 uses Microsoft Direct3D surfaces rather than the private surfaces that DirectX VA 1.0 uses, the user-mode display driver obtains values for the index, width, height, and stride from the given compressed buffer type rather than from the values in the <b>BufferIndex</b>, <b>Width</b>, <b>Height</b>, and <b>Stride</b> members. In fact, the Microsoft Direct3D runtime sets these members to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decodeexecute">D3DDDIARG_DECODEEXECUTE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_pvp_hw_iv">DXVADDI_PVP_HW_IV</a>



<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a>



<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_sliceinfo">DXVA_SliceInfo</a>