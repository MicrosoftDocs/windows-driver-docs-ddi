---
UID: NS:ksmedia.tagKS_VIDEOINFOHEADER2
title: tagKS_VIDEOINFOHEADER2
author: windows-driver-content
description: The KS_VIDEOINFOHEADER2 structure describes the details of a video stream, including bob or weave settings, copy protection, and pixel aspect ratio.
old-location: stream\ks_videoinfoheader2.htm
old-project: stream
ms.assetid: 4eb909fe-7ba2-4208-b713-54252022a5cf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKS_VIDEOINFOHEADER2 structure pointer [Streaming Media Devices], tagKS_VIDEOINFOHEADER2, *PKS_VIDEOINFOHEADER2, ksmedia/PKS_VIDEOINFOHEADER2, ksmedia/KS_VIDEOINFOHEADER2, KS_VIDEOINFOHEADER2 structure [Streaming Media Devices], KS_VIDEOINFOHEADER2, PKS_VIDEOINFOHEADER2, vidcapstruct_c789f606-9b19-42b0-8492-3b945141c274.xml, stream.ks_videoinfoheader2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
apiname: 
-	KS_VIDEOINFOHEADER2
product: Windows
targetos: Windows
req.typenames: *PKS_VIDEOINFOHEADER2, KS_VIDEOINFOHEADER2
---

# tagKS_VIDEOINFOHEADER2 structure


## -description


The KS_VIDEOINFOHEADER2 structure describes the details of a video stream, including bob or weave settings, copy protection, and pixel aspect ratio.


## -syntax


````
typedef struct tagKS_VIDEOINFOHEADER2 {
  RECT                rcSource;
  RECT                rcTarget;
  DWORD               dwBitRate;
  DWORD               dwBitErrorRate;
  REFERENCE_TIME      AvgTimePerFrame;
  DWORD               dwInterlaceFlags;
  DWORD               dwCopyProtectFlags;
  DWORD               dwPictAspectRatioX;
  DWORD               dwPictAspectRatioY;
  union {
    DWORD dwControlFlags;
    DWORD dwReserved1;
  };
  DWORD               dwReserved2;
  KS_BITMAPINFOHEADER bmiHeader;
} KS_VIDEOINFOHEADER2, *PKS_VIDEOINFOHEADER2;
````


## -struct-fields




### -field dwControlFlags

In operating systems prior to Windows Vista, this member was named <b>dwReserved1</b> and was required to be zero. In Windows Vista, <b>dwReserved1</b> was combined in a union with a new member named <b>dwControlFlags</b>. If used, <b>dwControlFlags</b> contains a bitwise OR of the flags in the following table.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
AMCONTROL_USED

</td>
<td>
Indicates the <b>dwControlFlags</b> flags are used.

</td>
</tr>
<tr>
<td>
AMCONTROL_PAD_TO_4x3

</td>
<td>
The image should be padded and displayed in a 4 x 3 area.

</td>
</tr>
<tr>
<td>
AMCONTROL_PAD_TO_16x9

</td>
<td>
The image should be padded and displayed in a 16 x 9 area.

</td>
</tr>
<tr>
<td>
AMCONTROL_COLORINFO_PRESENT

</td>
<td>
Additional color information is contained in the upper 24 bits of the <b>dwControlFlags</b> field.

</td>
</tr>
</table> 

The AMCONTROL_USED flag provides backward compatibility with older filters. If the AMCONTROL_USED flag is not set, the remaining bits in this field should be ignored. If a filter uses any other flags, it should set the AMCONTROL_USED flag. 

The two AMCONTROL_PAD_xxx flags are used by decoders to determine the aspect ratio of the output rectangle.

If the AMCONTROL_COLORINFO_PRESENT flag is set, it means the upper 24 bits of the dwControlFlags field are treated as a <a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a> structure. 

See the Remarks section later in this topic for more information about <b>dwControlFlags</b>.


### -field dwReserved1

This member is for backward compatibility. See <b>dwControlFlags </b>for more information.


### -field rcSource

Specifies a clipping rectangle that selects the portion of the active video signal to use. 


### -field rcTarget

Specifies a rectangle that indicates what part of the target buffer to use.


### -field dwBitRate

Specifies a value that indicates the video stream's appropriate data rate, in bits per second.


### -field dwBitErrorRate

Specifies a value that indicates the video stream's data error rate, in bit errors per second.


### -field AvgTimePerFrame

Specifies the average time per frame, in 100-nanosecond units.


### -field dwInterlaceFlags

