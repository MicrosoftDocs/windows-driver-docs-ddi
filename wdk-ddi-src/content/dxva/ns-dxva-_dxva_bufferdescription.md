---
UID: NS:dxva._DXVA_BufferDescription
title: "_DXVA_BufferDescription"
author: windows-driver-content
description: The DXVA_BufferDescription structure is sent by the host decoder to the accelerator to provide information to the accelerator about the buffer that is currently being passed from the host to the accelerator.
old-location: display\dxva_bufferdescription.htm
old-project: display
ms.assetid: 34b1585d-ceba-4e13-b5c1-70ce29a940c5
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*LPDXVA_BufferDescription, DXVA_BufferDescription, DXVA_BufferDescription structure [Display Devices], LPDXVA_BufferDescription, LPDXVA_BufferDescription structure pointer [Display Devices], _DXVA_BufferDescription, display.dxva_bufferdescription, dxva/DXVA_BufferDescription, dxva/LPDXVA_BufferDescription, dxvaref_3d6f62c8-77a1-40b0-8bf3-1a82deaf3020.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_BufferDescription
product:
- Windows
targetos: Windows
req.typenames: DXVA_BufferDescription, *LPDXVA_BufferDescription
---

# _DXVA_BufferDescription structure


## -description


The DXVA_BufferDescription structure is sent by the host decoder to the accelerator to provide information to the accelerator about the buffer that is currently being passed from the host to the accelerator. 


## -struct-fields




### -field dwTypeIndex

Identifies the type of buffer passed to the accelerator. The following table lists the numeric identifiers and the associated buffer type.

<table>
<tr>
<th>Value </th>
<th>Buffer Type</th>
</tr>
<tr>
<td>
1

</td>
<td>
Picture decoding parameter buffers.

</td>
</tr>
<tr>
<td>
2

</td>
<td>

<a href="https://msdn.microsoft.com/7a416992-04d3-4307-83b3-9fb94c17d60e">Macroblock control command buffers</a> (closely associated with and having a 1:1 correspondence with residual difference block data buffers).

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Residual difference block data buffers. See <a href="https://msdn.microsoft.com/7a416992-04d3-4307-83b3-9fb94c17d60e">Macroblock-Oriented Picture Decoding</a> for more information.

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Deblocking filter control command buffers (with or without a restriction on the effect of the filter).

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Inverse-quantization matrix buffers (only used with off-host VLD processing).

</td>
</tr>
<tr>
<td>
6

</td>
<td>
Slice-control buffers (closely associated with and having a 1:1 correspondence with bitstream data buffers).

</td>
</tr>
<tr>
<td>
7

</td>
<td>
Bitstream data buffers.

</td>
</tr>
<tr>
<td>
8

</td>
<td>
AYUV alpha-blending sample buffers.

</td>
</tr>
<tr>
<td>
9

</td>
<td>
IA44/AI44 alpha-blending surface buffers.

</td>
</tr>
<tr>
<td>
10

</td>
<td>
DPXD alpha-blending surface buffers.

</td>
</tr>
<tr>
<td>
11

</td>
<td>
Highlight data buffers.

</td>
</tr>
<tr>
<td>
12

</td>
<td>
DCCMD data buffers.

</td>
</tr>
<tr>
<td>
13

</td>
<td>
Alpha-blend combination buffers.

</td>
</tr>
<tr>
<td>
14

</td>
<td>
Picture resampling control buffers.

</td>
</tr>
<tr>
<td>
15

</td>
<td>
Read-back command buffers containing commands to read macroblocks of the resulting picture back to the host.

</td>
</tr>
</table>
 


### -field dwBufferIndex

Specifies the sequence number of the buffer within the buffers of the same type that were passed in the same <a href="https://msdn.microsoft.com/7d820491-2df2-4036-8f3d-e6bcff4cd1f6">buffer description list</a>.


### -field dwDataOffset

Specifies the offset of the relevant data from the beginning of the buffer in bytes. The use of this member is currently restricted to the value zero. 


### -field dwDataSize

Specifies the amount of relevant data in the buffer in bytes. The location of the last byte of content in the buffer is <b>dwDataOffset</b>, plus <b>dwDataSize</b> minus 1.


### -field dwFirstMBaddress

Specifies the macroblock address of the first macroblock in the buffer passed to the accelerator. The macroblock address is given in raster scan order. The address is determined by the members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564012">DXVA_PictureParameters</a>. Examples of macroblock addresses are as follows.

<table>
<tr>
<th>Macroblock</th>
<th>Address </th>
</tr>
<tr>
<td>
top-left 

</td>
<td>
zero

</td>
</tr>
<tr>
<td>
top-right 

</td>
<td>
<b>wPicWidthInMBminus1</b>

</td>
</tr>
<tr>
<td>
lower-left 

</td>
<td>
<b>wPicHeightInMBminus1</b> x (<b>wPicWidthInMBminus1</b>+1)

</td>
</tr>
<tr>
<td>
lower-right

</td>
<td>
(<b>wPicHeightInMBminus1</b>+1) x (<b>wPicWidthInMBminus1</b>+1)-1

</td>
</tr>
</table>
 

This member must be zero if the data buffer is among the following types: picture decoding parameters, inverse-quantization matrix, slice control, bitstream data, AYUV, IA44/AI44, DPXD, Highlight, and DCCMD.

If the data buffer is a residual difference block data buffer, <b>dwFirstMBaddress</b> must have the same value as for the corresponding macroblock control command buffer. See <a href="https://msdn.microsoft.com/7a416992-04d3-4307-83b3-9fb94c17d60e">Macroblock-Oriented Picture Decoding</a> for more information.


### -field dwNumMBsInBuffer

Specifies the number of macroblocks of data in the buffer. This count includes skipped macroblocks. Must be zero if the data buffer is among the following types: picture decoding parameters, inverse-quantization matrix, AYUV, IA44/AI44, DPXD, Highlight, or DCCMD.

The value for <b>dwNumMBsInBuffer</b> depends on the type of data buffer being used as shown in the following table.

<table>
<tr>
<th>Buffer Type</th>
<th>Value of dwNumMBsInBuffer</th>
</tr>
<tr>
<td>
Macroblock control command

</td>
<td>
Must be equal to the sum of all values for <i>MBskipsFollowing,</i> added to the number of macroblock control commands in the macroblock control command buffer.

</td>
</tr>
<tr>
<td>
Residual difference block

</td>
<td>
Must have the same value as for the corresponding macroblock control command buffer.

</td>
</tr>
<tr>
<td>
Slice-control command

</td>
<td>
Must be equal to the value of the <b>wNumberMBsInSlice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564049">DXVA_SliceInfo</a> structure in the slice-control buffer.

</td>
</tr>
<tr>
<td>
Bitstream

</td>
<td>
Must have the same value as for the corresponding slice-control command buffer.

</td>
</tr>
</table>
 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564012">DXVA_PictureParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564049">DXVA_SliceInfo</a>
 

 

