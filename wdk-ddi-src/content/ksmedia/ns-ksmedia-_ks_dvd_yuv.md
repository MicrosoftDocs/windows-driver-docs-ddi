---
UID: NS:ksmedia._KS_DVD_YUV
title: "_KS_DVD_YUV"
author: windows-driver-content
description: The KS_DVD_YUV structure is used to describe a color in the YUV colorspace.
old-location: stream\ks_dvd_yuv.htm
old-project: stream
ms.assetid: 9b155d09-6fb2-4c6c-bde6-7eadeb09bc40
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKS_DVD_YUV structure pointer [Streaming Media Devices], PKS_DVD_YUV, ksmedia/PKS_DVD_YUV, stream.ks_dvd_yuv, *PKS_DVD_YUV, KS_DVD_YUV structure [Streaming Media Devices], _KS_DVD_YUV, KS_DVD_YUV, dvdref_ea41e501-8a59-4d54-8dde-792ce2673b8c.xml, ksmedia/KS_DVD_YUV
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
-	KS_DVD_YUV
product: Windows
targetos: Windows
req.typenames: "*PKS_DVD_YUV, KS_DVD_YUV"
---

# _KS_DVD_YUV structure


## -description


The KS_DVD_YUV structure is used to describe a color in the YUV colorspace.


## -syntax


````
typedef struct _KS_DVD_YUV {
  UCHAR Reserved;
  UCHAR Y;
  UCHAR V;
  UCHAR U;
} KS_DVD_YUV, *PKS_DVD_YUV;
````


## -struct-fields




#### - Reserved

Reserved. Do not use.


#### - Y

Indicates the luminance (brightness) component of the color.


#### - V

Indicates the color-red (chrominance) component of the color.


#### - U

Indicates the color-blue (chrominance) component of the color.


## -remarks


The KS_DVD_YUV structure is used 



## -see-also

<a href="..\ksmedia\ns-ksmedia-_ks_dvd_ycrcb.md">KS_DVD_YCrCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVD_YUV structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

