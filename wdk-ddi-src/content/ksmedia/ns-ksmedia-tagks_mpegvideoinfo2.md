---
UID: NS:ksmedia.tagKS_MPEGVIDEOINFO2
title: tagKS_MPEGVIDEOINFO2 (ksmedia.h)
description: The KS_MPEGVIDEOINFO2 structure describes an MPEG-2 video stream, including bob or weave settings.
old-location: stream\ks_mpegvideoinfo2.htm
tech.root: stream
ms.assetid: 735bff90-7406-4fe8-87d5-de3aa48fbcd0
ms.date: 04/23/2018
ms.keywords: "*PKS_MPEGVIDEOINFO2, KS_MPEGVIDEOINFO2, KS_MPEGVIDEOINFO2 structure [Streaming Media Devices], PKS_MPEGVIDEOINFO2, PKS_MPEGVIDEOINFO2 structure pointer [Streaming Media Devices], ksmedia/KS_MPEGVIDEOINFO2, ksmedia/PKS_MPEGVIDEOINFO2, stream.ks_mpegvideoinfo2, tagKS_MPEGVIDEOINFO2, vidcapstruct_decbdb49-a4a2-44d6-a005-bd3cbe0df02e.xml"
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
-	KS_MPEGVIDEOINFO2
product:
- Windows
targetos: Windows
req.typenames: KS_MPEGVIDEOINFO2, *PKS_MPEGVIDEOINFO2
---

# tagKS_MPEGVIDEOINFO2 structure


## -description


The KS_MPEGVIDEOINFO2 structure describes an MPEG-2 video stream, including bob or weave settings.


## -struct-fields




### -field hdr

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567702">KS_VIDEOINFOHEADER2</a> structure that describes the details of the video stream.


### -field dwStartTimeCode

A 25-bit "group-of-pictures" time code at the start of data (not used for DVD).


### -field cbSequenceHeader

The length of the <b>bSequenceHeader</b> member, in bytes (zero for DVD).


### -field dwProfile

Specifies the MPEG-2 profile. This member must be one of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567662">KS_MPEG2Profile</a> enumeration.


### -field dwLevel

Specifies the MPEG-2 level. This member must be one of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567660">KS_MPEG2Level</a> enumeration.


### -field dwFlags

Specifies the flags that indicate preferences. This member can be set to one or more (logical OR) values that are defined in <i>ksmedia.h</i>.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>KS_MPEG2_DoPanScan</b>

</td>
<td>
If set, the MPEG-2 video decoder should crop the output image based on pan-scan vectors in the picture display extension and change the picture aspect ratio accordingly.

</td>
</tr>
<tr>
<td>
<b>KS_MPEG2_DVDLine21Field1</b>

</td>
<td>
If set, the MPEG-2 decoder must be able to produce an output pin for DVD-style closed caption data found in the GOP layer of Field 1.

</td>
</tr>
<tr>
<td>
<b>KS_MPEG2_DVDLine21Field2</b>

</td>
<td>
If set, the MPEG-2 decoder must be able to produce an output pin for DVD-style closed caption data found in the GOP layer of Field 2.

</td>
</tr>
<tr>
<td>
<b>KS_MPEG2_SourceIsLetterboxed</b>

</td>
<td>
If set, indicates that black bars have been encoded in the top and bottom of the video.

</td>
</tr>
<tr>
<td>
<b>KS_MPEG2_FilmCameraMode</b>

</td>
<td>
If set, indicates "film mode" used for 625/50 content. If cleared, indicates that "camera mode" was used.

</td>
</tr>
<tr>
<td>
<b>KS_MPEG2_LetterboxAnalogOut</b>

</td>
<td>
If set, and the stream is sent to an analog output, then the stream should be letterboxed. Streams sent to VGA should be letterboxed only by renderers.

</td>
</tr>
<tr>
<td>
<b>KS_MPEG2_DSS_UserData</b>

</td>
<td>
If set, the MPEG-2 decoder must process DSS-style user data.

</td>
</tr>
<tr>
<td>
<b>KS_MPEG2_DVB_UserData</b>

</td>
<td>
If set, the MPEG-2 decoder must process DVB-style user data.

</td>
</tr>
<tr>
<td>
<b>KS_MPEG2_27MHzTimebase</b>

</td>
<td>
If set, the PTS and DTS timestamps advance at 27 MHz rather than 90 kHz.

</td>
</tr>
</table>
 


### -field bSequenceHeader

The length of the <b>bSequenceHeader</b> member, in bytes (zero for DVD).


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567702">KS_VIDEOINFOHEADER2</a>
 

 

