---
UID: NS:dxva._DXVA_BufferDescription
title: _DXVA_BufferDescription (dxva.h)
description: The DXVA_BufferDescription structure is sent by the host decoder to the accelerator to provide information to the accelerator about the buffer that is currently being passed from the host to the accelerator.
old-location: display\dxva_bufferdescription.htm
tech.root: display
ms.assetid: 34b1585d-ceba-4e13-b5c1-70ce29a940c5
ms.date: 05/10/2018
keywords: ["_DXVA_BufferDescription structure"]
ms.keywords: "*LPDXVA_BufferDescription, DXVA_BufferDescription, DXVA_BufferDescription structure [Display Devices], LPDXVA_BufferDescription, LPDXVA_BufferDescription structure pointer [Display Devices], _DXVA_BufferDescription, display.dxva_bufferdescription, dxva/DXVA_BufferDescription, dxva/LPDXVA_BufferDescription, dxvaref_3d6f62c8-77a1-40b0-8bf3-1a82deaf3020.xml"
f1_keywords:
 - "dxva/DXVA_BufferDescription"
 - "DXVA_BufferDescription"
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
- DXVA_BufferDescription
targetos: Windows
req.typenames: DXVA_BufferDescription, *LPDXVA_BufferDescription
---

# _DXVA_BufferDescription structure


## -description


The DXVA_BufferDescription structure is sent by the host decoder to the accelerator to provide information to the accelerator about the buffer that is currently being passed from the host to the accelerator. 


## -struct-fields




### -field dwTypeIndex

Identifies the type of buffer passed to the accelerator. The following table lists the numeric identifiers and the associated buffer type.

| **Value** | **Buffer Type** | 
|:--|:--|
| 1 | Picture decoding parameter buffers. | 
| 2 | [Macroblock control command buffers](https://docs.microsoft.com/windows-hardware/drivers/display/macroblock-oriented-picture-decoding)  (closely associated with and having a 1:1 correspondence with residual difference block data buffers). | 
| 3 | Residual difference block data buffers. See [Macroblock-Oriented Picture Decoding](https://docs.microsoft.com/windows-hardware/drivers/display/macroblock-oriented-picture-decoding)  for more information. | 
| 4 | Deblocking filter control command buffers (with or without a restriction on the effect of the filter). | 
| 5 | Inverse-quantization matrix buffers (only used with off-host VLD processing). | 
| 6 | Slice-control buffers (closely associated with and having a 1:1 correspondence with bitstream data buffers). | 
| 7 | Bitstream data buffers. | 
| 8 | AYUV alpha-blending sample buffers. | 
| 9 | IA44/AI44 alpha-blending surface buffers. | 
| 10 | DPXD alpha-blending surface buffers. | 
| 11 | Highlight data buffers. | 
| 12 | DCCMD data buffers. | 
| 13 | Alpha-blend combination buffers. | 
| 14 | Picture resampling control buffers. | 
| 15 | Read-back command buffers containing commands to read macroblocks of the resulting picture back to the host. | 


### -field dwBufferIndex

Specifies the sequence number of the buffer within the buffers of the same type that were passed in the same <a href="https://docs.microsoft.com/windows-hardware/drivers/display/buffer-description-list">buffer description list</a>.


### -field dwDataOffset

Specifies the offset of the relevant data from the beginning of the buffer in bytes. The use of this member is currently restricted to the value zero. 


### -field dwDataSize

Specifies the amount of relevant data in the buffer in bytes. The location of the last byte of content in the buffer is <b>dwDataOffset</b>, plus <b>dwDataSize</b> minus 1.


### -field dwFirstMBaddress

Specifies the macroblock address of the first macroblock in the buffer passed to the accelerator. The macroblock address is given in raster scan order. The address is determined by the members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a>. Examples of macroblock addresses are as follows.

| **Macroblock** | **Address** | 
|:--|:--|
| top-left | zero | 
| top-right | **wPicWidthInMBminus1** | 
| lower-left | wPicHeightInMBminus1 x (wPicWidthInMBminus1+1) | 
| lower-right | (wPicHeightInMBminus1+1) x (wPicWidthInMBminus1+1)-1 | 


This member must be zero if the data buffer is among the following types: picture decoding parameters, inverse-quantization matrix, slice control, bitstream data, AYUV, IA44/AI44, DPXD, Highlight, and DCCMD.

If the data buffer is a residual difference block data buffer, <b>dwFirstMBaddress</b> must have the same value as for the corresponding macroblock control command buffer. See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/macroblock-oriented-picture-decoding">Macroblock-Oriented Picture Decoding</a> for more information.


### -field dwNumMBsInBuffer

Specifies the number of macroblocks of data in the buffer. This count includes skipped macroblocks. Must be zero if the data buffer is among the following types: picture decoding parameters, inverse-quantization matrix, AYUV, IA44/AI44, DPXD, Highlight, or DCCMD.

The value for <b>dwNumMBsInBuffer</b> depends on the type of data buffer being used as shown in the following table.

| **Buffer Type** | **Value of dwNumMBsInBuffer** | 
|:--|:--|
| Macroblock control command | Must be equal to the sum of all values for MBskipsFollowing, added to the number of macroblock control commands in the macroblock control command buffer. | 
| Residual difference block | Must have the same value as for the corresponding macroblock control command buffer. | 
| Slice-control command | Must be equal to the value of the wNumberMBsInSlice member of the [DXVA_SliceInfo](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_sliceinfo) structure in the slice-control buffer. | 
| Bitstream | Must have the same value as for the corresponding slice-control command buffer. | 



### -field dwWidth

Specifies the width of the data in the buffer as the number of units of bits for the following types of data: AYUV (data is specified in 32-bit units), IA44/AI44 (data is specified in 8-bit units), or DPXD (data is specified in 2-bit units). This member must be zero if the data buffer is not among the preceding types.


### -field dwHeight

Specifies the height of the data in the buffer as the number of units of bits for the following types of data: AYUV (data is specified in 32-bit units), IA44/AI44 (data is specified in 8-bit units), or DPXD (data is specified in 2-bit units).This member must be zero if the data buffer is not among the preceding types.


### -field dwStride

Specifies the stride of the data in the buffer as the number of units of bits for the following types of data: AYUV (data is specified in 32-bit units), IA44/AI44 (data is specified in 8-bit units), or DPXD (data is specified in 2-bit units). The stride for the applicable buffer types is determined from the buffer allocation setup performed by the accelerator. This member must be zero if the data buffer is not among the preceding types.


### -field dwReservedBits

Reserved bits used for packing and alignment. Must be zero.


## -remarks



An array of DXVA_BufferDescription structures is referred to as a buffer description list. When a set of buffers is sent from the host decoder to the hardware accelerator, a buffer description list is sent to describe the buffers. The buffer description list contains one DXVA_BufferDescription structure for each buffer in this set. The buffer description list starts with a DXVA_BufferDescription structure for the first buffer of the first type, followed by a DXVA_BufferDescription structure for the next buffer of the same type, and so on. The buffer description list then continues with a DXVA_BufferDescription structure for the first buffer of the next type, and so on.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_sliceinfo">DXVA_SliceInfo</a>
 

 

