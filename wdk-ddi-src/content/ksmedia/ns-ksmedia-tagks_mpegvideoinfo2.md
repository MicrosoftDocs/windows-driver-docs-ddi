---
UID: NS:ksmedia.tagKS_MPEGVIDEOINFO2
title: tagKS_MPEGVIDEOINFO2
author: windows-driver-content
description: The KS_MPEGVIDEOINFO2 structure describes an MPEG-2 video stream, including bob or weave settings.
old-location: stream\ks_mpegvideoinfo2.htm
old-project: stream
ms.assetid: 735bff90-7406-4fe8-87d5-de3aa48fbcd0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKS_MPEGVIDEOINFO2, KS_MPEGVIDEOINFO2, *PKS_MPEGVIDEOINFO2
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
req.alt-api: KS_MPEGVIDEOINFO2
req.alt-loc: ksmedia.h
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
req.typenames: KS_MPEGVIDEOINFO2, *PKS_MPEGVIDEOINFO2
---

# tagKS_MPEGVIDEOINFO2 structure



## -description
The KS_MPEGVIDEOINFO2 structure describes an MPEG-2 video stream, including bob or weave settings.



## -syntax

````
typedef struct tagKS_MPEGVIDEOINFO2 {
  KS_VIDEOINFOHEADER2 hdr;
  DWORD               dwStartTimeCode;
  DWORD               cbSequenceHeader;
  DWORD               dwProfile;
  DWORD               dwLevel;
  DWORD               dwFlags;
  DWORD               bSequenceHeader[1];
} KS_MPEGVIDEOINFO2, *PKS_MPEGVIDEOINFO2;
````


## -struct-fields

### -field hdr

Specifies a <a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader2.md">KS_VIDEOINFOHEADER2</a> structure that describes the details of the video stream.


### -field dwStartTimeCode

A 25-bit "group-of-pictures" time code at the start of data (not used for DVD).


### -field cbSequenceHeader

The length of the <b>bSequenceHeader</b> member, in bytes (zero for DVD).


### -field dwProfile

Specifies the MPEG-2 profile. This member must be one of the values from the <a href="..\ksmedia\ne-ksmedia-ks_mpeg2profile.md">KS_MPEG2Profile</a> enumeration.


### -field dwLevel

Specifies the MPEG-2 level. This member must be one of the values from the <a href="..\ksmedia\ne-ksmedia-ks_mpeg2level.md">KS_MPEG2Level</a> enumeration.


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader2.md">KS_VIDEOINFOHEADER2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_MPEGVIDEOINFO2 structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