Specifies interlace information. Undefined flags must be set to zero, or the connection may be rejected. This member can be set to one or more (logical OR) values that are defined in <i>ksmedia.h</i>:
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_INTERLACE_IsInterlaced

</td>
<td>
Indicates an interlace stream. If 0, then the other KS_INTERLACE_Xxx bits are irrelevant.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_1FieldPerSample

</td>
<td>
Indicates one field per media sample. If zero, indicates two fields per media sample.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_Field1First

</td>
<td>
Indicates that Field 1 is first. If zero, indicates that Field 2 is first. Top field in PAL is Field 1, top field in NTSC is Field 2.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_UNUSED

</td>
<td>
Unused.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_FieldPatternMask

</td>
<td>
Indicates the bits used to specify field pattern.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_FieldPatField1Only

</td>
<td>
Indicates that a stream never contains a Field 2.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_FieldPatField2Only

</td>
<td>
Indicates that a stream never contains a Field 1.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_FieldPatBothRegular

</td>
<td>
Indicates that there will be a Field 2 for every Field 1.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_FieldPatBothIrregular

</td>
<td>
Indicates a random pattern of Field 1s and Field 2s.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_DisplayModeMask

</td>
<td>
Invalid for video capture.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_DisplayModeBobOnly

</td>
<td>
Invalid for video capture.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_DisplayModeWeaveOnly

</td>
<td>
Invalid for video capture.

</td>
</tr>
<tr>
<td>
KS_INTERLACE_DisplayModeBobOrWeave

</td>
<td>
Invalid for video capture.

</td>
</tr>
</table> 


### -field dwCopyProtectFlags

Specifies a KSCOPYPROTECTRestrictDuplication value (0x00000001) to indicate if duplication of a stream should be restricted. If undefined, specify zero or the connection will be rejected.


### -field dwPictAspectRatioX

Specifies the <i>x</i> dimension of the picture-aspect ratio (for example, 16 for a 16 × 9 display). The value is expressed in inches-by-inches, not pixels-by-pixels.


### -field dwPictAspectRatioY

Specifies the <i>y</i> dimension of the picture aspect ratio (for example, 9 for 16 × 9 display). The value is expressed in inches-by-inches, not pixels-by-pixels.


### -field dwReserved2

Reserved for system use. Must be set to zero or the connection will be rejected.


### -field bmiHeader

Indicates a <a href="..\ksmedia\ns-ksmedia-tagks_bitmapinfoheader.md">KS_BITMAPINFOHEADER</a> structure that contains color and dimension information for the video image bitmap.


## -remarks


To describe a video stream without bob or weave settings, use <a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader.md">KS_VIDEOINFOHEADER</a>.

The KS_VIDEOINFOHEADER2 structure is identical to the DirectShow <a href="http://go.microsoft.com/fwlink/p/?linkid=96751">VIDEOINFOHEADER2</a> structure.

Capture minidrivers that produce video fields (instead of frames) must use the <a href="..\ksmedia\ns-ksmedia-tagks_datarange_video2.md">KS_DATARANGE_VIDEO2</a> structure, which contains the KS_VIDEOINFOHEADER2 structure.

A source filter can request that the sink filter take only a section of the video by providing values that effectively define a clipping rectangle in the <b>rcSource</b> member. However, if the sink filter does not check for the clipping rectangle on connection, the sink filter simply renders all of the video, effectively ignoring any clipping information passed from the source filter to the sink filter.

Ideally, a sink filter checks <b>rcSource</b> and if the sink filter does not support image extraction, and the rectangle is <i>not</i> empty, then it rejects the connection. A filter should use the Win32 function <b>SetRectEmpty</b> to reset a rectangle to all zeros (and set <b>IsRectEmpty</b> to later check the rectangle).

The <b>rcTarget</b> member specifies the destination rectangle for the video. Most source filters set this member to all zeros. A downstream filter can request that the video be placed in a particular area of the buffers that it supplies. In this case, it calls the Win32 function <b>QueryAccept</b> with a nonempty target.

If the AMCONTROL_COLORINFO_PRESENT flag is set in the <b>dwControlFlags</b> member, you can cast the <b>dwControlFlags</b> value to a <a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a> structure to access the extended color information. For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=96751">VIDEOINFOHEADER2</a>.



## -see-also

<a href="..\ksmedia\ns-ksmedia-tagks_datarange_video2.md">KS_DATARANGE_VIDEO2</a>

<a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader.md">KS_VIDEOINFOHEADER</a>

<a href="..\ksmedia\ns-ksmedia-tagks_bitmapinfoheader.md">KS_BITMAPINFOHEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_VIDEOINFOHEADER2 structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

