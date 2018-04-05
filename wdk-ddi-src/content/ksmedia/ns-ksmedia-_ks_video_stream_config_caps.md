---
UID: NS:ksmedia._KS_VIDEO_STREAM_CONFIG_CAPS
title: "_KS_VIDEO_STREAM_CONFIG_CAPS"
author: windows-driver-content
description: The KS_VIDEO_STREAM_CONFIG_CAPS structure describes the configuration and capabilities of a video stream, including analog video standard (for example, NTSC, PAL or SECAM), scaling, and cropping capabilities; minimum and maximum frame rates; and minimum and maximum data rates.
old-location: stream\ks_video_stream_config_caps.htm
old-project: stream
ms.assetid: a8089653-a14b-4542-bf20-b1b596b1b4ea
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_VIDEO_STREAM_CONFIG_CAPS, KS_VIDEO_STREAM_CONFIG_CAPS, KS_VIDEO_STREAM_CONFIG_CAPS structure [Streaming Media Devices], PKS_VIDEO_STREAM_CONFIG_CAPS, PKS_VIDEO_STREAM_CONFIG_CAPS structure pointer [Streaming Media Devices], _KS_VIDEO_STREAM_CONFIG_CAPS, ksmedia/KS_VIDEO_STREAM_CONFIG_CAPS, ksmedia/PKS_VIDEO_STREAM_CONFIG_CAPS, stream.ks_video_stream_config_caps, vidcapstruct_43cae18b-0430-4a1e-9bac-7de2e32388a6.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KS_VIDEO_STREAM_CONFIG_CAPS
product:
- Windows
targetos: Windows
req.typenames: KS_VIDEO_STREAM_CONFIG_CAPS, *PKS_VIDEO_STREAM_CONFIG_CAPS
---

# _KS_VIDEO_STREAM_CONFIG_CAPS structure


## -description


The KS_VIDEO_STREAM_CONFIG_CAPS structure describes the configuration and capabilities of a video stream, including analog video standard (for example, NTSC, PAL or SECAM), scaling, and cropping capabilities; minimum and maximum frame rates; and minimum and maximum data rates.


## -struct-fields




### -field guid

GUID that specifies the video format type. Possible values include:

KSDATAFORMAT_SPECIFIER_VIDEOINFO

KSDATAFORMAT_SPECIFIER_VIDEOINFO2

KSDATAFORMAT_SPECIFIER_ANALOGVIDEO

KSDATAFORMAT_SPECIFIER_VBI

KSDATAFORMAT_SPECIFIER_MPEG1_VIDEO

KSDATAFORMAT_SPECIFIER_MPEG2_VIDEO

This GUID is identical to the DirectShow AM_MEDIA_TYPE enumeration. For more information about AM_MEDIA_TYPE, see the DirectX SDK documentation.


### -field VideoStandard

Specifies the analog video standards that are supported by the stream. This member can be set to one or more (logically ORed) values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567297">KS_AnalogVideoStandard</a> enumeration.


### -field InputSize

Specifies the size of the incoming signal. <b>InputSize</b> indicates the image rectangle's width and height, in pixels. This is the largest signal that the filter can digitize with each pixel remaining unique. 


### -field MinCroppingSize

Specifies the smallest cropping rectangle allowed, as specified in the <b>rcSource</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567700">KS_VIDEOINFOHEADER</a> structure, which is associated with the <b>DataRange</b> member. 


### -field MaxCroppingSize

Specifies the largest cropping rectangle allowed, as specified in the <b>rcSource</b> member of the KS_VIDEOINFOHEADER structure, which is associated with the <b>DataRange</b> member. 


### -field CropGranularityX

Specifies the horizontal granularity of the cropping size. For example, valid widths could be specified as even multiples of four. 


### -field CropGranularityY

Specifies the vertical granularity of the cropping size. For example, valid heights could be specified as even multiples of four. 


### -field CropAlignX

Specifies the horizontal alignment of the cropping rectangle inside <b>InputSize</b>. For example, the minidriver could specify that valid rectangles must start on a boundary that is a multiple of four. 


### -field CropAlignY

Specifies the vertical alignment of the cropping rectangle inside <b>InputSize</b>. For example, the minidriver could specify that valid rectangles must start on a boundary that is a multiple of four.


### -field MinOutputSize

Specifies the smallest bitmap that this pin can produce.


### -field MaxOutputSize

Specifies the largest bitmap that this pin can produce.


### -field OutputGranularityX

Specifies the granularity of the output bitmap width.


### -field OutputGranularityY

Specifies the granularity of the output bitmap height.


### -field StretchTapsX

Specifies one of the following values to indicate how well the filter can stretch the image's width.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
The filter cannot stretch.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
The filter uses pixel doubling to achieve stretching.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
The filter uses interpolation (2 taps).

