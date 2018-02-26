---
UID: NS:d3dumddi._DXVADDI_DECODEBUFFERDESC
title: "_DXVADDI_DECODEBUFFERDESC"
author: windows-driver-content
description: The DXVADDI_DECODEBUFFERDESC structure describes a buffer that is currently passed from the host decoder to the accelerator.
old-location: display\dxvaddi_decodebufferdesc.htm
old-project: display
ms.assetid: 809b4cf8-e4c5-4cb6-b58f-8b6b98111361
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, A, B, C, D, DXVA2_Structs_0946584e-3d1f-4bb4-95d5-7ae2c669814a.xml, DXVADDI_DECODEBUFFERDESC, DXVADDI_DECODEBUFFERDESC structure [Display Devices], E, F, I, O, R, S, U, V, X, _, _DXVADDI_DECODEBUFFERDESC, d3dumddi/DXVADDI_DECODEBUFFERDESC, display.dxvaddi_decodebufferdesc"
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
-	DXVADDI_DECODEBUFFERDESC
product: Windows
targetos: Windows
req.typenames: DXVADDI_DECODEBUFFERDESC
---

# _DXVADDI_DECODEBUFFERDESC structure


## -description


The DXVADDI_DECODEBUFFERDESC structure describes a buffer that is currently passed from the host decoder to the accelerator. 


## -syntax


````
typedef struct _DXVADDI_DECODEBUFFERDESC {
  HANDLE            hBuffer;
  D3DDDIFORMAT      CompressedBufferType;
  UINT              BufferIndex;
  UINT              DataOffset;
  UINT              DataSize;
  UINT              FirstMBaddress;
  UINT              NumMBsInBuffer;
  UINT              Width;
  UINT              Height;
  UINT              Stride;
  UINT              ReservedBits;
  DXVADDI_PVP_HW_IV *pCipherCounter;
} DXVADDI_DECODEBUFFERDESC;
````


## -struct-fields




### -field hBuffer

[in] A handle to the buffer.


### -field CompressedBufferType

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the buffer.


### -field BufferIndex

[in] Reserved. Do not use this member. For more information, see the Remarks section.


### -field DataOffset

[in] The offset of the relevant data from the beginning of the buffer, in bytes. The use of this member is currently restricted to the value zero. 


### -field DataSize

[in] The amount of relevant data in the buffer, in bytes. The location of the last byte of content in the buffer is the value of <b>DataOffset</b> plus the value of <b>DataSize</b> minus 1.


### -field FirstMBaddress

[in] The macroblock address of the first macroblock in the buffer that is passed to the accelerator. The macroblock address is given in raster scan order. The address is determined by the members of the <a href="..\dxva\ns-dxva-_dxva_pictureparameters.md">DXVA_PictureParameters</a> structure. The following table shows examples of macroblock addresses.

<table>
<tr>
<th>Macroblock</th>
<th>Address </th>
</tr>
<tr>
<td>
Top-left 

</td>
<td>
Zero

</td>
</tr>
<tr>
<td>
Top-right 

</td>
<td>
<b>wPicWidthInMBminus1</b> of DXVA_PictureParameters.

</td>
</tr>
<tr>
<td>
Bottom-left 

</td>
<td>
<b>wPicHeightInMBminus1</b> x (<b>wPicWidthInMBminus1</b>+1). Members of DXVA_PictureParameters.

</td>
</tr>
<tr>
<td>
Bottom-right

</td>
<td>
(<b>wPicHeightInMBminus1</b>+1) x (<b>wPicWidthInMBminus1</b>+1)-1. Members of DXVA_PictureParameters.

</td>
</tr>
</table>
 

The <b>FirstMBaddress</b> member must be zero if the data buffer is one of the following types: picture decoding parameters, inverse-quantization matrix, slice control, bitstream data, AYUV, IA44/AI44, DPXD, Highlight, and DCCMD.

If the data buffer is a residual difference block data buffer, <b>FirstMBaddress</b> must have the same value as for the corresponding macroblock control command buffer. 


### -field NumMBsInBuffer

[in] The number of macroblocks of data in the buffer, including skipped macroblocks. This member must be zero if the data buffer is one of the following types: picture decoding parameters, inverse-quantization matrix, AYUV, IA44/AI44, DPXD, Highlight, or DCCMD.

The value for <b>NumMBsInBuffer</b> depends on the type of data buffer that is being used, as shown in the following table.

<table>
<tr>
<th>Buffer type</th>
<th>Value of NumMBsInBuffer</th>
</tr>
<tr>
<td>
Macroblock control command

</td>
<td>
The sum of all of the values for <i>MBskipsFollowing,</i> added to the number of macroblock control commands in the macroblock control command buffer.

</td>
</tr>
<tr>
<td>
Residual difference block

</td>
<td>
The same value as for the corresponding macroblock control command buffer.

</td>
</tr>
<tr>
<td>
Slice-control command

</td>
<td>
The value of the <b>wNumberMBsInSlice</b> member of the <a href="..\dxva\ns-dxva-_dxva_sliceinfo.md">DXVA_SliceInfo</a> structure in the slice-control buffer.

</td>
</tr>
<tr>
<td>
Bitstream

</td>
<td>
The same value as for the corresponding slice-control command buffer.

</td>
</tr>
</table>
 


### -field Width

[in] Reserved. Do not use this member. For more information, see the Remarks section.


### -field Height

[in] Reserved. Do not use this member. For more information, see the Remarks section.


### -field Stride

[in] Reserved. Do not use this member. For more information, see the Remarks section.


### -field ReservedBits

[in] Reserved bits that are used for packing and alignment. This member must be zero.


### -field pCipherCounter

[in] A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_pvp_hw_iv.md">DXVADDI_PVP_HW_IV</a> structure that contains a 128-bit protected video path (PVP) value. 


## -remarks



An array of DXVADDI_DECODEBUFFERDESC structures is referred to as a <i>buffer description list</i>. When a set of buffers is sent from the host decoder to the hardware accelerator, a buffer description list is sent to describe the buffers. The buffer description list contains one DXVADDI_DECODEBUFFERDESC structure for each buffer in this set. The buffer description list starts with a DXVADDI_DECODEBUFFERDESC structure for the first buffer of the first type, followed by a DXVADDI_DECODEBUFFERDESC structure for the next buffer of the same type, and so on. The buffer description list then continues with a DXVADDI_DECODEBUFFERDESC structure for the first buffer of the next type, and so on. This entire list is contained in a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodeexecute.md">D3DDDIARG_DECODEEXECUTE</a> structure.

Because Microsoft DirectX Video Acceleration (VA) version 2.0 uses Microsoft Direct3D surfaces rather than the private surfaces that DirectX VA 1.0 uses, the user-mode display driver obtains values for the index, width, height, and stride from the given compressed buffer type rather than from the values in the <b>BufferIndex</b>, <b>Width</b>, <b>Height</b>, and <b>Stride</b> members. In fact, the Microsoft Direct3D runtime sets these members to zero.




## -see-also

<a href="..\dxva\ns-dxva-_dxva_sliceinfo.md">DXVA_SliceInfo</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_pvp_hw_iv.md">DXVADDI_PVP_HW_IV</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodeexecute.md">D3DDDIARG_DECODEEXECUTE</a>



<a href="..\dxva\ns-dxva-_dxva_pictureparameters.md">DXVA_PictureParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_DECODEBUFFERDESC structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

