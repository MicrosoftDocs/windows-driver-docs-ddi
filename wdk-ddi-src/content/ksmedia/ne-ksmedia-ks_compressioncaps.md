---
UID: NE:ksmedia.KS_CompressionCaps
title: KS_CompressionCaps
author: windows-driver-content
description: The KS_CompressionCaps enumeration defines compression capabilities of a device.
old-location: stream\ks_compressioncaps.htm
old-project: stream
ms.assetid: 47781af6-bf14-4b95-bef2-506aadb2d1fb
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_CompressionCaps, KS_CompressionCaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_CompressionCaps
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
req.typenames: KS_CompressionCaps
---

# KS_CompressionCaps enumeration



## -description
The KS_CompressionCaps enumeration defines compression capabilities of a device.



## -syntax

````
typedef enum  { 
  KS_CompressionCaps_CanQuality   = 1,
  KS_CompressionCaps_CanCrunch    = 2,
  KS_CompressionCaps_CanKeyFrame  = 4,
  KS_CompressionCaps_CanBFrame    = 8,
  KS_CompressionCaps_CanWindow    = 0x10
} KS_CompressionCaps;
````


## -enum-fields

### -field KS_CompressionCaps_CanQuality

The video compressor supports quality settings.


### -field KS_CompressionCaps_CanCrunch

The video compressor can compress the video to a specified data rate. If a minidriver supports this capability, the <b>dwBitRate</b> member of the <a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader.md">KS_VIDEOINFOHEADER</a> structure specifies the default data rate.


### -field KS_CompressionCaps_CanKeyFrame

The video compressor supports a user-specified key-frame rate.


### -field KS_CompressionCaps_CanBFrame

The video compressor supports a user-specified P frame interval. The frames that occur between the key frames and P frames are bidirectional (B) frames.


### -field KS_CompressionCaps_CanWindow

The video compressor supports a user-specified window size (that is, the number of frames whose average size cannot exceed the specified data rate).


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader.md">KS_VIDEOINFOHEADER</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-ksproperty_videocompression_getinfo_s.md">KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_CompressionCaps enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