</td>
</tr>
<tr>
<td>
3

</td>
<td>
The filter uses a higher-order (smoother) form of interpolation.

</td>
</tr>
</table>
 


### -field StretchTapsY

Specifies one of the following values to indicate how well the filter can stretch the image's height.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
The filter cannot stretch.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
The filter uses pixel doubling to achieve stretching.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
The filter uses interpolation (2 taps).

</td>
</tr>
<tr>
<td>
3

</td>
<td>
The filter uses a higher-order (smoother) form of interpolation.

</td>
</tr>
</table>
 


### -field ShrinkTapsX

Specifies one of the following values to indicate how well the filter can shrink the image's width.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
The filter cannot shrink.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
The filter eliminates some rows of pixels to achieve shrinking.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
The filter uses interpolation (2 taps).

</td>
</tr>
<tr>
<td>
3

</td>
<td>
The filter uses a higher-order (smoother) form of interpolation.

</td>
</tr>
</table>
 


### -field ShrinkTapsY

Specifies one of the following values to indicate how well the filter can shrink the image's height.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
The filter cannot shrink.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
The filter eliminates some columns of pixels to achieve shrinking.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
The filter uses interpolation (2 taps).

</td>
</tr>
<tr>
<td>
3

</td>
<td>
The filter uses a higher-order (smoother) form of interpolation.

</td>
</tr>
</table>
 


### -field MinFrameInterval

Specifies the minimum frame rate allowed. This value applies to capture filters only.


### -field MaxFrameInterval

Specifies the maximum frame rate allowed. This value applies to capture filters only.


### -field MinBitsPerSecond

Specifies the minimum data rate, in bits per second, that this pin can produce.


### -field MaxBitsPerSecond

Specifies the maximum data rate, in bits per second, that this pin can produce.


## -remarks



The KS_VIDEO_STREAM_CONFIG_CAPS structure is identical to the DirectShow VIDEO_STREAM_CONFIG_CAPS structure.

It is important to understand the relationships between the members of this structure. For example, assume the following values for some of the structure members: 

<b>MinCroppingSize</b> = (160, 120) 

<b>MaxCroppingSize</b> = (320, 240) 

<b>CropGranularityX</b> = 4 

<b>CropGranularityY</b> = 8 

These values indicate that valid cropping sizes begin at <b>MinCroppingSize</b> and increase in steps in the <i>x</i>-direction by<b> CropGranularityX</b> and in the <i>y</i>-direction by <b>CropGranularityY</b>. In this case, the <i>x</i>-value can be anywhere from 160 to 320 pixels, in steps of four, and the <i>y</i>-value can be anywhere from 120 to 240 pixels in steps of eight. 

In the example scenario, a few of the valid sizes are: 

<ul>
<li>
160 × 120, 164 × 120, 168 × 120, 172 × 120, and so on. 

</li>
<li>
160 × 128, 164 × 128, 168 × 128, 172 × 128, and so on. 

</li>
<li>
160 × 136, 164 × 136, 168 × 136, 172 × 136, and so on. 

</li>
</ul>
<b>CropAlignX</b> and <b>CropAlignY</b> indicate where the cropping rectangle can be located inside the input size rectangle. Given a 160 × 120 cropping rectangle and a value of 2 for <b>CropAlignX</b> and a value of 4 for <b>CropAlignY</b>, 

some of the valid values for the <b>rcSource</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567700">KS_VIDEOINFOHEADER</a> structure would be: 

<ul>
<li>
(0, 0, 160, 120) 

</li>
<li>
(2, 0, 162, 120) 

</li>
<li>
(2, 4, 162, 124) 

</li>
<li>
(2, 8, 162, 128) 

</li>
</ul>
For a 320 × 240 cropping rectangle and the same cropping alignment values, (2, 4, 322, 244) is one example of the many valid rectangles. 

The <b>MinCroppingSize</b>, <b>MaxCroppingSize</b>, <b>CropGranularityX</b>, <b>CropGranularityY</b>, <b>CropAlignX</b>, and <b>CropAlignY</b> members discussed above work together to specify which values of <b>rcSource</b> are valid for the KS_VIDEOINFOHEADER structure that describes the output pin's media type. The remaining structure members (<b>MinOutputSize</b>, <b>MaxOutputSize</b>, <b>OutputGranularityX</b>, and <b>OutputGranularityY</b>) describe the <b>biWidth</b> and <b>biHeight</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567305">KS_BITMAPINFOHEADER</a> structure, which is contained in the pin's media type KS_VIDEOINFOHEADER structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567297">KS_AnalogVideoStandard</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567305">KS_BITMAPINFOHEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567700">KS_VIDEOINFOHEADER</a>
 

 

