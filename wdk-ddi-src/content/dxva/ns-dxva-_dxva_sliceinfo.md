---
UID: NS:dxva._DXVA_SliceInfo
title: "_DXVA_SliceInfo"
author: windows-driver-content
description: The DXVA_SliceInfo structure is sent by the host decoder to the accelerator to specify the slice-level parameters of a slice of bitstream data for off-host bitstream compressed picture decoding.
old-location: display\dxva_sliceinfo.htm
old-project: display
ms.assetid: fd1d0cf5-2ee2-44d8-945f-492af57c3990
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: LPDXVA_SliceInfo structure pointer [Display Devices], DXVA_SliceInfo, DXVA_SliceInfo structure [Display Devices], dxva/LPDXVA_SliceInfo, _DXVA_SliceInfo, dxvaref_04736e26-0c58-4e92-9f45-1675565c9f55.xml, LPDXVA_SliceInfo, *LPDXVA_SliceInfo, display.dxva_sliceinfo, dxva/DXVA_SliceInfo
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
-	DXVA_SliceInfo
product: Windows
targetos: Windows
req.typenames: DXVA_SliceInfo, *LPDXVA_SliceInfo
---

# _DXVA_SliceInfo structure


## -description


The DXVA_SliceInfo structure is sent by the host decoder to the accelerator to specify the slice-level parameters of a slice of bitstream data for off-host bitstream compressed picture decoding.


## -syntax


````
typedef struct _DXVA_SliceInfo {
  WORD  wHorizontalPosition;
  WORD  wVerticalPosition;
  DWORD dwSliceBitsInBuffer;
  DWORD dwSliceDataLocation;
  BYTE  bStartCodeBitOffset;
  BYTE  bReservedBits;
  WORD  wMBbitOffset;
  WORD  wNumberMBsInSlice;
  WORD  wQuantizerScaleCode;
  WORD  wBadSliceChopping;
} DXVA_SliceInfo, *LPDXVA_SliceInfo;
````


## -struct-fields




### -field wHorizontalPosition

Specifies the horizontal position of the first macroblock of the slice expressed in units of macroblocks, with zero indicating the left-most or top-most macroblock of the picture.


### -field wVerticalPosition

Specifies the vertical position of the first macroblock of the slice expressed in units of macroblocks, with zero indicating the left-most or top-most macroblock of the picture.


### -field dwSliceBitsInBuffer

Specifies the total number of bits in the corresponding bitstream data buffer that contain data for the current slice. This must be a multiple of eight for MPEG-1, MPEG-2, MPEG-4. It must also be in the slice-structured mode of H.263, because slice start codes in these cases are byte-aligned.


### -field dwSliceDataLocation

Specifies the location of the first byte containing data for the slice (for example, the location of a slice start code) in the bitstream data buffer. Must be zero if the start of the slice is not within the corresponding bitstream data buffer.


### -field bStartCodeBitOffset

Specifies the number of most significant bits of the byte at <b>dwSliceDataLocation</b> that do not contain data for the slice. <b>bStartCodeBitOffset </b>must be zero for MPEG-1, MPEG-2, and MPEG-4, because slice start codes in these specifications are byte-aligned. <b>bStartCodeBitOffset </b>could possibly be nonzero for H.261 and H.263, because these standards do not force byte alignment of GOB (group of blocks) start codes. This member must be in the range of  zero through 7, and must be zero if the start of the slice is not within the corresponding bitstream data buffer. The most significant bits marked irrelevant for the current slice by <b>bStartCodeBitOffset</b> may contain data for a previous slice in the case of start codes that are not byte aligned (for example, in H.263 baseline mode).


### -field bReservedBits

Reserved bits used for packing and alignment. Must be zero.


### -field wMBbitOffset

Specifies the number of bits of slice header data prior to the first bit of macroblock layer data in the bitstream buffer. For example, if <b>wMBbitOffset</b> is 83, the macroblock layer data for the slice starts after 83 bits of slice header data. Must be zero if the start of the slice is not within the corresponding bitstream data buffer.


### -field wNumberMBsInSlice

Specifies the number of macroblocks of data in the slice, including skipped macroblocks. May be zero if this number cannot be readily determined from the header of the picture and the headers and initial macroblock data of the current and next slice in the bitstream, such as in the rectangular slice and arbitrary slice ordering submodes of the slice mode of H.263. Must not be zero for H.261, MPEG-1, MPEG-2, MPEG-4, or when not using the rectangular slice or arbitrary slice submodes of the slice-structured mode in H.263.


### -field wQuantizerScaleCode

The quantizer scaling code from the slice level of the bitstream, as specified in the particular video coding specification (ranging from 1 through 31 for H.261, H.262/MPEG-2, H.263, MPEG-1, and MPEG-4).


### -field wBadSliceChopping

Specifies the location of data within a slice for a corresponding bitstream data buffer. If zero, indicates that all bits for the slice are in the bitstream data buffer. If nonzero, indicates what part of the bits for the slice are missing from the corresponding bitstream data buffer as follows.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
1

</td>
<td>
The bits for the start of the slice are within the corresponding bitstream data buffer, and the bits for the end of the slice are not (because the bitstream data buffer is full).

</td>
</tr>
<tr>
<td>
2

</td>
<td>
The bits for the start of the slice are not within the corresponding bitstream data buffer (because the previous bitstream data buffer was full), but the bits for the end of the slice are within the corresponding bitstream data buffer.

</td>
</tr>
<tr>
<td>
3

</td>
<td>
The bits for the start of the slice are not within the corresponding bitstream data buffer (because the previous bitstream data buffer was full), and the bits for the end of the slice are also not within the corresponding bitstream data buffer (because the corresponding bitstream data buffer is also full).

</td>
</tr>
</table> 
<div class="alert"><b>Note</b>    Nonzero values of <b>wBadSliceChopping</b> should generally be avoided by the host software decoder.</div><div> </div>

## -remarks


Slice-control buffers are provided to guide the operation of off-host VLD bitstream processing. Slice-control buffers are sent only when the <b>bConfigBitstreamRaw</b> member of <a href="..\dxva\ns-dxva-_dxva_configpicturedecode.md">DXVA_ConfigPictureDecode</a> is 1. The host software decoder must determine the location of slice-level resynchronization points in the bitstream. A <i>slice</i> is defined to be a multimacroblock layer that includes a resynchronization point in the bitstream data.

In H.261 bitstreams, a GOB is considered a slice. In H.263 bitstreams, a sequence of one or more GOBs starting with a GOB start code and containing no additional GOB start codes, is considered a slice. A slice-control buffer must contain one or more DXVA_SliceInfo structures, according to the contents of a corresponding bitstream data buffer.



## -see-also

<a href="..\dxva\ns-dxva-_dxva_configpicturedecode.md">DXVA_ConfigPictureDecode</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_SliceInfo structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

